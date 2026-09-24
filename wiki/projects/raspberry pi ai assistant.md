# Le'bama — Raspberry Pi AI Assistant

**Type:** Project
**Tags:** #project #electronics #ai #raspberrypi #software #homeassistant
**Last updated:** 2026-09-23

---

## Concept

Le'bama — a personal voice assistant running on a Raspberry Pi. **Primary goal: replace Alexa/Google with something that actually answers instead of "sorry, I can't help with that," and has a sense of humor** — explicitly *not* fully local, because a local model can't match Claude (or another cloud LLM) for quality and wit. Spotify, Bluetooth speaker duty, home automation, and language practice are all secondary — nice to have once the core voice loop works.

**2026-09-23 priority clarification:** voice Q&A is THE point of this project, not one feature among several. Spotify/Bluetooth/automation are explicitly second-priority. This reorders the build path below — the voice loop (wake word → STT → Claude → TTS) now comes before Spotify/Bluetooth/HA setup, not after. Also resolves the "Claude API or Ollama" open question: **Claude API, decided** — the entire motivation is cloud-quality answers and personality, which rules out local models by definition.

**2026-09-23 architecture revision:** original plan (below, kept for history) was built around Rhasspy, which its own creator archived in 2022-2023 when he joined the Home Assistant team to fold its functionality directly into HA's built-in "Assist" voice pipeline. Rhasspy is no longer the recommended path. Also decided: **Raspberry Pi OS (standard), not Home Assistant OS (HAOS)** — HAOS's locked-down, containerized model fights the two things that turned out to be core requirements (Spotify via Raspotify, and bidirectional Bluetooth audio), both of which need native OS-level access HAOS doesn't cleanly offer.

**Open question raised 2026-09-23, unresolved:** given voice is primary and automation is explicitly secondary, is Home Assistant needed *at all* in the first build phase? None of Spotify (Raspotify), Bluetooth (BlueZ), or the voice loop itself require HA — HA's only role is (a) pre-built orchestration glue for wake word → STT → LLM → TTS via its Assist pipeline, and (b) actual smart-home device control, which doesn't exist yet. A lightweight custom bridge script can do (a) directly against the Wyoming services without running all of HA. Leaning toward: build the voice loop standalone first, add HA later only once there's real hardware to automate — see revised Build Path below. Not yet confirmed with Nykel.

---

## Reference Videos

1. [my local, AI Voice Assistant (I replaced Alexa!!)](https://www.youtube.com/watch?v=XvbVePuP7NY)
2. [Create an AI Voice Assistant in 5 minutes - Powered by GPT-4o](https://www.youtube.com/watch?v=E7qxYWLWOtk) *(architecture reference — swap GPT-4o → Claude)*
3. [I Built a Local AI Assistant: 100% Free & No Subscriptions!](https://www.youtube.com/watch?v=7ffF3fumhcQ)
4. [How to build a multilingual conversational AI voice assistant](https://www.raspberrypi.com/news/how-to-build-a-multilingual-conversational-ai-voice-assistant/) *(uses ElevenLabs' commercial API, not a local stack — the multilingual concept transfers, the specific implementation doesn't. Whisper/Piper/Claude are all natively multilingual already, so no new tool needed — see Language Practice note below)*

---

## Stack (revised 2026-09-23)

| Layer | Tool | Notes |
|---|---|---|
| **Base OS** | Raspberry Pi OS (64-bit) | Not HAOS — see architecture revision note above |
| **Smart home hub** | Home Assistant, **Container install** (Docker) | Not HAOS. Gives up the one-click Add-on Store, but Whisper/Piper/openWakeWord have official standalone Docker images for exactly this setup ("Wyoming protocol" services) |
| **Wake word** | openWakeWord (Wyoming/Docker) | Stock wake words available; "Le'bama"/"Hey Bama" needs a custom-trained model (openWakeWord Colab notebook) |
| **STT** | Whisper (Wyoming/Docker) | Local, offline |
| **TTS** | Piper (Wyoming/Docker) | Local, offline, many voice options |
| **LLM / Brain** | Claude, via a small local bridge script | HA's "conversation agent" fallback — home-automation intents handled natively by HA first, unrecognized/open queries forwarded to Claude |
| **Spotify** | Raspotify | Makes the Pi a real Spotify Connect target — shows up as a playable device in the Spotify app, controllable by voice via HA's Spotify integration |
| **Bluetooth audio (both directions)** | BlueZ + bluez-alsa/PulseAudio | Pi as a Bluetooth receiver (phone → Pi speaker) and/or sender (Pi audio → external BT speaker). Native-OS only — this plus Spotify is why HAOS was ruled out |
| **Hardware** | Raspberry Pi 4 or 5 | Pi 5 preferred |
| **Microphone** | USB mic or ReSpeaker HAT | ReSpeaker has built-in noise cancellation |
| **Speaker** | 3.5mm, USB, or Bluetooth | Bluetooth now explicitly supported per above |

---

## Architecture (revised 2026-09-23)

```
[Wake Word — openWakeWord]
        ↓
[STT — Whisper]
        ↓
[Intent recognized by HA?]
    ↙                    ↘
[HA-native intent]         [Open query / complex]
 ├─ home automation        [Claude via bridge → response]
 └─ Spotify (Raspotify)
        ↘                    ↙
        [Piper TTS → Speaker or Bluetooth]
```

Simple intents (lights, timers, "play [X] on Spotify") → Home Assistant + Raspotify handle directly, no AI call needed.
Open-ended queries → forwarded to Claude via the bridge, response piped through Piper.
Output routes to the wired speaker or a paired Bluetooth speaker; input can also come via Bluetooth (phone → Pi) independent of the voice pipeline.

---

## LLM Options

**Decided 2026-09-23: Claude API.** Not close — the whole motivation for this project is answers with actual quality and personality ("Alexa doesn't have a sense of humor"), which a small local model running on a Pi can't deliver. Fully-local/offline was never the goal here. Ollama table kept below for reference only.

| Option | What it is | Pros | Cons |
|---|---|---|---|
| **Claude API** ✅ | Actual Claude, called over internet | Best quality by far, has personality | Needs internet + API key; small usage cost |
| **Ollama (local)** | Open-source model running on the Pi itself (Phi-3, Gemma, Llama 3) | Fully offline, free, private, no API key | Slower responses on Pi hardware; smaller models = less capable; doesn't serve the actual goal |

**Ollama on Pi — realistic expectations (reference only, not the chosen path):**

| Model | Size | Pi 4 8GB | Pi 5 8GB |
|---|---|---|---|
| Phi-3 Mini (3.8B) | ~2.3GB | Slow (~30–60s) | Usable (~10–20s) |
| Gemma 2 (2B) | ~1.6GB | Marginal | Better |
| Llama 3.2 (3B) | ~2GB | Slow | Usable |
| Llama 3 (8B) | ~4.7GB | Very slow | Slow but possible |

For Ollama to feel tolerable, Pi 5 8GB is the minimum. Pi 4 will frustrate you for LLM inference.

---

## Pi 4 vs Pi 5 — For Le'bama Specifically

| | Raspberry Pi 4 (8GB) | Raspberry Pi 5 (8GB) |
|---|---|---|
| **CPU** | Cortex-A72 @ 1.8GHz | Cortex-A76 @ 2.4GHz (~2–3× faster) |
| **RAM** | Up to 8GB | Up to 8GB |
| **Price (8GB)** | ~$75 MSRP (often $90–120 market) | ~$80 MSRP |
| **PCIe slot** | No | Yes — add NVMe SSD (huge for HA + Ollama model storage) |
| **Rhasspy + Piper** | Fine | Fine, faster |
| **Home Assistant** | Fine on 4GB+ | Fine, snappier |
| **Whisper STT** | Slow on base model (~20–30s) | Noticeably faster (~5–10s) |
| **Ollama (local LLM)** | Painful — don't bother | Usable with small models (3B–4B) |
| **Claude API** | Totally fine — Pi just routes the call | Totally fine |
| **Verdict** | Good if using Claude API only | **Get this one** — especially if using Ollama |

**Bottom line:**
- Using **Claude API** → Pi 4 8GB works fine, saves money
- Using **Ollama** → Pi 5 8GB, no question. Also buy the active cooler and consider an NVMe hat for faster model loading.
- Running **HA + Rhasspy + Ollama all on one Pi** → Pi 5 8GB is the minimum viable config

---

## Build Path (revised 2026-09-23, reordered voice-first)

**Phase 1 — Core voice loop (the actual point of the project):**
- [x] Flash Raspberry Pi OS (64-bit) — done, Pi working and set up
- [ ] Install Docker + Docker Compose
- [ ] Run Whisper, Piper, and openWakeWord as standalone Wyoming-protocol Docker services (no HA yet)
- [ ] Wire up mic + speaker
- [ ] Write a small bridge script: wake word event → stream audio to Whisper → send transcript to Claude API → send response text to Piper → play audio. This is standalone Python, not an HA integration
- [ ] Train a custom wake word ("Le'bama" / "Hey Bama") via openWakeWord's Colab notebook, if not sticking with a stock wake word
- [ ] System prompt + personality — define who Le'bama is (this is what's supposed to beat Alexa's blandness)
- [ ] Test open-ended queries through the full voice loop end-to-end
- [ ] Add internet search layer for live info queries (Tavily or DuckDuckGo API)
- [ ] Polish: conversation history, error handling, fallback responses

**Phase 2 — Secondary features (once Phase 1 works):**
- [ ] Install Raspotify — standalone, makes the Pi a Spotify Connect target
- [ ] Set up BlueZ + bluez-alsa (or PulseAudio/PipeWire Bluetooth module) — test both directions: phone → Pi, and Pi → external BT speaker
- [ ] Add simple intent matching in the bridge script (e.g. "play X on Spotify") so those commands short-circuit before hitting Claude — no HA required for this
- [ ] **Language practice mode:** download a Piper voice model for the target practice language (Mandarin, per [[chinese]]); confirm Whisper transcribes it accurately; add a system-prompt mode where Claude corrects grammar/pronunciation notes and stays in the target language rather than just answering in it — this is the actual "practice" part the reference article's ElevenLabs example doesn't really do

**Phase 3 — Home automation (only once there's real hardware to automate):**
- [ ] Run Home Assistant as a Docker Container
- [ ] Decide then: migrate the bridge script's voice pipeline into HA's Assist (gets HA's device/entity handling for free), or keep the standalone script and have it call HA's API only for automation intents
- [ ] Connect real devices/entities, test voice commands

---

## Open Questions

- [x] Rhasspy 2 vs. 3? — moot, Rhasspy dropped entirely in favor of HA's native Assist pipeline (2026-09-23)
- [x] Same Pi for everything, or separate Pi for Home Assistant? — same Pi, one dedicated box for Le'bama (2026-09-23)
- [x] HAOS or regular OS? — regular Raspberry Pi OS, decided 2026-09-23 specifically because of the Spotify/Bluetooth requirements
- [x] Claude API or Ollama (local)? — **Claude API, confirmed 2026-09-23.** Explicitly not-fully-local was the goal from the start; local models can't match the quality/personality bar this project is being built for.
- [ ] Home Assistant in Phase 1 at all, or only add it in Phase 3 once there's real hardware to automate? — leaning "only in Phase 3" per 2026-09-23 priority clarification above, not yet confirmed
- [ ] Piper voice — pick one from the voice list
- [ ] Wake word — "Le'bama", "Hey Bama", or a stock option to start with and customize later?
- [ ] Always-on listening vs. push-to-talk?
- [ ] Language practice: Mandarin only (matches current [[chinese]] goal), or also Spanish/English-vocab per [[english]]?

---

## Status

Building — OS decided (Raspberry Pi OS), LLM decided (Claude API), priority order locked (voice loop first, Spotify/Bluetooth/automation second/third), build path reordered accordingly. Open question: whether Home Assistant belongs in Phase 1 at all (leaning no).

---

## Related

- [[ollama local llm]]
- [[discord wiki bot]]
- [[things to learn]]
