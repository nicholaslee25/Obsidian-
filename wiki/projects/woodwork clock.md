# Woodwork Clock

**Type:** Project
**Tags:** #project #woodworking #clock
**Status:** Brainstorming
**Last updated:** 2026-05-15

---

## Overview

A handmade 5-inch wooden clock face. The movement is a fully discrete no-microcontroller circuit — every part visible and understandable. 3x AA battery powered.

**Status:** Circuit design phase — want to get this done ASAP.

---

## Circuit Design

Signal chain:
```
32.768kHz crystal → CD4060 (÷2¹⁴ = 2Hz) → 74HC74 flip-flop (÷2 = 1Hz) → DRV8837 driver → stepper motor → clock hands
```

Full build notes are in the active conversation — covering oscillator wiring, flip-flop feedback, DRV8837 hookup, trimmer cap tuning, and power.

**Key flags from circuit review:**
- Crystal must be **12.5pF** (not 6pF) — 2x 22pF load caps are sized for 12.5pF
- XTAL2 needs: fixed 22pF cap + trimmer in parallel (not trimmer alone)
- CD4060 RESET pin (pin 12) must be tied to GND
- Add 100nF decoupling caps on each IC's VCC/GND pins
- SM-5VDC is a 2-coil bipolar stepper — single DRV8837 drives one coil; may need second driver

## Build Path

1. [ ] Research oscillator circuit + finalize schematic (CircuitJS / CircuitLab)
2. [ ] Design verified circuit
3. [ ] Order parts
4. [ ] CAD the clock face + enclosure (for woodworking dimensions)
5. [ ] Breadboard test
6. [ ] PCB or perfboard build
7. [ ] Woodwork the final clock body

## Parts List (Current)

| Part | Value/Model | Notes |
|---|---|---|
| Crystal | 32.768kHz, **12.5pF** | Standard watch crystal |
| Counter IC | CD4060 / 74HC4060 | 14-stage + built-in oscillator |
| Flip-flop IC | 74HC74 | D flip-flop, toggle via D=Q̄ feedback |
| Motor driver | DRV8837 | Tiny H-bridge, SO-8 |
| Stepper motor | SM-5VDC-DRV (Olimex) | Verify single-coil drive works |
| Load caps | 2x 22pF | Crystal load, one per XTAL pin |
| Trimmer cap | 5–30pF | In parallel with fixed cap on XTAL2 |
| Feedback resistor | 10MΩ | Across XTAL1–XTAL2 |
| Decoupling caps | 100nF x3 | One per IC |
| Batteries | 3x AA | 4.5V supply |

## Open Questions

- SM-5VDC single-coil drive: test before committing
- Clock face style: wall or desk? Gift or keeping?
- Wood species TBD

---

## Related

- [[woodwork shelf]]
- [[moon cycle clock]]
- [[goals]]
