# Curiosities

**Type:** Topic
**Tags:** #learning #science #curiosities
**Last updated:** 2026-05-30

---

Answers to things worth knowing. Short, dense, no padding.

---

## What is the efficient compute frontier?

The **efficient compute frontier** (also called the compute-optimal frontier) defines the optimal tradeoff between model size and training data for a given compute budget — the sweet spot where you get maximum performance per FLOP.

The **Chinchilla paper** (DeepMind, 2022) was the landmark finding: previous large language models like GPT-3 were massively *undertrained*. You get better performance per compute dollar by training a **smaller model on significantly more data** rather than a huge model on less. The frontier is a curve — for any compute budget, there's an ideal (model size, training tokens) pair.

Practically: instead of "make the model bigger," the answer is often "train longer on more data."

---

## How is data stored?

You're right — flip-flops and transistors are the core.

- **SRAM (cache):** 6 transistors per bit forming a bistable latch (flip-flop). Holds state as long as powered. Fast but expensive and power-hungry. Used in CPU cache.
- **DRAM (RAM):** 1 transistor + 1 capacitor per bit. The capacitor holds charge = 1, no charge = 0. Must be refreshed thousands of times per second because capacitors leak. Slower than SRAM, much denser.
- **NAND Flash (SSDs):** Floating gate transistors — electrons are trapped in an insulated gate region. The charge persists without power. Slower to write, limited write cycles, but non-volatile.
- **HDD:** Magnetic domains on a spinning platter. A read/write head magnetizes tiny regions. Purely mechanical — slowest, most fragile, still cheapest per GB.

The transistor count is the core tradeoff: more transistors = faster + more reliable, fewer = cheaper + denser.

---

## What is LiDAR? How does it compare to Tesla's camera vision?

**LiDAR (Light Detection and Ranging):** Fires pulses of laser light and measures the time-of-return to build a precise 3D point cloud of the environment. Direct, ground-truth range measurement. Works in low light. Expensive. Used by Waymo, most robotaxis.

**Tesla's approach (camera-only vision):** Uses ~8 cameras and neural networks to infer 3D depth from 2D images — similar to how humans use two eyes for stereo depth perception. No dedicated range sensor. Much cheaper. Relies entirely on AI to reconstruct 3D geometry.

The "stereo/multi-point imaging" you're thinking of: **stereo vision** uses 2 cameras with a known baseline — disparity between the two images encodes depth geometrically. More cameras add coverage and redundancy.

**The debate:**
- LiDAR gives raw, reliable distance data regardless of AI quality
- Tesla argues humans drive with eyes alone, so cameras should suffice — and that LiDAR is a crutch masking poor AI
- Critics argue edge cases (sensor occlusion, adversarial conditions) expose the camera-only approach's fragility

---

## What is resonant frequency — why does amplitude spike there?

Every object has a **natural frequency** — determined by its stiffness and mass (like a spring-mass system: f = 1/2π × √(k/m)). At rest, it wants to oscillate at that frequency.

When you apply a periodic driving force **at that exact frequency**, each cycle adds energy *in phase* with the existing motion. The system can't dissipate energy fast enough through damping, so amplitude grows — sometimes catastrophically (see: Tacoma Narrows Bridge).

At other frequencies, the driving force is sometimes in-phase and sometimes out-of-phase, so net energy input averages out.

**Why amplitude varies by material:** The peak amplitude at resonance is governed by the **damping ratio** — how much energy the material dissipates per cycle. Steel (low damping) rings hard and long. Rubber (high damping) absorbs energy fast. This is why some materials are used for vibration isolation and others aren't.

---

## What is Secure Boot and TPM?

**TPM (Trusted Platform Module):** A dedicated security chip on the motherboard. Stores cryptographic keys in tamper-resistant hardware. Also performs **measured boot** — it hashes each component of the boot process and logs them, creating a chain of trust you can verify later.

**Secure Boot:** A UEFI/BIOS feature that checks the cryptographic signature of every bootloader before running it. Only code signed by a trusted key (stored in firmware) is allowed to execute. Blocks rootkits and bootkits from hijacking the boot process.

**Together:** TPM holds the keys Secure Boot uses to verify signatures. If anything in the boot chain is tampered with, the TPM's measurements won't match, and the system knows it's been compromised. BitLocker uses the TPM to detect if the boot environment changed and will lock the drive if so.

---

## Stroke vs. cylinder in cars

**Cylinder:** The chamber where combustion happens. More cylinders = smoother power delivery (more firing events per revolution), more total displacement capacity. V8 > I6 > I4 in smoothness.

**Stroke:** The distance the piston travels from top dead center (TDC) to bottom dead center (BDC). Longer stroke = more torque, lower RPM powerband — better for towing, lugging. Shorter stroke = higher RPM ceiling, more power at high revs — better for performance engines.

**Engine displacement** = bore area × stroke × cylinder count. That's the "2.0L" or "5.7L" figure.

The 4 strokes of a 4-stroke cycle (separate concept, same word): **intake → compression → combustion (power) → exhaust.** Two-stroke engines skip separate intake/exhaust strokes — fire every revolution, lighter and simpler, but less efficient and dirtier.

---

## Why does fishing line weight matter? Is 60lb impressive?

**Line weight (lb test):** The force at which the line is rated to break under sustained tension. 60lb test = breaks at ~60 lbs of pull.

Heavier line for: larger fish, heavier lures, rocky/abrasive environments, saltwater. Lighter line for: smaller fish, clearer water (less visible = more bites), longer casts (less wind resistance), finesse techniques.

**Is 60lb impressive?** Totally context-dependent:
- Bass fishing: massive overkill — typical is 8–17lb
- Offshore saltwater (tuna, mahi): normal to moderate
- Heavy shark/billfish: might be light
- Ice fishing panfish: 60lb is absurd

Line type also matters: **monofilament** (stretchy, forgiving), **fluorocarbon** (invisible underwater, sinks, low stretch), **braid** (no stretch, thin diameter, very strong — 60lb braid is thin as 15lb mono).

---

## 1MDB Controversy

One of the largest financial frauds in history. **1Malaysia Development Berhad (1MDB)** was a Malaysian state investment fund established in 2009 by PM Najib Razak.

Over **$4.5 billion** was embezzled through a network involving Najib Razak, fugitive financier **Jho Low**, and Goldman Sachs bankers. The scheme worked by:
1. Goldman Sachs raised billions in bonds for 1MDB
2. The money flowed through layers of shell companies across multiple countries
3. It was used to buy luxury real estate in NYC/LA/London, a $250M superyacht, Picasso paintings, and to **fund the film *The Wolf of Wall Street*** (the irony)

**Goldman Sachs** paid a $2.9 billion settlement. **Najib Razak** was convicted of corruption and sentenced to 12 years. **Jho Low** remains a fugitive, believed to be in China.

The case exposed how international financial systems, offshore shell companies, and correspondent banking could be exploited at a sovereign level for years before anyone caught it.

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
