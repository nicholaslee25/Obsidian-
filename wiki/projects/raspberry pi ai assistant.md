# Le'bama — Raspberry Pi AI Assistant

**Type:** Project
**Tags:** #project #electronics #ai #raspberrypi #software #homeassistant
**Last updated:** 2026-06-02

---

## Concept

Le'bama — a personal voice assistant running on a Raspberry Pi. Rhasspy handles the voice pipeline, Home Assistant is the smart home hub, Claude is the brain, Piper handles speech output. Goal: replace Alexa/Google with something actually yours.

---

## Reference Videos

1. [my local, AI Voice Assistant (I replaced Alexa!!)](https://www.youtube.com/watch?v=XvbVePuP7NY)
2. [Create an AI Voice Assistant in 5 minutes - Powered by GPT-4o](https://www.youtube.com/watch?v=E7qxYWLWOtk) *(architecture reference — swap GPT-4o → Claude)*
3. [I Built a Local AI Assistant: 100% Free & No Subscriptions!](https://www.youtube.com/watch?v=7ffF3fumhcQ)

---

## Stack

| Layer | Tool | Notes |
|---|---|---|
| **Voice pipeline** | Rhasspy | Open-source, fully offline voice assistant framework. Handles wake word → STT → intent recognition → TTS orchestration. Integrates with Home Assistant via MQTT. |
| **Smart home hub** | Home Assistant | Runs on Pi (or dedicated Pi). Controls lights, switches, thermostats, media. Le'bama routes home automation intents here. |
| **LLM / Brain** | Claude *(see note below)* | For complex queries beyond simple home automation. |
| **TTS** | Piper | Fast, local, runs on Pi. Many voice options. Free. |
| **Hardware** | Raspberry Pi 4 or 5 | Pi 5 preferred for Rhasspy + HA together |
| **Microphone** | USB mic or ReSpeaker HAT | ReSpeaker has built-in noise cancellation |
| **Speaker** | 3.5mm or USB | Anything works |

---

## Architecture

```
[Wake Word — Rhasspy]
        ↓
[STT — Rhasspy / Whisper]
        ↓
[Intent recognized?]
    ↙           ↘
[Simple intent]   [Open query / complex]
[Home Assistant]  [Claude → response]
        ↘           ↙
        [Piper TTS → Speaker]
```

Simple intents (turn off lights, set timer, play music) → Home Assistant handles directly.
Open-ended queries → forwarded to Claude, response piped through Piper.

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

## Build Path

- [ ] Decide: same Pi for Rhasspy + HA, or dedicated Pi for HA?
- [ ] Flash Raspberry Pi OS (64-bit), install Home Assistant (HAOS or supervised)
- [ ] Install Rhasspy — configure wake word, STT backend, intent system
- [ ] Install and configure Piper TTS in Rhasspy
- [ ] Wire up mic + speaker, test full Rhasspy pipeline end-to-end
- [ ] Set up Anthropic Python SDK (or Ollama if going local)
- [ ] Write custom intent handler: catch open queries → send to Claude → return TTS response
- [ ] Connect Rhasspy intents → Home Assistant (MQTT or REST)
- [ ] Test home automation commands through Le'bama
- [ ] Add internet search layer for live info queries (Tavily or DuckDuckGo API)
- [ ] System prompt + personality — define who Le'bama is
- [ ] Polish: conversation history, error handling, fallback responses

---

## Open Questions

- [ ] Claude API or Ollama (local)? — see note above
- [ ] Rhasspy 2 (stable) vs. Rhasspy 3 (newer, more modular)?
- [ ] Same Pi for everything, or separate Pi for Home Assistant?
- [ ] Piper voice — pick one from the voice list
- [ ] Wake word — "Le'bama", "Hey bama", custom?
- [ ] Always-on listening vs. push-to-talk?

---

## Status

Planning — stack selected, following reference videos

---

## Related

- [[ollama local llm]]
- [[discord wiki bot]]
- [[things to learn]]
