# Google Home Mini × Arduino

**Type:** Project
**Tags:** #project #electronics #smart-home
**Last updated:** 2026-07-25

---

## Concept

Connect a Google Home Mini to an Arduino so voice commands can trigger physical hardware — lights, motors, relays, whatever's on the other end.

## Open Questions

- Path is almost certainly IFTTT or Google Assistant SDK → webhook → a WiFi-capable board (ESP8266/ESP32) listening for the trigger, rather than the Arduino talking to the Mini directly
- Plain Arduino (Uno/Nano) has no WiFi — would need an ESP add-on or just use an ESP32 outright
- What's the actual thing being triggered? No target action defined yet

## Notes

*(overlaps a lot with [[raspberry pi ai assistant]] — Le'bama already solves "voice → action," just via a different mic input. Worth comparing before building a separate pipeline.)*

---

## Related

- [[raspberry pi ai assistant]]
- [[nfc wifi connection]]
