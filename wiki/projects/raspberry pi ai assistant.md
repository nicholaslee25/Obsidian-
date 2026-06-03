# Raspberry Pi AI Assistant

**Type:** Project
**Tags:** #project #electronics #ai #raspberrypi #software
**Last updated:** 2026-06-02

---

## Concept

A voice assistant running on a Raspberry Pi — locally hosted interface, Claude as the brain, internet access enabled. Goal: replace Alexa/Google with something actually personal and controllable.

---

## Reference Videos

1. [my local, AI Voice Assistant (I replaced Alexa!!)](https://www.youtube.com/watch?v=XvbVePuP7NY)
2. [Create an AI Voice Assistant in 5 minutes - Powered by GPT-4o](https://www.youtube.com/watch?v=E7qxYWLWOtk) *(swap GPT-4o → Claude API)*
3. [I Built a Local AI Assistant: 100% Free & No Subscriptions!](https://www.youtube.com/watch?v=7ffF3fumhcQ)

---

## Architecture

```
[Wake Word] → [Microphone] → [STT] → [Claude API] → [TTS] → [Speaker]
                                           ↑
                                    [Internet / Tools]
```

### Components

| Layer | Tool / Option | Notes |
|---|---|---|
| **Hardware** | Raspberry Pi 4 or 5 | Pi 5 preferred for speed; Pi 4 works |
| **Microphone** | USB mic or ReSpeaker HAT | ReSpeaker has built-in noise cancellation + wake word chip |
| **Speaker** | 3.5mm audio out or USB speaker | Any small speaker works |
| **Wake word** | Porcupine (Picovoice) or custom keyword | "Hey Claude", "Hey Pi", etc. |
| **STT** | Whisper (OpenAI, runs locally) | Faster-Whisper for Pi performance |
| **LLM** | Claude API (Anthropic) | Requires internet + API key; not fully local |
| **TTS** | Piper (local, fast) or ElevenLabs | Piper is free and runs on Pi; ElevenLabs sounds better but costs |
| **Internet access** | Pass web search results as context | Use a search API (SerpAPI, Tavily, or DuckDuckGo) to give Claude live info |
| **Orchestration** | Python script | Ties all layers together |

---

## Key Decisions

- **Fully local vs. API-dependent:** Videos 1 and 3 go fully local (Ollama + local TTS/STT). Video 2 uses cloud API. Your version = hybrid — local STT/TTS, cloud Claude API for the brain.
- **"Local" here means:** The Pi handles audio input/output and orchestration. Claude inference happens via API (not on-device). Trade-off: needs internet, has API cost, but Claude >>> any model that runs on Pi hardware.
- **Internet access for Claude:** Feed Claude real-time info by running a web search step before each API call when needed. Tools like Tavily or SerpAPI return clean search results you can pass as context.

---

## Build Path

- [ ] Flash Raspberry Pi OS (64-bit) onto SD card
- [ ] Install Python 3.10+, set up virtual env
- [ ] Wire up USB mic + test audio in/out
- [ ] Install and test Faster-Whisper (STT)
- [ ] Install and test Piper (TTS)
- [ ] Set up Anthropic Python SDK, test basic Claude API call
- [ ] Implement wake word detection (Porcupine free tier or keyword spotting)
- [ ] Build orchestration loop: wake → record → transcribe → call Claude → speak response
- [ ] Add internet/search layer: detect when query needs live info, run search, inject into prompt
- [ ] Polish: conversation history, system prompt, error handling
- [ ] Optional: Home automation hooks (lights, music, etc.)

---

## Open Questions

- [ ] Pi 4 or Pi 5? (Pi 5 has noticeably better performance for Whisper)
- [ ] Piper TTS voice selection (many voices available — pick one)
- [ ] Always-on listening vs. push-to-talk? (Push-to-talk is simpler and more private)
- [ ] System prompt — what personality/context does this assistant have?
- [ ] API cost management — log usage, set monthly cap

---

## Status

Planning — following reference videos

---

## Related

- [[ollama local llm]]
- [[discord wiki bot]]
- [[things to learn]]
