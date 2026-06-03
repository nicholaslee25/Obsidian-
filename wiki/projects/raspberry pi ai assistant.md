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

## ⚠️ Claude "Locally Hosted" — Important Note

Anthropic's Claude **cannot run locally** — it's a closed, proprietary model served via API only. "Locally hosted" options:

| Option | What it actually is | Trade-off |
|---|---|---|
| **Claude API** | Actual Claude, called over internet | Needs internet + API key. Has usage cost. Best quality. |
| **Ollama (local LLM)** | Open-source model (Llama 3, Mistral, Qwen) running on Pi | Fully offline, free, no internet needed. Not Claude — noticeably less capable, especially on Pi hardware. |
| **Local API proxy** | Routes Claude API calls through a local endpoint | Still needs internet for uncached queries. Adds complexity for minimal benefit. |

**Decision needed:** True offline (Ollama) vs. internet-dependent but actually Claude (API). Recommend Claude API — the quality difference is real, and a Pi can handle the orchestration even if it can't run the model.

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
