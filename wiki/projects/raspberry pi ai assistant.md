# Le'bama — Raspberry Pi AI Assistant

**Type:** Project
**Tags:** #project #electronics #ai #raspberrypi #software #homeassistant
**Last updated:** 2026-09-23

---

## Concept

Le'bama — a personal voice assistant running on a Raspberry Pi. Goal: replace Alexa/Google with something that actually answers instead of "sorry, I can't help with that," plus plays Spotify, works as a Bluetooth speaker, and automates the house.

**2026-09-23 architecture revision:** original plan (below, kept for history) was built around Rhasspy, which its own creator archived in 2022-2023 when he joined the Home Assistant team to fold its functionality directly into HA's built-in "Assist" voice pipeline. Rhasspy is no longer the recommended path. Also decided: **Raspberry Pi OS (standard), not Home Assistant OS (HAOS)** — HAOS's locked-down, containerized model fights the two things that turned out to be core requirements (Spotify via Raspotify, and bidirectional Bluetooth audio), both of which need native OS-level access HAOS doesn't cleanly offer.

---

## Reference Videos

1. [my local, AI Voice Assistant (I replaced Alexa!!)](https://www.youtube.com/watch?v=XvbVePuP7NY)
2. [Create an AI Voice Assistant in 5 minutes - Powered by GPT-4o](https://www.youtube.com/watch?v=E7qxYWLWOtk) *(architecture reference — swap GPT-4o → Claude)*
3. [I Built a Local AI Assistant: 100% Free & No Subscriptions!](https://www.youtube.com/watch?v=7ffF3fumhcQ)

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

Two viable paths — both work with the Rhasspy + HA + Piper stack:

| Option | What it is | Pros | Cons |
|---|---|---|---|
| **Ollama (local)** | Open-source model running on the Pi itself (Phi-3, Gemma, Llama 3) | Fully offline, free, private, no API key | Slower responses on Pi hardware; smaller models = less capable than Claude |
| **Claude API** | Actual Claude, called over internet | Best quality by far | Needs internet + API key; small usage cost |

**Ollama on Pi — realistic expectations:**

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

## Build Path (revised 2026-09-23)

- [x] Flash Raspberry Pi OS (64-bit) — done, Pi working and set up
- [ ] Install Docker + Docker Compose
- [ ] Install Raspotify — quick standalone win, test as a real Spotify Connect target before touching anything else
- [ ] Set up BlueZ + bluez-alsa (or PulseAudio/PipeWire Bluetooth module) — test both directions: phone → Pi, and Pi → external BT speaker
- [ ] Run Home Assistant as a Docker Container
- [ ] Add Whisper, Piper, and openWakeWord as Wyoming-protocol Docker services, wire into HA's Assist pipeline
- [ ] Wire up mic + speaker, test the voice pipeline end-to-end with zero AI involved (wake word → built-in HA command → Piper response)
- [ ] Train a custom wake word ("Le'bama" / "Hey Bama") via openWakeWord's Colab notebook, if not sticking with a stock wake word
- [ ] Write the Claude bridge script (small local service, OpenAI-compatible endpoint backed by the Claude API)
- [ ] Wire the bridge into HA as the Assist pipeline's fallback conversation agent (check HACS for a direct Anthropic integration first; "Extended OpenAI Conversation" + bridge is the documented fallback)
- [ ] Test open-ended queries through the full voice loop
- [ ] Set up HA's Spotify integration, confirm voice-triggered "play X on Spotify" routes to the Raspotify-connected Pi
- [ ] Home automation: connect real devices/entities, test voice commands
- [ ] Add internet search layer for live info queries (Tavily or DuckDuckGo API)
- [ ] System prompt + personality — define who Le'bama is
- [ ] Polish: conversation history, error handling, fallback responses

---

## Open Questions

- [x] Rhasspy 2 vs. 3? — moot, Rhasspy dropped entirely in favor of HA's native Assist pipeline (2026-09-23)
- [x] Same Pi for everything, or separate Pi for Home Assistant? — same Pi, one dedicated box for Le'bama (2026-09-23)
- [x] HAOS or regular OS? — regular Raspberry Pi OS, decided 2026-09-23 specifically because of the Spotify/Bluetooth requirements
- [ ] Claude API or Ollama (local)? — leaning Claude API per the original comparison table above, not revisited yet
- [ ] Piper voice — pick one from the voice list
- [ ] Wake word — "Le'bama", "Hey Bama", or a stock option to start with and customize later?
- [ ] Always-on listening vs. push-to-talk?

---

## Status

Building — OS decided (Raspberry Pi OS), architecture locked in (see 2026-09-23 revision above), starting the build path for real

---

## Related

- [[ollama local llm]]
- [[discord wiki bot]]
- [[things to learn]]
