# Symmetrical Gear Arm Gripper

**Type:** Project
**Tags:** #project #mechanical #gripper #robotics #3dprint #gears
**Status:** Brainstorming
**Last updated:** 2026-05-27

---

## Overview

A parallel gripper with symmetrical arms driven by a rack and pinion, actuated by a linear spring on a rod. The spring either pulls or compresses the rack, which drives both arms simultaneously through the pinion — keeping motion perfectly symmetrical.

## Mechanism Breakdown

```
[Spring] — [Rod] — [Rack] — [Pinion] — [Symmetrical Arms]
```

- **Spring + rod** — linear actuator. Spring state (compressed or extended) determines normally-open or normally-closed behavior
- **Rack** — translates linear spring force into motion for the pinion
- **Pinion** — central gear that meshes with the rack; rotation drives both arms equally
- **Symmetrical arms** — linked to the pinion on both sides; always mirror each other, keeping grip centered on the object

## Design Variants

| Configuration | Spring State | Grip Default |
|---|---|---|
| Normally closed | Spring pulls rod inward | Grips at rest, release needs force |
| Normally open | Spring pushes rod outward | Open at rest, grip needs force |

## Key Design Decisions (TBD)

- Arm geometry — straight, curved, or angled fingers?
- Pinion linkage type — direct rack on each arm, or lever arms off the pinion?
- Spring spec — extension vs compression spring, stiffness, travel
- Actuation input — manual trigger, servo, solenoid, or pneumatic?
- Material — 3D printed, machined, or hybrid
- Scale — fingertip gripper or larger?

## Fabrication

Likely 3D printed prototype first. Key parts:
- Rack (linear gear teeth)
- Pinion gear
- Two mirrored arm bodies
- Rod + spring housing/guide
- Frame to hold everything aligned

## Notes

*(add sketches, CAD notes, print iterations, and test results here)*

---

## Related

- [[floating gear]]
- [[hand crank fan]]
- [[zen sand table]]
