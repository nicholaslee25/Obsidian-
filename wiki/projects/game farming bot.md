# Game Farming Bot

**Type:** Project
**Tags:** #project #software #automation #gaming
**Status:** Planning
**Last updated:** 2026-05-27

---

## Overview

Automate farming in a game using screen capture + mouse/keyboard control. Claude reads the game state from screenshots and executes actions — grinding resources, repeating loops, whatever the farm requires.

**Game:** Marvel Contest of Champions (MCOC)

## Approach

Depends on game type:
- **Browser game** → Claude in Chrome MCP (simplest, no extra setup)
- **Desktop game** → PyAutoGUI (Python: screenshot + mouse/keyboard input)
- **Needs fast timing** → AutoHotKey (Windows-native, low latency)

## Components

1. **Screen capture** — screenshot the game window or region
2. **State detection** — read what's on screen (pixel color, image match, or OCR)
3. **Action logic** — decide what to click/press based on state
4. **Loop** — repeat until farm is done or interrupted

## Progress

Planning — game TBD

## Open Questions

- Which game?
- Browser or desktop?
- What exactly is being farmed (resources, XP, items)?
- Any anti-bot detection to work around?

## Notes

*(add game details, farming logic, script progress here)*

---

## Related

- [[nfc microcontroller connection]]
