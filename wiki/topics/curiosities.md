# Curiosities

**Type:** Topic
**Tags:** #learning #science #curiosities
**Last updated:** 2026-05-30

---

Answers to things worth knowing. Short, dense, no padding.

---

## What is tilt-shift photography?

**Tilt-shift** is a technique that makes real scenes look like miniature models. Achieved two ways:

1. **Tilt-shift lens** (physical): the lens plane tilts relative to the image sensor, exploiting the **Scheimpflug principle** — the plane of focus rotates, creating an extremely narrow band of sharpness across the scene instead of a flat plane parallel to the sensor. Everything outside that band goes soft.
2. **Post-processing**: selectively blur the top and bottom of an image to simulate the same effect.

Why it looks like a miniature: our brains associate very shallow depth of field with close-up macro photography. When applied to a wide scene (a city, a stadium, a crowd from above), the brain reads it as a tiny physical model being photographed up close. The perspective compression from a high shooting angle amplifies the illusion.

---

## What is the Fibonacci sequence in stock charts?

The **Fibonacci sequence** (0, 1, 1, 2, 3, 5, 8, 13, 21...) produces ratios that converge on the **golden ratio (φ ≈ 1.618)**. The key ratios used in trading: **23.6%, 38.2%, 50%, 61.8%, 78.6%** (retracements) and **127.2%, 161.8%, 261.8%** (extensions).

**How it's used:**
- Identify a significant price move (swing low → swing high, or vice versa)
- Draw horizontal lines at the Fibonacci ratios between those two points
- Those levels are treated as potential **support and resistance** — areas where price might pause, bounce, or reverse during a pullback

**What they show:** After a trend, price rarely goes straight back. Fib levels mark the common "resting points" where buyers or sellers step back in. The 38.2% and 61.8% levels are watched most closely.

**Caveat:** Effectiveness is debated. Part of why they "work" is self-fulfilling — enough traders watch the same levels that they become real by collective action. Not a guarantee, but widely embedded in technical analysis toolkits.

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

---

## What is a device driver?

Software that acts as a **translator between the OS and a hardware device**. Hardware speaks its own protocol; the OS speaks in generic terms ("print this"). The driver bridges the two — it knows the specific commands that printer, GPU, or USB chip actually understands. When something works plug-and-play, it's because a driver was either pre-installed or fetched automatically. When it doesn't, you go find the driver manually.

---

## Biphasic vs. monophasic defibrillator shocks

**Monophasic:** current flows in one direction only. Requires higher energy (~360J). More myocardial damage. Older technology.

**Biphasic:** current flows in one direction, then reverses — two phases. More effective at lower energy (~150–200J). Less tissue damage. Standard in all modern AEDs and hospital defibrillators.

Why it's better: the biphasic waveform more closely matches the heart's own action potential, depolarizing the entire myocardium more effectively without frying it.

---

## Most common and useful CS algorithms

| Algorithm | What it does | Useful to you? |
|---|---|---|
| Binary search | Find item in sorted list in O(log n) | Yes — anytime you search |
| BFS / DFS | Traverse graphs and trees | Yes — pathfinding, state machines |
| Dijkstra's | Shortest path in a weighted graph | Yes — compass, routing |
| A\* | Like Dijkstra but with a heuristic (faster) | Yes — robotics, zen sand table |
| QuickSort / MergeSort | Sort a list efficiently | Background knowledge |
| Dynamic programming | Solve complex problems by breaking into subproblems | Yes — optimization |
| Hashing | O(1) lookup via hash map | Yes — game bot state tracking |
| Flood fill | Fill connected region (like paint bucket) | Yes — game bot screen detection |

---

## How to fix ghost scrolling on a mouse

Scroll wheel ghosts because dust and debris interrupt the optical sensor or mechanical encoder inside the wheel. **Fix: take apart the mouse, blow out the scroll wheel assembly with compressed air.** Usually 100% effective. No disassembly required on most mice — just a can of air aimed at the scroll wheel gap.

---

## How to fix a leak in a pipe

| Leak type | Temp fix | Permanent fix |
|---|---|---|
| Pinhole or hairline crack | Epoxy putty stick, pipe repair clamp, or rubber sleeve + clamp | Cut out bad section, replace with new pipe + couplings |
| Joint leak | PTFE tape (thread joints) or pipe joint compound | Disassemble and re-tape/re-seal |
| Small crack | Plumber's epoxy over cleaned dry surface | Replace section |

Don't use electrical tape — it fails under water pressure. Epoxy or a proper clamp only for emergency fixes.

---

## How do hydrofoil boards work?

A hydrofoil board has a **wing-like foil mounted on a strut below the hull**. At low speed, the board sits on the water surface. As speed increases, the foil generates **lift** (same principle as an airplane wing — faster flow over the top surface creates lower pressure, slower flow below creates higher pressure → net upward force). Once lift exceeds the board's weight, it rises completely out of the water. With no hull drag, it's faster and smoother. The rider shifts their weight to control pitch; the foil shape controls stall speed and max lift.

---

## Geneva mechanism — what it is and the design equations

A Geneva mechanism converts **continuous rotation into intermittent rotation** (step-pause-step-pause). Used in film projectors, watches, indexing machines.

**How it works:** A driving wheel with a pin engages slots in the driven wheel, rotating it one step, then a locking arc holds it stationary until the next pin engagement.

**Key equations:**

Number of slots: **n** (minimum 3, most common is 4)

Rotation per step: **360° / n**

Half the angle between slots: **α = 180° / n**

Distance between wheel centers: **d = r / sin(α)** where r = driving pin radius from center

Locking arc half-angle: **β = 90° − α**

With n=4: each step = 90°, α = 45°, β = 45°. Clean and symmetric — that's why it's the most common.

---

## How was 3-phase power discovered? Why is it so much better?

**Discovered:** Nikola Tesla (1887–1888), independently around the same time by Mikhail Dolivo-Dobrovolsky (who built the first 3-phase power transmission system in 1891).

**Why 3 phases are so much better:**
1. **Continuous power delivery** — 3 phases offset 120° apart = power is never zero. One phase is always near peak.
2. **Less wire for the same power** — 3 phases share a neutral; balanced loads don't need a neutral at all. 75% of the copper cost of single-phase for the same power.
3. **Rotating magnetic fields** — 3-phase naturally produces a smoothly rotating field. This is exactly what an AC induction motor needs to spin — no extra components required.
4. **No torque ripple** — single-phase motors pulse; 3-phase motors run smoothly.
5. **Efficient long-distance transmission** — higher voltage, lower current, less heat loss in wires.

---

## What is impedance (vs. resistance)?

**Resistance (R):** Opposition to current in a DC circuit. Fixed value. Dissipates energy as heat. Ohm's law: V = IR.

**Impedance (Z):** Opposition to current in an AC circuit. Combines resistance AND **reactance** (opposition from capacitors and inductors). Z = √(R² + X²). Measured in ohms.

**Reactance (X):**
- Capacitors block DC, pass AC. Reactance decreases as frequency increases: **Xc = 1 / (2πfC)**
- Inductors pass DC, block AC. Reactance increases with frequency: **Xl = 2πfL**

Why it matters: speaker impedance (4Ω, 8Ω) tells the amp how "hard" it has to work. Impedance matching maximizes power transfer in RF and audio circuits.

---

## Reynolds, Prandtl, and Nusselt numbers

Dimensionless numbers used in heat transfer and fluid mechanics to describe flow behavior without needing units.

**Reynolds number (Re):** Ratio of inertial forces to viscous forces.
- Re < 2,300 → laminar flow (smooth, layered)
- Re > 4,000 → turbulent flow (chaotic, mixing)
- Formula: Re = ρVL / μ (density × velocity × length / dynamic viscosity)

**Prandtl number (Pr):** Ratio of momentum diffusivity to thermal diffusivity.
- Low Pr (liquid metals): heat spreads faster than momentum → thin thermal boundary layers
- High Pr (oils): momentum spreads faster → thick thermal boundary layers
- Water ≈ 7, air ≈ 0.7

**Nusselt number (Nu):** Dimensionless convective heat transfer coefficient.
- Nu = 1 → pure conduction
- Higher → convection is dominant
- Used to calculate actual heat transfer rate: h = Nu × k / L

Together: Re tells you if flow is turbulent (affects Nu), Pr tells you the fluid's thermal behavior, Nu gives you the actual heat transfer coefficient.

---

## Newtonian vs. non-Newtonian fluids / compressible vs. incompressible

**Newtonian:** Viscosity is constant regardless of shear rate. Water, air, most oils. V = IR equivalent — consistent behavior.

**Non-Newtonian:**
- *Shear thinning (pseudoplastic):* gets less viscous under stress. Ketchup, blood, nail polish, paint.
- *Shear thickening (dilatant):* gets more viscous under stress. Cornstarch + water (oobleck), quicksand-like.
- *Bingham plastic:* acts solid until yield stress is met, then flows. Toothpaste, mayonnaise, concrete.

**Compressible:** Density changes significantly with pressure. Gases at high speed (approaching Mach 1+). Matters for aerodynamics, nozzles, shock waves. Requires more complex equations.

**Incompressible:** Density stays constant. Liquids and slow-moving gases (most engineering fluid problems). Simplifies math significantly.

---

## Vacuum physics

| Vacuum level | Pressure | Behavior |
|---|---|---|
| Low vacuum | > 1 mbar | Still lots of molecules. Behaves roughly like air. Roughing pump sufficient. |
| Medium vacuum | 1–10⁻³ mbar | Mean free path grows; molecules start hitting walls more than each other |
| High vacuum | < 10⁻³ mbar | Molecules mostly hit walls. Thermal conductivity near zero. Turbopump needed. |
| Ultra-high vacuum | < 10⁻⁷ mbar | Near-space conditions. Particle accelerators, surface science. Requires bakeout. |

**Temperature:** Lower temp = lower molecular kinetic energy = lower vapor pressure = easier to pump down. Cryogenic traps help pumps by freezing out remaining gas molecules.

**Pump staging:** Single pump types rarely cover the full range. Roughing pump first (atm → ~1 mbar), then diffusion or turbomolecular pump for high vacuum.

**Container material:** Outgassing is the enemy. Absorbed water and gases slowly release from surfaces into the vacuum. Stainless steel outgasses less than plastics. Baking the chamber at 150–200°C drives out surface water before pumping down.

---

## Gauss' collective works

**Carl Friedrich Gauss (1777–1855)** — called the "Prince of Mathematics." One of the most prolific mathematicians in history, often working independently before others knew fields existed.

Major contributions:
- **Number theory** — *Disquisitiones Arithmeticae* (1801), still a foundational text
- **Gaussian distribution** (normal curve) — the bell curve used everywhere in statistics
- **Gauss's law** — one of Maxwell's four equations; describes electric fields from charge distributions
- **Differential geometry** — *Theorema Egregium*: intrinsic curvature of a surface exists independently of how it's embedded in space
- **Celestial mechanics** — calculated the orbit of Ceres from limited observations in 1801, to everyone's amazement
- **Complex numbers** — proved the fundamental theorem of algebra (every polynomial has a root in complex numbers)
- **Non-Euclidean geometry** — developed privately, never published (feared controversy). Influenced Bolyai and Lobachevsky
- **Geomagnetism** — devised methods for mapping Earth's magnetic field; the unit of magnetic flux density (Gauss) is named for him

---

## How to build non-lethal weapons (capacitor gun context)

A **capacitor discharge gun / Gauss gun / coilgun** fires a ferromagnetic projectile using a magnetic pulse from a rapidly discharged capacitor bank.

Basic principle:
1. Charge a capacitor bank to high voltage
2. Discharge through a coil around the barrel
3. Magnetic pulse accelerates a steel projectile down the tube

**"Firing a blank"** = discharge with no projectile → loud pop, spark, no projectile.

⚠️ **Important safety note:** The capacitor bank is genuinely dangerous even when "firing blanks." High-voltage capacitors (>50V) can kill. Always add a bleeder/discharge resistor circuit so the caps fully discharge when not in use. The gun fires blanks; the electronics can still hurt you.

Non-lethal designation applies to the projectile velocity, not the electronics.

---

## What is Travis picking?

A fingerpicking guitar technique developed by Merle Travis, popularized by Chet Atkins.

**How it works:**
- Thumb alternates between bass strings (usually the root and fifth of the chord) on beats 1 and 3 — this is the "boom-chick" pattern
- Fingers pick melody and inner notes on the off-beats (2 and 4) simultaneously
- Creates the illusion of two guitarists playing at once: bass line + melody

**Why it's cool:** Self-accompaniment — you're playing rhythm and lead at the same time. Foundational to country, folk, and fingerstyle guitar.

Songs that use it: *Freight Train* (Elizabeth Cotten), *Wildwood Flower*, most Chet Atkins material, *The Boxer* (Simon & Garfunkel fingerpicking sections).

---

## Tech — Tinkering (Components to Consider Buying)

Hardware worth knowing about and potentially getting for projects:

| Component | What it is | Why interesting |
|---|---|---|
| **Teensy 4.0 / 4.1** | High-performance ARM microcontroller (600MHz). More powerful than Arduino. USB-native, small form factor. | Great for projects needing speed: audio processing, fast PWM, high-frequency control. Better than Arduino for most DIY electronics. |
| **WiFi module (ESP8266 / ESP32)** | Microcontroller with built-in WiFi (and BT on ESP32). Much cheaper than adding a shield to Arduino. | Moon clock WiFi sync, NFC WiFi project, any connected device. The ESP32 is practically the default MCU for connected projects now. |

---

## Related

- [[useful websites]]
- [[reading]]
- [[things to learn]]
