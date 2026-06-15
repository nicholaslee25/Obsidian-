# Woodwork Clock

**Type:** Project
**Tags:** #project #woodworking #clock
**Status:** Active — circuit design phase
**Last updated:** 2026-06-14

---

## Overview

A handmade 5-inch wooden clock face. The movement is a fully discrete no-microcontroller circuit — every part visible and understandable. Battery powered.

---

## !! URGENT — Design Before Ordering !!

### Hand Setting Mechanism (clutch)

Need to design this before purchasing parts — it affects the physical shaft layout.

**Concept:** Old-fashioned watch crown. A knob on the back of the clock face connects to the hand shaft. Friction clutch between motor and shaft — enough grip for motor to drive hands normally, but you can overpower it by hand to set the time. Let go, motor takes back over. No electronics involved — purely mechanical.

**DIY options to evaluate:**
- **Knurled knob** press-fit onto extended hand shaft — simplest. Turn it by hand. Motor torque on 28BYJ-48 is low enough that backdriving won't damage it.
- **Allen key socket** (brass sleeve) on the shaft — cleaner, looks intentional, very watchmaker aesthetic
- **Push-pull crown** — push in = motor engaged, pull out = manual mode. More complex but most watch-accurate.

**What needs to be figured out:**
- How long does the shaft need to extend out the back?
- Where does the friction clutch sit relative to the gear train?
- Does the 28BYJ-48 shaft couple directly to the hand shaft, or via gears?
- Hand shaft needs to pass through clock face center — CAD this first

---

## Circuit Design

Signal chain:
```
32.768kHz crystal → CD4060 (÷2¹⁴ = 2Hz) → 74HC74 flip-flop (÷2 = 1Hz) → ULN2003 driver → 28BYJ-48 stepper → clock hands
```

**Key flags:**
- Crystal must be **12.5pF** (not 6pF) — 2x 22pF C0G/NP0 load caps sized for this
- XTAL2: fixed 22pF cap + trimmer in parallel (not trimmer alone)
- CD4060 RESET pin 12 must be tied to GND
- 100nF decoupling caps on each IC VCC/GND pin
- 28BYJ-48 has 2048 steps/rev — at 1Hz (1 step/sec) one full rotation = ~34 min. Map out steps-per-hand-tick before finalising gear coupling

**Drift correction:** trimmer cap (passive, set once) + knob/crown for manual hand adjustment

---

## Parts List

### Need to Buy
| Part | Value/Model | Notes |
|---|---|---|
| Crystal | 32.768kHz, **12.5pF** | Standard watch crystal |
| Counter IC | CD4060 / 74HC4060 | 14-stage divider + built-in oscillator |
| Flip-flop IC | 74HC74 | D flip-flop, ÷2 via D=Q̄ feedback |
| Trimmer cap | 5–30pF | In parallel with fixed cap on XTAL2 for freq tuning |

### Already Have
| Part | Value/Model | Notes |
|---|---|---|
| Stepper motor | 28BYJ-48 (5V or 12V) | Geared, 2048 steps/rev |
| Motor driver | ULN2003 board | Designed for 28BYJ-48, replaces DRV8837 |
| Load caps | 2x 22pF C0G/NP0 ceramic | Crystal load, one per XTAL pin — use C0G/NP0 only (thermally stable) |
| Decoupling caps | 100nF ceramic x3 | One per IC, any ceramic fine |
| Feedback resistor | 10MΩ | Across XTAL1–XTAL2 |
| Batteries | TBD | 3x AA (4.5V) or LiPo + TP4056 USB-C charger |

---

## Build Path

1. [ ] **Design hand-setting clutch mechanism** (do this before ordering — affects shaft layout)
2. [ ] Finalize schematic in CircuitJS / CircuitLab
3. [ ] Order 4 remaining parts
4. [ ] CAD clock face + enclosure
5. [ ] Breadboard test
6. [ ] Perfboard build
7. [ ] Woodwork final clock body

---

## Open Questions

- Clutch design: knob vs allen key vs push-pull crown?
- 28BYJ-48 shaft → hand shaft coupling: direct or geared?
- Clock face style: wall or desk? Gift or keeping?
- Wood species TBD
- Power: 3x AA or USB-C LiPo?

---

## Related

- [[woodwork shelf]]
- [[moon cycle clock]]
- [[goals]]
