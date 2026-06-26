# Game Farming Bot

**Type:** Project
**Tags:** #project #software #automation #gaming
**Status:** Active
**Last updated:** 2026-06-14

---

## Overview

Automate farming in MCOC (Marvel Contest of Champions) using screen capture + mouse control. Script detects game state from screenshots and clicks the right buttons — navigating menus, starting autofight, looping through content.

**Game:** Marvel Contest of Champions (MCOC) — desktop/emulator
**Goal:** Auto-navigate screens to get autoplay running, then let the game handle itself

## Stack

`python
import pyautogui as pag
import os
import numpy as np
import time
`

- **pyautogui** — mouse movement, clicking, screenshots
- **os** — build file paths to reference PNGs
- **numpy** — image array handling (used internally by pyautogui/opencv)
- **time** — delays between actions
- opencv-python installed separately — powers image matching under the hood

## How It Works

1. Screenshot the button/screen element you want to detect → save as .png in project folder
2. pag.locateCenterOnScreen('button.png', confidence=0.8) — finds it on screen, returns (x, y)
3. pag.click(x, y) — clicks it
4. Loop with 	ime.sleep() between checks to wait for next screen

## Key Patterns

`python
# Setup
pag.FAILSAFE = False  # disable corner-kill (re-enable during dev)
current_path = os.path.dirname(__file__)
login_png = os.path.join(current_path, 'login_button.png')

# Find and click
x, y = pag.locateCenterOnScreen(login_png, confidence=0.8)
pag.click(x, y)

# Screen size / mouse pos
pag.size()      # (width, height)
pag.position()  # current mouse (x, y)
`

## confidence param
locateCenterOnScreen('btn.png', confidence=0.8) — 0.8 = 80% match threshold. Lower = more lenient but more false positives. Start at 0.9, lower if not finding it.

## Gotchas

- Reference PNGs must match exact resolution/scale of the game window
- Animations or glowing buttons will break matching — screenshot a static state
- locateCenterOnScreen returns None if not found — add a check or it'll crash on unpack
- pyscreeze, cv2 don't need to be imported — pyautogui uses them internally

## TODO

- [ ] Map out all screens that need navigation (lobby → quest → fight → repeat)
- [ ] Screenshot each button needed as a .png reference
- [ ] Add None-check before clicking (handle screen not found)
- [ ] Add timing logic — some screens load slower than others
- [ ] Loop structure: detect state → act → sleep → repeat

## People

- **Parker** — working on this project, good learning opportunity for programming fundamentals (screen capture, logic flow, timing)

---

## Docs

- [PyAutoGUI Official Docs](https://pyautogui.readthedocs.io/en/latest/)

---

## Related

- [[nfc microcontroller connection]]

