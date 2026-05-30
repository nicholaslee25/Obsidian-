# Curiosities

**Type:** Topic
**Tags:** #learning #science #curiosities
**Last updated:** 2026-05-30

---

Answers to things worth knowing. Short, dense, no padding.

---

## The Moon — how it works, moves, and looks

An interactive deep-dive by Bartosz Ciechanowski covering the moon's orbit, phases, libration, tides, and more. Live diagrams you can manipulate. One of the best explanations of anything on the internet.

→ [ciechanow.ski/moon](https://ciechanow.ski/moon/)

*(See also: his full archive at [ciechanow.ski/archives](https://ciechanow.ski/archives/) — every article is this good)*

---

## How do batteries charge?

Rechargeable batteries (like lithium-ion) work through reversible electrochemical reactions. During **discharge**, lithium ions migrate from the anode (negative, usually graphite) through the electrolyte to the cathode (positive, usually a metal oxide), releasing electrons that flow through the external circuit as usable current.

**Charging reverses this**: an external voltage source forces the ions back from cathode to anode, restoring the battery's potential energy. The charger must apply a voltage slightly higher than the battery's own to push ions "uphill" against their natural direction.

Degradation over cycles happens because the anode/cathode materials physically expand and contract with ion movement, causing microscopic cracking and loss of capacity over time.

---

## Asbury Revival

In February 2023, a routine chapel service at **Asbury University** in Wilmore, Kentucky simply didn't end. Students stayed. Others came. The service ran continuously for over two weeks, drawing tens of thousands of visitors from around the world.

No organized speakers or events — just sustained worship, prayer, and what participants described as genuine repentance and spiritual presence. No social media campaign started it. It spread by word of mouth and sparked smaller revivals at other universities across the US.

Theologically debated but widely documented. Whether you're a believer or not, the spontaneous and sustained nature of it is historically unusual.

---

## How is FFT used in file compression?

**FFT (Fast Fourier Transform)** converts a signal from the time domain to the frequency domain — it reveals *which frequencies are present* and at what intensities.

In **audio compression (MP3)**:
1. FFT breaks a sound chunk into its frequency components
2. A psychoacoustic model identifies which frequencies humans can't hear well — masked by louder nearby frequencies, or outside audible range
3. Those inaudible components get fewer bits or are discarded entirely
4. Result: smaller file, perceptually similar sound

In **image compression (JPEG)**, the related DCT (Discrete Cosine Transform) does the same thing spatially — it identifies high-frequency detail (sharp edges, fine texture) that the eye tolerates losing, and compresses those aggressively.

The key insight behind both: *you don't need to store what people can't perceive.*

---

## How does a tuned mass damper work?

A **tuned mass damper (TMD)** is a large mass mounted inside a structure (skyscraper, bridge) on springs and dampers, tuned to match the structure's natural resonant frequency.

When wind or an earthquake pushes the structure, it starts oscillating at its natural frequency. The TMD mass — because of its inertia — lags slightly behind the structure's motion. This phase offset means the TMD is always pulling in the *opposite direction* of the structure at any given moment, applying a counterforce that reduces the amplitude of the swing. The dampers dissipate the energy as heat.

The "tuned" part is critical — the spring stiffness is dialed in so the TMD oscillates at exactly the same frequency as the structure. If it's off, it stops canceling effectively.

Famous example: **Taipei 101** has a 660-ton steel pendulum ball suspended near the top. You can watch it move during typhoons.

---

## How does detergent work?

Detergent is a **surfactant** — it lowers the surface tension of water so it can flow between the seams and fibers of clothing more easily. It then suspends dirt, grease, and contaminants into microscopic spheres called **micelles**, which the water carries away when rinsed.

---

## Related

- [[useful websites]]
- [[reading]]
