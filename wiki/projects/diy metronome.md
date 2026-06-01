# DIY Metronome

**Type:** Project
**Tags:** #project #electronics #music
**Status:** Idea — rotary encoder research needed

---

## Overview

Build a DIY metronome with a rotary encoder to set tempo. Learn how rotary encoders work in the process.

## Rotary Encoder Notes

Two main types:

**Mechanical (incremental):**
- Has physical detents that click as you rotate
- Two output signals (A and B) that alternate in a specific pattern depending on rotation direction
- Microcontroller reads the pattern to determine direction and steps
- Common: EC11 style — cheap, tactile, widely used

**Magnetic (Hall effect):**
- Uses small magnets and Hall sensors instead of mechanical contacts
- No wear, more precise
- Small disc magnets: **different polarity on each face (N/S top/bottom) AND opposite polarity on each semi-circle of the edge** — this is how the sensor reads rotation and direction
- Higher quality builds use these

**Attaching an encoder to a shaft:**
- Mechanical encoders: set-screw hub or D-shaft coupling
- Magnetic encoders: mount magnet directly on shaft end, sensor beneath it — no physical contact at all

## Build Components (Rough)

- Rotary encoder (tempo input)
- Microcontroller (Arduino/Teensy) to calculate BPM and generate beat signal
- Buzzer or speaker output
- Optional: display for BPM value

## Notes

*(add schematic, code, build progress here)*

---

## Related

- [[woodwork clock]]
- [[music]]
