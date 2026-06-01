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

## Uses of a planetary gear system

A planetary gearset has three parts: **sun gear** (center), **planet gears** (orbit the sun), **ring gear** (outer, internal teeth), and a **carrier** (holds the planets). What makes it powerful: you can fix any one part and get different ratios from the same hardware.

| Fix this | Input | Output | Effect |
|---|---|---|---|
| Ring gear | Sun | Carrier | Speed reduction (most common) |
| Carrier | Sun | Ring | High-speed increase |
| Sun | Ring | Carrier | Reverse reduction |

**Why it's compact:** Multiple planet gears share the load simultaneously — much higher torque density than a standard spur gear train of the same volume.

**Uses:**
- **Power tools** — every cordless drill has a planetary gearbox inside (that's the satisfying "click" when you change torque settings)
- **Automatic transmissions** — combine multiple planetary sets for multiple gear ratios
- **Electric motors** — planetary reducer + motor = compact high-torque actuator
- **Robotic joints** — combined with cycloidal or harmonic drive concepts
- **Bicycle hubs** — internally-geared hubs use planetary sets

**Project potential:** 3D printable. Add a DC motor to the sun gear, fix the ring, get output at the carrier. Cheap, compact, high torque. Good first gearbox build.

---

## Battery Management Systems (BMS)

The circuit that makes a lithium battery pack safe. Without it, Li-ion cells are fire hazards — they cannot be left unprotected.

**What a BMS does:**

| Function | Why it matters |
|---|---|
| **Overvoltage protection** | Li-ion cells max out at ~4.2V. Above that → thermal runaway (fire) |
| **Undervoltage protection** | Below ~2.5–3V → permanent capacity damage |
| **Overcurrent / short circuit** | Cuts power instantly if current spikes |
| **Temperature monitoring** | Stops charge/discharge if too hot or cold |
| **Cell balancing** | In series packs, individual cells drift apart in voltage over time — BMS equalizes them |

**Cell balancing types:**
- *Passive balancing:* bleeds excess charge from high cells as heat via resistors. Simple, cheap, wastes energy.
- *Active balancing:* transfers charge from high cells to low cells. More efficient, more complex.

**Key ICs:** BQ76940 (TI, up to 15S), BQ29700, or integrated "protection IC + FET" packages for simple single-cell builds.

**Connects to:** [[diy battery charger]] project.

---

## Unipolar vs. bipolar stepper motors

Both are stepper motors — both step in discrete increments by energizing coils in sequence.

| | Bipolar | Unipolar |
|---|---|---|
| Wires | 4 (two coils) | 5 or 6 (coils with center tap) |
| How current works | Reverses direction through each coil | Only one half of coil energized at a time |
| Driver needed | H-bridge (e.g., DRV8837, A4988) | Simple switches — no H-bridge needed |
| Torque | Higher — full coil used | Lower — only half coil active |
| Complexity | Slightly more complex driver | Simpler driver |
| Modern use | Preferred for almost everything | Legacy; hobbyist simplicity use case |

**Why bipolar wins in practice:** H-bridge ICs are cheap and widely available. The torque advantage is significant. Your SM-5VDC and most stepper motors you'll encounter are bipolar.

**Unipolar use case:** When you really need the simplest possible driver and torque doesn't matter.

---

## Internal cycloidal robotic actuator

A compact robotic joint that integrates a **cycloidal drive + motor (+ sometimes encoder)** into a single coaxial unit. The direction robotics is heading.

**Why it's interesting:**
- Cycloidal reduction gives very high torque density — a small motor outputs huge torque
- Near-zero backlash — critical for precise robot arm positioning
- **Backdrivable** — the joint can be moved by external force (safe for collaborative robots and compliant manipulation)
- All in one: motor + reducer + output bearing in a hockey-puck-sized unit

**Real examples:**
- MIT Mini Cheetah actuator — open-source, 3D printed + machined
- Mjbots moteus — open-source brushless driver + actuator platform
- T-Motor AK series — commercial, widely used in research arms

**To build one:**
- BLDC motor (outrunner style preferred for torque) + cycloidal disc + output bearing
- See [[cycloidal drive vs. harmonic drive]] for the disc geometry
- Control with FOC (field-oriented control) driver — mjbots moteus or ODrive
- Parametric CAD: design disc in Fusion 360 using cycloidal equations, then machine or print

**Connects to:** [[mechatronics beginner]], [[symmetrical gear arm gripper]]

---

## Brush vs. brushless motors

**Brushed DC motor:**
Current flows through physical **brushes** (carbon contacts) that rub against a **commutator** ring on the rotating shaft. This mechanically switches which coils get powered as the motor turns, creating a rotating magnetic field. Simple, cheap, no controller needed — connect to power and it spins. Downside: brushes wear out, create electrical noise and sparks, have friction losses.

**Brushless DC motor (BLDC):**
No physical contact. Permanent magnets on the rotor; coils on the stator. An **electronic speed controller (ESC)** senses rotor position (via Hall sensors or back-EMF) and switches current to the correct coils in sequence. No wear, more efficient, more power-dense, quieter, longer lifespan. Requires a controller — won't run from raw DC.

| | Brushed | Brushless |
|---|---|---|
| Controller needed | No | Yes (ESC) |
| Efficiency | Lower (~75–80%) | Higher (~85–95%) |
| Lifespan | Limited by brush wear | Much longer |
| Cost | Cheaper | More expensive |
| Noise | More electrical noise | Less |
| Best for | Simple toys, low-cost builds | Drones, RC cars, CNC spindles, power tools |

---

## (Re)learning math: Chain rule, parametric chain rule, and the Jacobian

**Chain rule (derivatives):**
> d/dx[f(g(x))] = f'(g(x)) · g'(x) — "derivative of outside × derivative of inside"

Example: d/dx[sin(x²)] = cos(x²) · 2x

**Integration version (u-substitution):**
∫f(g(x)) · g'(x) dx = F(g(x)) + C
Let u = g(x), du = g'(x)dx → transforms the integral to ∫f(u)du which is often easier to solve.

**Parametric chain rule:**
If x = x(t) and y = y(t), then: **dy/dx = (dy/dt) / (dx/dt)**

Useful when a curve is defined by a parameter (like time) rather than directly as y = f(x).

**Jacobian:**
When you have a multi-variable transformation — e.g., (u, v) → (x, y) — the Jacobian is the **matrix of all partial derivatives**:

```
J = | ∂x/∂u   ∂x/∂v |
    | ∂y/∂u   ∂y/∂v |
```

**det(J)** = the "stretching factor" — how area (or volume in 3D) scales under that transformation. Used in change-of-variables for multi-variable integrals: ∬f(x,y) dx dy = ∬f(x(u,v), y(u,v)) |det(J)| du dv

Intuition: if a transformation squishes area by half, det(J) = 0.5. If it flips orientation, det(J) is negative.

Visual reference: [Visualizing Chain Rule and Product Rule](https://www.youtube.com/watch?v=YG15m2VwSjA)

---

## ISO/IEC 17025 — Lab accreditation standard

**ISO/IEC 17025** is the international standard for the **competence of testing and calibration laboratories**. A lab accredited to 17025 has been independently verified to produce technically valid results.

Covers:
- Management requirements (quality system, document control, handling complaints)
- Technical requirements (equipment calibration, measurement uncertainty, staff competence, test methods)
- Impartiality requirements (no conflicts of interest)

Why it matters: regulators (FDA, EPA, government bodies) and customers trust 17025-accredited results as audit-ready. Required for labs that serve aerospace, medical devices, food safety, environmental testing, and similar fields. The audit body is typically a national accreditation body (A2LA in the US, UKAS in the UK).

---

## Benefits of engineering consulting

Instead of working for one company, a consultant is hired by many — project to project.

| Benefit | What it means |
|---|---|
| Higher hourly rate | Clients pay a premium for specialized expertise on-demand — often 2–3× employee rate |
| Variety | New problems, industries, and teams constantly |
| Flexibility | Set your own schedule, choose your clients |
| Independence | You own your work style and tools |
| Skill premium | Niche expertise (FEA, controls, electronics) commands higher rates than generalist roles |
| Tax advantages | Business expenses are deductible as a self-employed consultant |

**Tradeoffs:** No benefits (health insurance, 401k, paid leave). Income is variable and requires client acquisition. Can be isolating. Works best when you have a reputation or niche.

**Path:** Usually people consult after building 5–10 years of credibility as an employee first — then leverage that network.

---

## What are stock options? (Full explanation)

You know the basics — here's the full picture.

**A call option** = the right (not obligation) to **buy** 100 shares at the **strike price** before **expiration**.
**A put option** = the right to **sell** 100 shares at the strike price.

You pay a **premium** (price per share × 100) to own this right. If you don't exercise it, you lose the premium. That's the max loss for a buyer.

---

**What makes up the option price (the premium)?**

Three components:

1. **Intrinsic value** — how "in the money" is it right now?
   - Call with strike $50, stock at $55 → intrinsic value = $5/share
   - Out of the money = zero intrinsic value

2. **Time value (Theta decay)** — more time until expiration = more opportunity = more premium
   - Time value bleeds away every day, accelerating near expiration
   - Theta is the "decay" per day. Sellers love theta; buyers hate it.

3. **Implied volatility (IV) / Vega** — this is your "steepness" intuition
   - IV is the market's expectation of future price movement
   - High IV = bigger expected swings = higher premium, even far from the money
   - A stock moving 5%/day has high IV → options are expensive
   - You can profit from IV changes even if the stock barely moves (IV crush after earnings)

---

**The Greeks (how option prices move):**

| Greek | What it measures |
|---|---|
| **Delta** (Δ) | How much option price moves per $1 stock move. 0.5 delta = option gains $0.50 per $1 stock rise |
| **Theta** (Θ) | Time decay per day (negative for buyers) |
| **Vega** (ν) | Sensitivity to implied volatility changes |
| **Gamma** (Γ) | Rate of change of delta — how fast delta accelerates as price moves toward strike |

**Why people sell options:** Collect premium, profit from time decay (theta positive). But risk is theoretically unlimited on a naked call.

**Why you can't always exercise:** Contracts require buying 100 shares at strike — if strike = $200, that's $20,000. Most retail traders don't have that. So they sell the contract itself when it has value, rather than exercising it.

---

## What are the best future investments? (Post-COVID landscape)

Not financial advice — patterns worth knowing:

| Theme | Why | Examples |
|---|---|---|
| AI & semiconductors | AI is a generational infrastructure build. Chips are the bottleneck. | NVDA, TSM, AMD, ASML |
| Energy transition | Massive capital flowing into solar, wind, grid infrastructure by policy mandate | NEE, ENPH, grid hardware ETFs |
| Copper & critical minerals | EVs, grid expansion, and data centers all need copper. Supply constrained. | FCX, copper ETFs, lithium miners |
| India / Southeast Asia | Demographic growth + manufacturing shift from China | VWO, INDA, country-specific ETFs |
| Healthcare / biotech | Aging populations + AI-accelerated drug discovery | XBI, specific biotech if you research |
| Defense | Geopolitical reality post-Ukraine/Taiwan tension | RTX, LMT, defense ETFs |
| Real estate (selectively) | Long-term still appreciates in supply-constrained cities | REITs or direct if you can |

**Post-COVID specific:** Rates rose sharply → bonds and cash are finally viable (CDs, T-bills, HYSA) for the first time in 15 years. Don't ignore the risk-free rate when comparing to equities.

---

## How to build a to-do list (as a project)

Core architecture is simple. Stack depends on how far you want to take it.

**Minimal version (CLI or local app):**
- Text file or SQLite database (zero setup)
- Python script: add task, list tasks, mark done, delete
- ~50 lines of code. Teaches file I/O or basic SQL.

**Web version:**
- Backend: Flask or FastAPI (Python) — REST API with endpoints: GET /tasks, POST /tasks, PATCH /tasks/:id, DELETE /tasks/:id
- Database: SQLite → PostgreSQL when you need scale
- Frontend: plain HTML/JS fetch calls, or React if you want to practice

**Features to add progressively:**
1. Title, done/not-done
2. Priority level, category/tag
3. Due date
4. Recurring tasks
5. Notes per task
6. Sync across devices (requires server/cloud DB)

Good first real project — teaches CRUD, REST, and database fundamentals end-to-end.

---

## What is JDK 17?

**JDK** = Java Development Kit — everything you need to develop and run Java programs: the compiler (javac), the JVM (runs bytecode), standard libraries, and development tools.

**Version 17** is an **LTS (Long-Term Support)** release (2021). LTS versions receive security and stability updates for years — production systems standardize on them.

**JDK vs JRE vs JVM:**
- **JVM** — Java Virtual Machine. Executes Java bytecode. Platform-specific (Windows/Mac/Linux JVMs exist).
- **JRE** — Java Runtime Environment. JVM + standard libraries. Enough to *run* Java apps.
- **JDK** — JRE + compiler + development tools. What you need to *write and build* Java.

**Why version matters:** Each version adds language features. Java 17 added sealed classes, pattern matching for instanceof, records. LTS = trust it for production. Non-LTS versions are short-lived experiments.

---

## How to make a galvo laser

**Galvanometer mirrors (galvos)** are tiny motorized mirrors driven by electromagnetic coils — they can deflect a laser beam extremely fast and precisely. Two mirrors handle X and Y axes.

**How it works:** Each galvo is essentially a rotary actuator — coil creates a magnetic field, permanent magnet on the mirror shaft rotates it. Analog voltage (or digital PWM) controls angle. Full scan in milliseconds.

**To build one:**
- **Pre-built galvo scanners** (~$50–200 from Chinese suppliers) include two mirrors + driver boards + analog input. Most common for laser shows = 20K or 30K scanners (scan speed in points per second).
- **Laser:** CO2 (cutting/engraving), diode (cheap, visible), or DPSS green (488/532nm — great for shows)
- **Control:** Analog X/Y signals (±5V or ±10V range). ILDA protocol for laser show software. Or drive with a microcontroller DAC output.
- **Safety:** Laser safety goggles rated for your wavelength. CO2 requires hard enclosure.

Use cases: laser engraver, laser show, LIDAR, galvo clock (draw clock face with laser).

---

## Cycloidal drive vs. harmonic drive

Both are compact, high-ratio speed reduction gearboxes. Used in robotics, robotic arms, servo systems.

**Harmonic drive (strain wave gear):**
- Three parts: wave generator (elliptical bearing), flexspline (flexible cup-shaped gear, 2 fewer teeth than circular spline), circular spline (rigid ring gear)
- Wave generator deforms the flex spline into an oval — engages circular spline at two points
- Each full rotation of the wave generator advances the flex spline by **2 teeth**
- Ratio = (teeth on circular spline) / 2 — achieves 50:1 to 320:1 in one stage
- Very low backlash. Used in robot joints, satellites, CNC.
- Weakness: flexspline fatigues over time under high load

**Cycloidal drive:**
- Eccentric cam rotates a cycloidal disc against a ring of outer pins
- Disc has slightly fewer lobes than the number of pins
- Each rotation of the cam advances the disc one "lobe-worth"
- High ratio, very high torque capacity, extremely low backlash, more robust than harmonic
- More complex to machine; more parts

**How to CAD a cycloidal:**
The disc profile is mathematically defined — parametric equations for the cycloid curve. In Fusion 360: use the equation-driven curve tool or a parametric sketch. Many tutorials on YouTube search: "fusion 360 cycloidal drive."

---

## Does carbon monoxide rise or sink?

Neither consistently. CO has a molecular weight of ~28 g/mol — nearly identical to air (~29 g/mol) — so it doesn't float or sink by molecular weight alone. It **disperses and mixes** with air.

However, CO from combustion (car exhaust, gas appliances) is **hot when produced**, and hot gas rises due to convection. As it cools, it spreads evenly through the room. In practice, CO concentrations are relatively uniform throughout a space.

**Detector placement:** Mid-wall to near-ceiling (5 feet or higher) catches it whether it's still rising or already mixed. Don't put it at floor level — CO isn't like propane (which is heavier and sinks).

---

## Project inspiration: What can you make from a broken laptop?

YouTube video — watch and brainstorm. Potential salvage from a dead laptop:
- Screen (repurpose as external monitor or control display)
- Battery cells (Li-ion 18650s — repack into power bank)
- Keyboard + trackpad (USB controller mod)
- Speakers
- Webcam
- WiFi card
- Cooling fan
- Hard drive / SSD
- Hinges and chassis hardware

*(YouTube: search "things to make from a broken laptop" — watch first, then come back and add specific project ideas here)*

---

## (Re)learning math: Cross product with a determinant

The cross product **a × b** of two 3D vectors is computed as a 3×3 determinant:

```
a × b = | i   j   k  |
        | a₁  a₂  a₃ |
        | b₁  b₂  b₃ |
```

Expand along the top row:
- **i** component: (a₂b₃ − a₃b₂)
- **j** component: −(a₁b₃ − a₃b₁)
- **k** component: (a₁b₂ − a₂b₁)

Result is a vector perpendicular to both **a** and **b**. Magnitude = |a||b|sin(θ) = area of the parallelogram they form.

Right-hand rule: curl fingers from **a** toward **b** — thumb points in the direction of **a × b**.

---

## (Re)learning math: Representing higher-power curves in linear algebra

You're right that a matrix represents a linear system (rows = equations, columns = variables). Higher powers seem to break that — but you can handle them by **changing what the variables represent**.

**Key idea: introduce substitution variables**

For a polynomial equation like y = ax² + bx + c, treat x², x, and 1 as three separate "variables": let u₁ = x², u₂ = x, u₃ = 1. Now it's linear: y = au₁ + bu₂ + cu₃.

**Vandermonde matrix** — used for polynomial curve fitting. If you have n data points (x₁, y₁) ... (xₙ, yₙ), build:

```
| 1   x₁   x₁²   x₁³ |   | a₀ |   | y₁ |
| 1   x₂   x₂²   x₂³ | × | a₁ | = | y₂ |
| 1   x₃   x₃²   x₃³ |   | a₂ |   | y₃ |
| 1   x₄   x₄²   x₄³ |   | a₃ |   | y₄ |
```

Columns are powers of x — each row is one data point evaluated at those powers. Solve for the coefficient vector [a₀, a₁, a₂, a₃] using standard linear algebra (Gaussian elimination, or least squares for overdetermined systems). This is how polynomial regression works under the hood.

---

## How do recommendation systems work?

Systems that predict what a user wants based on data. Two main approaches:

**Collaborative filtering:** "Users like you also liked..." — finds patterns in user behavior without knowing anything about the items themselves. Builds a user-item matrix (rows = users, columns = items, values = ratings). Uses matrix factorization (SVD) to find latent features. Netflix, Spotify, Amazon all use variants of this.

**Content-based filtering:** "Because you liked X, here's something similar..." — analyzes item attributes and matches to user history. Needs metadata about items.

**Hybrid:** Most real systems combine both.

**Deep learning approach:** Neural collaborative filtering — embeddings for users and items, dot product or MLP to predict preference. More powerful than classic matrix factorization.

**The cold start problem:** New users or items have no data — hard to recommend anything. Usually solved with popularity-based defaults or onboarding questionnaires.

Reference: [NVIDIA — Recommendation Systems](https://www.nvidia.com/en-us/glossary/recommendation-system/)

---

## What is a Support Vector Machine (SVM)?

An ML algorithm that classifies data by finding the **optimal hyperplane** that maximally separates two classes. The "support vectors" are the data points closest to the boundary — they're the only ones that matter for defining it.

**Key idea — maximum margin:** SVM doesn't just find any separating line, it finds the one with the largest gap between classes. Wider margin = better generalization.

**Kernel trick:** For data that isn't linearly separable in the original space, SVM maps it to a higher-dimensional space where it becomes separable — without actually computing the high-dimensional coordinates (just the distances). Common kernels: linear, polynomial, RBF (radial basis function).

**When to use:** Small-to-medium datasets, high-dimensional feature spaces (text classification), when you need a clear margin of separation. Neural nets often outperform it at scale.

---

## What is the consistency rule in fiction?

The concept you're thinking of is **internal consistency** — sometimes called **verisimilitude** or more practically, **Sanderson's Laws of Magic**.

**Brandon Sanderson's First Law:** *"An author's ability to solve conflict with magic is directly proportional to how well the reader understands said magic."*

The broader principle: within a fictional world, you can define any rules, physics, or logic you want — but you must **apply them consistently**. The reader accepts your world's rules through suspension of disbelief, but the moment you violate your own established rules without justification, the contract breaks.

- You can have FTL travel — just pick a mechanism and be consistent
- You can have magic that works on sacrifice — but it must always work on sacrifice
- You can have a villain who can't lie — but he really can't, ever

**Verisimilitude** = the quality of appearing true and believable *within* the world's own logic. You're not trying to match real life — you're trying to match your own rules.

---

## NSF/ANSI 456 — Vaccine storage standard

**NSF/ANSI 456** is the American standard for pharmaceutical-grade refrigerators and freezers used to store vaccines. Defines:

- Temperature performance requirements (vaccines typically need 2–8°C refrigeration or −15 to −50°C freezing)
- Temperature uniformity across the storage unit
- Temperature recovery time after door opening
- Alarm requirements for temperature excursions
- No frost-free cycling in freezers (frost-free units cause temperature swings that degrade some vaccines)

Key practical point: a standard household fridge/freezer does NOT meet NSF 456. Vaccines require purpose-built units with tighter temperature control and logging. Relevant for pharmacy context.

---

## Current transformers vs. voltage transformers — and how transformers work

**How a transformer works:** Two coils of wire wound around a shared magnetic core. AC current in the primary coil creates a changing magnetic field in the core, which induces an AC voltage in the secondary coil. Voltage ratio = turns ratio: V₂/V₁ = N₂/N₁.

**Voltage transformer (PT — potential transformer):** Standard transformer. Steps voltage up or down. Used for measurement to safely scale down high voltages (e.g., 11kV → 110V) for meters and instruments. High input impedance.

**Current transformer (CT):** Designed to measure current, not voltage. Primary is often just the wire carrying the current (one "turn" through the core). Secondary has many turns. Outputs a small, proportional current (e.g., 1000A primary → 5A secondary at 200:1 ratio). Low input impedance — secondary must NEVER be open-circuited while energized (dangerously high voltage will develop).

Use case: power monitoring, protection relays, smart meters. The clamp meter you've seen around a wire — that's a CT.

---

## How do Janney / train couplers work?

The **Janney coupler** (patented 1873, now the AAR standard in North America) is the automatic knuckle coupler used on virtually all North American freight rail.

**How it works:**
1. Each coupler has a **knuckle** — a hook-shaped jaw that can pivot open or closed
2. As two cars approach, the knuckles contact each other and pivot open
3. They lock into each other automatically — no one needs to be between the cars
4. A **pin (knuckle pin)** drops to lock the assembly
5. To uncouple: pull a lever to retract the pin and open the knuckle

**Draft gear:** The large spring/buffer assembly behind the coupler absorbs shock forces during coupling and train acceleration/braking — prevents cars from slamming into each other.

Why it matters: before Janney couplers, brakemen had to stand between moving cars to insert a pin manually — extremely dangerous. The automatic coupler eliminated most of those deaths.

---

## Why are trusses the strongest structural shape?

Because **triangles are the only inherently rigid polygon**.

A rectangle deforms into a parallelogram when force is applied — it needs diagonal bracing to resist shear. A triangle cannot change shape without changing the length of its members. It's geometrically rigid by definition.

**What this means structurally:**
- Every member in a truss carries only **axial force** — pure tension or pure compression along its length
- No bending moments in the members (bending is what breaks beams)
- Axial forces are far more efficient: the entire cross-section works uniformly
- The geometry distributes loads through the whole structure rather than concentrating stress

**Why it's strong per weight:** Steel is strongest along its axis. A thin rod resists axial load efficiently but bends easily. Put those rods in a triangle — now none of them bend, all of them pull or push. Massive strength-to-weight ratio.

Relevant to your tensegrity table — tensegrity uses tension + compression members in a similar spirit, except the members never touch, and tension cables handle what would normally be bending loads.

---

## Cool Stuff

### Solar panels that repel dust

Researchers (including NASA and MIT) have developed **electrostatic dust-repelling solar panels** — an electric field is applied across the panel surface, which exerts force on the electrically charged dust particles and moves them off the surface.

Designed for: Mars rovers and desert solar farms where manual cleaning isn't viable. A panel coated in dust loses 30–40% efficiency. No water needed, works autonomously.

Current status (2024): being piloted at utility-scale solar farms. Not yet mainstream but close to commercial viability.

---

## Types of connectors (hobbyist electronics)

| Connector | What it is | Common use |
|---|---|---|
| **Spade / spade terminal** | Flat tab that slides onto a stud or post. Crimp-on. | Power connections, car audio, battery terminals |
| **BNC (Bayonet Neill-Concelman)** | Coaxial connector with a quarter-turn bayonet lock. RF and video. | Oscilloscope probes, RF equipment, camera/SDI video |
| **Barrel plug / DC barrel jack** | Cylindrical plug-and-socket for DC power. Defined by inner/outer diameter (common: 5.5mm outer / 2.1mm inner). | DC power adapters, Arduino power |
| **Compression connector** | Screws or compresses onto a cable end to form a sealed connection — no soldering. | Coax cable (RG6, RG59), antenna connections |
| **JST** | Small plastic snap connectors in various pin counts. Standard in RC hobby and battery packs. | LiPo batteries, small PCB wiring |
| **XT30 / XT60** | High-current gold-plated bullet connectors. 30A / 60A rated. | Drone batteries, e-bikes |
| **Dupont** | Female/male pin headers used on breadboards and Arduino GPIO. | Prototyping, jumper wires |

---

## What is a Schmitt trigger? (Hysteresis in hardware)

A **Schmitt trigger** is a comparator circuit with **hysteresis** — it has two different switching thresholds instead of one. The output switches HIGH when input crosses an upper threshold, and switches LOW only when input drops below a lower threshold. The gap between them is the **hysteresis band**.

**Why it matters:** Without it, any noisy analog signal hovering near a threshold causes the output to chatter — toggling rapidly dozens of times per second. With hysteresis, noise within the band is completely ignored. The output only flips when the signal clearly moves past a defined level.

**How to build one:** Use an op-amp or comparator with **positive feedback** (the output feeds back to the non-inverting input via a resistor divider). The output state shifts the reference voltage, creating the two thresholds automatically.

**Uses:** Debouncing mechanical switches, cleaning up sensor outputs, building oscillators (RC + Schmitt trigger = square wave generator), anywhere noisy analog needs to become clean digital.

---

## Reed switch vs. Hall effect sensor

Both detect the presence of a magnet. Different in every other way.

| | Reed Switch | Hall Effect Sensor |
|---|---|---|
| How it works | Magnetic field physically closes two ferromagnetic contacts | Magnetic field generates a voltage across a semiconductor (Hall effect) — no moving parts |
| Power needed | No — it's just a switch | Yes — needs VCC |
| Wear | Mechanical contacts wear out over time | None — solid state |
| Speed | Slow (~1kHz max) | Fast (kHz–MHz) |
| Bounce | Yes — needs debouncing | No |
| Cost | Very cheap | Slightly more |
| Output | Binary on/off | Digital or analog (can read field strength) |
| Best for | Door sensors, low-cycle detection, simple presence detection | Speed sensors, rotary encoders, motor control, high-cycle applications |

---

## How to blacken metal

Method depends on the metal and how durable you need it.

| Method | Metal | How | Durability |
|---|---|---|---|
| **Gun bluing (hot)** | Steel | Immerse in hot alkaline salt solution → forms magnetite (Fe₃O₄) | High |
| **Gun bluing (cold)** | Steel | Brush-on chemical solution | Low-medium |
| **Heat bluing** | Steel/spring steel | Heat until oxide forms — blue-black color at ~300°C | Medium |
| **Liver of sulfur** | Copper, brass, silver | Brush on solution → dark patina | Medium |
| **Chemical blackening / black oxide** | Steel | Industrial alkaline salt bath | High |
| **Cerakote / powder coat** | Any | Coating, not a surface treatment | Very high |

Heat bluing is the most satisfying to do by hand — watch the metal change color as temperature climbs. Ties directly into the [[copper plating oxidized gift]] project.

---

## How are biosignals read, processed, and turned into devices?

**Biosignals** are electrical or mechanical signals from biological processes:

| Signal | Source | Amplitude |
|---|---|---|
| ECG (electrocardiogram) | Heart electrical activity | ~1 mV |
| EEG (electroencephalogram) | Brain electrical activity | ~10–100 µV |
| EMG (electromyogram) | Muscle electrical activity | ~1–10 mV |
| PPG (photoplethysmogram) | Blood volume pulse (optical) | Analog light level |
| GSR / EDA | Skin conductance (stress) | Resistance change |

**Reading them:**
1. Electrodes contact skin and pick up microvolt-scale signals
2. **Instrumentation amplifier** — high gain, very low noise, high CMRR (rejects common-mode noise from both electrodes equally — critical for weak biosignals)
3. **Filtering** — 60Hz notch filter (removes power line noise), bandpass for signal of interest (ECG: 0.5–150Hz, EEG: 0.5–50Hz)
4. **ADC** — digitize the analog signal at adequate sample rate

**Processing:**
- FFT for frequency content (EEG frequency bands: delta, theta, alpha, beta, gamma)
- Wavelet transforms for time-frequency analysis
- Peak detection for heart rate (R-peak detection in ECG)
- ML classifiers for gesture recognition (EMG)

**Key ICs:**
- ADS1299 (TI) — 8-channel biosignal amplifier, very low noise, used in EEG/ECG
- AD8232 (Analog Devices) — ECG signal conditioning IC
- MAX30102 — integrated PPG sensor (SpO2 + heart rate), optical

**Open-source platforms:** OpenBCI, Arduino + bio-signal shield

This connects directly to signal processing coursework — the filter design, amplifier theory, and Fourier analysis you're studying are exactly what biosignal devices use.

---

## What is DC offset?

In AC circuits, a signal normally oscillates symmetrically around zero — equal positive and negative swings. **DC offset** is when that signal has a non-zero average value, meaning it's shifted up or down from zero.

**In audio:** A DC offset on a speaker signal means the speaker cone is sitting displaced from its rest position before any audio even plays. Causes:
- Distortion (asymmetric clipping)
- Wasted amplifier headroom
- Heat buildup in the voice coil
- Can physically damage speakers long-term

**Sources:** Amplifier imperfections, power supply noise bleeding into signal paths, ground loops, bad capacitor coupling.

**Fix:** A DC-blocking capacitor in series (passes AC, blocks DC). Most audio equipment has these built in. If you're measuring with an oscilloscope and see the waveform floating above or below zero — that's DC offset.

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
