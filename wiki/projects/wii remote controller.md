# Wii Remote → Pi/ESP32 Controller

**Type:** Project
**Tags:** #project #electronics #retro
**Last updated:** 2026-07-25

---

## Concept

Use a Wii remote (Bluetooth + accelerometer + IR) as an input controller for a Raspberry Pi or ESP32 project — repurpose old hardware as a gesture/motion controller.

## Open Questions

- Wiimote connects over Bluetooth HID — Pi has native BT, ESP32 needs a BT-capable variant (ESP32 classic supports BT Classic; check library support for Wiimote pairing)
- What's actually being controlled? No target project yet — this could drive the [[zen sand table]], [[symmetrical gear arm gripper]], or something new
- Library: `cwiid` (Linux Wiimote lib) is the standard starting point on Pi

## Notes

*(pick a target application before starting — this is currently a solution looking for a problem)*

---

## Related

- [[zen sand table]]
- [[mechatronics beginner]]
