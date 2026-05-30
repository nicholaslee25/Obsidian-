# Compass

**Type:** Project
**Tags:** #project #electronics #diy #gps
**Status:** Brainstorming
**Last updated:** 2026-05-15

---

## Overview

A physical DIY GPS-powered compass that points toward a custom fixed destination (configurable coordinates). Not magnetic north — points to wherever you set it.

Inspired by the idea of pointing it at something specific (e.g. the only Olive Garden in NYC), but the actual build is a general-purpose GPS compass.

GPS module reads live location → microcontroller calculates bearing to hardcoded target coordinates → servo drives a physical needle.

## Materials

- GPS module (NEO-6M or NEO-M8N)
- Microcontroller (ESP32 recommended — WiFi/BT capable)
- Servo motor (SG90 for a needle)
- Enclosure (wood, 3D printed, or machined — compass aesthetic)
- Optional: small OLED display for bearing/distance readout
- Power (USB or LiPo battery)
- Wiring

## Progress

Brainstorming

## Notes

*(add session recaps, wiring notes, code progress, and next steps here)*

Open questions:
- Purely mechanical needle or add a small screen?
- Enclosure material?
- Battery portable or desk piece?

---

## Related

- [[moon cycle clock]]
- [[nfc microcontroller connection]]
- [[goals]]
