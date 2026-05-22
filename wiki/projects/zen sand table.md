# Zen Sand Table

**Type:** Project
**Tags:** #project #mechanics #electronics #diy
**Last updated:** 2026-05-20

---

## Concept

Kinetic sand art table. A steel ball sits ON TOP of the sand and is dragged around by a magnet underneath the tray -- leaves trails as it goes. Software-to-motion mapping is 1:1 so pattern generation is essentially free.

Reference product: Lemofuta 20" Automatic Drift Sandscape ($370 -- absurd).

---

## How It Works

1. Sand sits in a shallow tray with a glass cover
2. Steel ball rests on the sand surface
3. Magnet underneath the tray moves on a gantry (likely CoreXY or polar)
4. Ball tracks the magnet and drags a trail through the sand
5. LED ring around the edge for aesthetics

Concealment is a non-problem -- the magnet is just under the tray floor, completely hidden.

---

## Open Problems

- **Actuation** -- CoreXY gantry or polar arm under the tray; both are well-documented (3D printer / Sisyphus table refs)
- **Magnet strength** -- needs to be strong enough to pull the ball consistently through sand without losing tracking; too weak = ball drifts, too strong = drags instead of rolls
- **Sand depth** -- affects how much resistance the ball has; shallower = easier to track but less dramatic trails

---

## Cost Reality Check

Commercial unit is $370. DIY breakdown is probably:
- Stepper motors + drivers
- Belt + gantry hardware
- Strong neodymium magnet
- Tray + glass + sand + LED strip

Should be well under $100 in parts.

---

## Status

Idea / research

---

## Related

- [[floating gear]]
- [[tensegrity table]]
