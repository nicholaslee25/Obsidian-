# Discord Wiki Bot

**Type:** Project
**Tags:** #project #software #discord #bot #wiki
**Status:** Planning
**Last updated:** 2026-05-27

---

## Overview

A Discord bot that acts as a wiki assistant — ask it questions in Discord, it reads the 空心菜 wiki and answers using the relevant pages. Powered by the Claude API.

Goal: access the second brain from anywhere, especially phone.

## Stack

- **Language:** Python or Node.js (TBD)
- **Discord library:** discord.py or discord.js
- **LLM:** Claude API (Anthropic SDK)
- **Wiki source:** local `.md` files in `空心菜/wiki/`
- **Hosting:** local machine (laptop must be running) or small server for always-on

## How It Works

1. User sends a message or slash command in Discord
2. Bot reads relevant wiki pages (index.md → route to specific pages)
3. Passes wiki content + question to Claude API
4. Returns response in Discord

## Progress

Planning — not started

## Open Questions

- Python or Node.js?
- Always-on (hosted) or local-only?
- Slash commands or natural language messages?
- Which Discord server / channel?

## Notes

*(add dev progress, decisions, and issues here)*

---

## Related

- [[index]]
- [[overview]]
