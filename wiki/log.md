# Log

Append-only record of all sessions and operations. Greppable by prefix: `## [YYYY-MM-DD]` — auto-sync enabled 2026-05-21

---

## [2026-08-23] update | GitHub connected + auto-sync workflow established

- Cloned the vault from `github.com/nicholaslee25/Obsidian-` to a local working directory; confirmed push access (Git Credential Manager authenticated)
- `CLAUDE.md` — added Sync section: every change is committed and pushed immediately, no batching
- `projects/game farming bot.md` — status updated to backburner/likely dropped; pyautogui approach got flagged for cheating by MCOC's anti-cheat

## [2026-08-23] ingest | Pharmacy database — Vitamins and Dietary Supplements

Twelfth category of 14. 27 subcategories — the most of any category so far, dominated by "Nature Made" and "Nature's Bounty" recurring across most of them. Anomaly worth noting: on this Windows filesystem (case-insensitive paths), brand names that differ only in casing on the source site — "zicam" (Immune Support) vs. the existing "Zicam" page from Cough, Cold & Allergy; "qunol" (Magnesium Supplements) vs. "Qunol" (Joint Health) — collapsed into the same file rather than creating separate near-duplicate pages, since `Path.exists()` is case-insensitive on Windows. This deviates from a strict literal exact-string match but was judged the better outcome (avoids clutter from what's clearly the same brand with inconsistent site capitalization) — flagging so it's a known, intentional-in-effect exception rather than a silent bug.

Pages created:
- `projects/pharmacy/vitamins-and-dietary-supplements/` — 27 subcategory files (letter-vitamin-brand, brain-health, calcium-supplements, cholesterol-management, coenzyme-q10-supplements, cranberry-supplements, diet-aids, fiber-supplements, flax-seed-oil-supplements, garlic-supplements, herbal-supplement-brand, high-potency-vitamin-c-supplements, hydration-support, immune-support, iron-supplements, joint-health, magnesium-supplements, melatonin-sleep-aids, memory-support, mood-health-supplements, multivitamins, nerve-health, nutritional-supplements, ocular-nutritional-supplements, omega-3-fish-oil-supplements, prenatal-vitamins, probiotic-dietary-supplements)
- `projects/pharmacy/drugs/` — 133 new unique stub pages

Pages updated:
- 16 existing drug pages appended, notably `Nature Made.md` now spans 13 subcategories within this category alone; `Zicam.md` and `Qunol.md` picked up cross-case appends per the note above
- `projects/pharmacy/overview.md` — status now 12 of 14; Vitamins and Dietary Supplements entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 12/14 categories

Next: Women's Health (category 13 of 14).

## [2026-08-23] ingest | Pharmacy database — Topicals

Eleventh category of 14, and the largest by subcategory count — 22 subcategories, 202 brand-ranking rows. Heavy overlap with earlier categories (CeraVe, Aquaphor, Eucerin, Cetaphil, Neutrogena, Aveeno, etc. all recur across many Topicals subcategories, and several also tie back to Diabetic Healthcare / Pain and Inflammation / First Aid drug pages from earlier categories) — 27 existing drug pages got Appears In lines appended rather than recreated.

Pages created:
- `projects/pharmacy/topicals/` — 22 subcategory files (acne-products, antibacterial-soaps, dandruff-shampoo, eczema-care-relief-products, foot-care-products, hemorrhoidal-preparations, homeopathic-topical-analgesics, incontinence-related-skin-protectants, insect-repellants, jock-itch-antifungal-products, lice-treatments, lip-balms, scar-treatments, stretch-mark-treatments, sunscreen, therapeutic-skin-care-cleansers, therapeutic-skin-care-moisturizers, toe-foot-antifungal-products, topical-analgesics, topical-analgesics-arthritis-joint-pain, topical-poison-ivy-oak-remedies, wart-removers)
- `projects/pharmacy/drugs/` — 116 new unique stub pages

Pages updated:
- 27 existing drug pages appended (Appears In), notably `CeraVe.md` now spans 6 subcategories across 3 categories (Diabetic Healthcare, Eczema Care/Relief, Sunscreen, Therapeutic Skin Care x2, Acne)
- `projects/pharmacy/overview.md` — status now 11 of 14; Topicals entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 11/14 categories

Next: Vitamins and Dietary Supplements (category 12 of 14).

## [2026-08-23] ingest | Pharmacy database — Gastrointestinal

Tenth category of 14. 13 subcategories. Note: "Nexium 24hr"/"Nexium 24HR" and "Prevacid 24hr"/"Prevacid 24HR" appear with different casing in different subcategories on the source site — filed as distinct exact-string drug pages per the established rule (not normalized/merged).

Pages created:
- `projects/pharmacy/gastrointestinal/` — 13 subcategory files (acid-reducers, antacids, antidiarrheals, antiflatulence-products, h2-receptor-antagonists, lactose-intolerance-products, laxatives-bulk-fiber, laxatives-nonfiber, laxatives-stimulant, nausea-remedies, proton-pump-inhibitors, stool-softeners, upset-stomach-remedies)
- `projects/pharmacy/drugs/` — 46 new unique stub pages

Pages updated (Appears In appended):
- `Gelusil.md`, `Mylanta.md`, `Pepcid.md`, `Tagamet HB 200.md`, `Beano.md`, `Dulcolax.md` (now spans 3 subcategories), `Fleet.md`, `Pepto-Bismol.md`, `Alka-Seltzer.md`, `Sea-Band.md`, `Prilosec OTC.md`, `Nexium 24HR.md`, `Prevacid 24HR.md`, `Zegerid OTC.md`, `MiraLAX.md`, `Emetrol.md`, `Kaopectate.md`, `Nauzene.md`
- `projects/pharmacy/overview.md` — status now 10 of 14; Gastrointestinal entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 10/14 categories

Next: Topicals (category 11 of 14).

## [2026-08-23] ingest | Pharmacy database — Pediatrics

Ninth category of 14. Largest so far — 11 subcategories, 79 new drug stubs. Note: "Hyland 4 Kids Cough Syrup" (no apostrophe) and "Hyland's 4 Kids Cough Syrup" (with apostrophe) are two distinct exact strings on the source site, filed as separate drug pages per the exact-string-match rule.

Pages created:
- `projects/pharmacy/pediatrics/` — 11 subcategory files (childrens-allergy, childrens-analgesics, childrens-cough, childrens-cough-cold-combinations, childrens-homeopathic-cough-products, childrens-motion-sickness-products, childrens-mouthwashes, childrens-multivitamins, childrens-topical-cough-suppressants-ointments, diaper-rash-products, infant-gas-products)
- `projects/pharmacy/drugs/` — 79 new unique stub pages

Pages updated (Appears In appended):
- `Children's Dimetapp.md`, `Children's Mucinex.md`, `Children's Delsym.md`, `Children's Robitussin.md`, `Zarbee's Naturals.md`, `PediaCare.md`, `Tom's of Maine.md`, `Vicks VapoRub.md` (already existed from Cough, Cold & Allergy's Topical Vapor Therapy)
- `projects/pharmacy/overview.md` — status now 9 of 14; Pediatrics entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 9/14 categories

Next: Gastrointestinal (category 10 of 14).

## [2026-08-23] ingest | Pharmacy database — Pain and Inflammation

Eighth category of 14. 7 subcategories. Note: "Oral Pain Relievers, Adult" on this category turned out to be dental/gum topical analgesics (Orajel, Anbesol, Kank-A) per the site's own data — overlaps with Oral Care's canker/toothache subcategories but is a distinct site subcategory, kept as scraped.

Pages created:
- `projects/pharmacy/pain-and-inflammation/` — 7 subcategory files (headache-products, migraine-headache-products, oral-anti-inflammatory-products, oral-arthritis-pain-relievers, oral-pain-relievers-adult, sleep-aid-analgesic-combination-products, transcutaneous-electrical-nerve-stimulation-tens-products)
- `projects/pharmacy/drugs/` — 28 new unique stub pages

Pages updated (Appears In appended):
- `Tylenol.md`, `Aleve.md` (now spans 4 subcategories), `Advil.md`, `Motrin.md`, `BC Powder.md`, `Orajel.md`, `Anbesol.md`, `Kank-A.md`
- `projects/pharmacy/overview.md` — status now 8 of 14; Pain and Inflammation entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 8/14 categories

Next: Pediatrics (category 9 of 14).

## [2026-08-23] ingest | Pharmacy database — Oral Care

Seventh category of 14. 9 subcategories.

Pages created:
- `projects/pharmacy/oral-care/` — 9 subcategory files (canker-sore-treatments, cold-sore-treatments, cosmetic-mouthwashes-oral-rinses, dry-mouth-therapy, night-guards-nocturnal-bruxism-management, therapeutic-mouthwashes-oral-rinses, toothache-products, toothpaste-general-use, toothpaste-sensitive-gums-teeth)
- `projects/pharmacy/drugs/` — 47 new unique stub pages

Pages updated (Appears In appended):
- `Orajel.md`, `Cepacol.md`, `Biotène.md` (now spans 4 subcategories), `TheraBreath.md`, `SmartMouth.md`, `Anbesol.md`, `Kank-A.md`, `parodontax.md`, `Tom's of Maine.md`, `Burt's Bees.md`, `Listerine.md`, `Sensodyne.md`
- `projects/pharmacy/overview.md` — status now 7 of 14; Oral Care entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 7/14 categories

Next: Pain and Inflammation (category 8 of 14).

## [2026-08-23] ingest | Pharmacy database — First Aid

Sixth category of 14. 8 subcategories. Note: "Bactine", "Bactine Max", and "Bactine MAX" appear as three distinct exact strings across different subcategories on the source site — filed as three separate drug pages per the exact-string-match rule (not merged/normalized).

Pages created:
- `projects/pharmacy/first-aid/` — 8 subcategory files (bandages-covers-and-gauze, burn-treatments, insect-bite-and-sting-management, liquid-bandages, sun-burn-relief, thermal-relief-products, topical-anesthetics, topical-antibiotics-antiseptics)
- `projects/pharmacy/drugs/` — 40 new unique stub pages

Pages updated (Appears In appended):
- `Dermoplast.md` (now spans 5 subcategories), `Nexcare.md`, `Bactine MAX.md`, `Alocane.md`, `Biofreeze.md`, `Aspercreme with Lidocaine.md`, `Bactine Max.md`, `Neosporin.md`, `Bacitraycin Plus.md`, `Polysporin.md`
- `projects/pharmacy/overview.md` — status now 6 of 14; First Aid entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 6/14 categories

Next: Oral Care (category 7 of 14).

## [2026-08-23] ingest | Pharmacy database — EENT (Ear, Eye, Nose & Throat)

Fifth category of 14. 8 subcategories.

Pages created:
- `projects/pharmacy/eareyesnosethroat/` — 8 subcategory files (artificial-tears-ophthalmic-lubricants, contact-lens-solutions-saline, ear-pain-relief, ear-wax-removal, ophthalmic-antihistamines-decongestants, saline-nasal-moisturizers, snore-aids, sore-throat-products)
- `projects/pharmacy/drugs/` — 48 new unique stub pages

Pages updated (Appears In appended, brand already existed from an earlier category):
- `Biotrue.md`, `Visine.md`, `Clear Eyes.md`, `Xlear.md`, `Cepacol.md`, `Chloraseptic.md`, `Ricola.md`, `HALLS.md`, `Fisherman's Friend.md`, `Luden's.md`, `Mucinex Instasoothe.md`, `Sucrets.md`
- `projects/pharmacy/overview.md` — status now 5 of 14; EENT entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 5/14 categories

Next: First Aid (category 6 of 14).

## [2026-08-23] ingest | Pharmacy database — Durable Goods

Fourth category of 14. Smallest so far — 2 subcategories (Joint Support/Braces, Support Hosiery). Devices, same page structure as everything else, filed under `drugs/`.

Pages created:
- `projects/pharmacy/durable-goods/` — 2 subcategory files (joint-support-braces, support-hosiery)
- `projects/pharmacy/drugs/` — 8 new unique stub pages

Pages updated:
- `projects/pharmacy/drugs/Futuro.md`, `ACE.md` — appended Support Hosiery lines (already existed from Joint Support/Braces)
- `projects/pharmacy/overview.md` — status now 4 of 14; Durable Goods entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 4/14 categories

Next: EENT (category 5 of 14).

## [2026-08-23] ingest | Pharmacy database — Diagnostics

Third category of 14. Devices, not drugs (glucose monitors, lancets, thermometers, at-home COVID tests) — same `.rankList` page structure as drug categories, so no scraping/format deviation needed. Filed under the same `drugs/` folder per the established convention.

Pages created:
- `projects/pharmacy/diagnostics/` — 4 subcategory files (at-home-covid-test, blood-glucose-monitors, blood-sampling-devices-lancets, digital-thermometers)
- `projects/pharmacy/drugs/` — 15 new unique stub pages

Pages updated:
- `projects/pharmacy/drugs/Accu-Chek.md`, `OneTouch.md`, `FreeStyle.md`, `Contour Next.md` — appended Blood Sampling Devices/Lancets line (already existed from Blood Glucose Monitors, same category)
- `projects/pharmacy/overview.md` — status now 3 of 14; Diagnostics entry flipped to built
- `wiki/index.md` — pharmacy overview sub-line updated to 3/14 categories

Next: Durable Goods (category 4 of 14).

## [2026-08-23] ingest | Pharmacy database — Diabetic Healthcare

Second category of 14. Small category — only 3 subcategories on the site.

Pages created:
- `projects/pharmacy/diabetic-health-care/` — 3 subcategory files (diabetic-cough-products, diabetic-foot-cream, diabetic-neuropathy-products), each listing pharmacist-recommended brands with % share and monthly recommendation volume
- `projects/pharmacy/drugs/` — 20 new unique drug stub pages

Pages updated:
- `projects/pharmacy/drugs/Robitussin.md` — appended "Diabetic Cough Products - 28%" to Appears In (already existed from Cough, Cold & Allergy)
- `projects/pharmacy/overview.md` — status now 2 of 14 categories built; Diabetic Healthcare entry flipped to built with subcategory list
- `wiki/index.md` — pharmacy overview sub-line updated to 2/14 categories

Next: Diagnostics (category 3 of 14).

## [2026-08-23] ingest | Pharmacy database — Cough, Cold & Allergy (pilot category)

Kicked off the OTC drug reference database, sourced from the Pharmacy Times OTC Guide (pharmacytimes.com/otcguide). Structure mirrors the site: 14 top-level categories, ~145 subcategories total. Built the first category as a validated pilot before scaling to the rest.

Pages created:
- `projects/pharmacy/overview.md` — hub page, lists all 14 categories in site order, tracks build status
- `projects/pharmacy/cough-cold-allergy/` — 18 subcategory files (antihistamines-oral, cold-remedies, cough-suppressants, cough-cold-flu-combinations-daytime/nighttime, decongestants-nasal-spray/oral, expectorants, flu-products, homeopathic-cold/cough/flu-products, intranasal-allergy-products, intranasal-corticosteroids, topical-cough-suppressants-lozenges, topical-vapor-therapy, zinc-cold-remedies, zinc-lozenges), each listing pharmacist-recommended brands with % share and monthly recommendation volume, no cross-links (plain data, by request)
- `projects/pharmacy/drugs/` — 84 unique drug stub pages (one per brand), each with Overview/Pros/Cons/Use Cases/Allergies/Symptoms Treated sections marked TBD — deep research is a later phase
- `projects/pharmacy for noobs.md` renamed → `projects/pharmacy ai consultant.md` and reframed: original family-education framing kept, expanded with the end goal of training a local AI on the completed database for home use

Pages updated:
- `wiki/index.md` — pharmacy project entry updated to new name + database sub-entry; game farming bot status updated

Next: build out the remaining 13 categories the same way, then move to per-drug research.

---

## [2026-07-25] update | Music hub restructure + todo clarifications

Per Nykel's clarification on the twelfth dump's open flags:
- Electronics build todo (ICs / Excel requirements sheet) confirmed as a standalone todo, not tied to any project — unflagged in `you/todo.md`
- "Foo" in the waterfront-paper item confirmed as the professor on that paper — `you/todo.md` updated to say "the professor" instead of leaving it as an unresolved placeholder
- `skills/instruments.md` restructured into the canonical hub for all instruments (was an orphan, overlapping with `music.md`) — `skills/music.md` deleted, content redistributed

Pages created:
- `skills/guitar songs.md` — full song list + Travis picking, split out of the old `music.md`
- `skills/music theory.md` — chord progressions by key, split out of the old `music.md`

Pages rewritten:
- `skills/instruments.md` — now the hub page: Guitar (→ guitar songs, → music theory), Lofi Production, Drums, Guzheng (Jianpu notation), Kalimba

Pages deleted:
- `skills/music.md` — merged into `instruments.md` / `guitar songs.md` / `music theory.md`

Pages updated (all `[[music]]` wikilinks repointed to `[[instruments]]`):
- `wiki/index.md`, `you/goals.md`, `you/todo.md`, `you/person — nykel.md`, `skills/drawing.md`, `projects/dad's guitars database.md`, `projects/diy metronome.md`, `projects/drum repair.md`, `topics/entertainment.md`, `languages/chinese.md`, `languages/english.md`, `languages/spanish.md`

---

## [2026-07-25] ingest | Twelfth dump — food, theology deep-dive, new skills/projects, camera curiosities

Pages created:
- `you/six degrees.md` — chains of who-knows-who (Mike→Lakers draft→LeBron; Jo Gong→Flonase PhD; Matt R's dad→Big Mouth illustrator)
- `skills/knot tying.md` — bowline, butterfly loop, sheet bend, trucker's hitch, taut-line hitch
- `projects/diy lava lamp.md`, `projects/7 segment clock.md`, `projects/wii remote controller.md`, `projects/google home mini arduino.md`, `projects/gas powered swing set.md`, `projects/diy camera gimbal.md`, `projects/shark fin rotating hatches.md` — seven new project stubs, all brainstorming stage
- `topics/career concepts.md` — Michael Driver's career-path model (myzenpath.com, careerconcepts.de)
- `topics/epistemology and theology.md` — big one. Rowe's *Can God Be Free?* argument (simplified per request), Alston/Almeida on grounded belief, Adam's framework for why people land where they do on faith, *How NOT to Read the Bible* summary, and Nykel's own reflections (free will + childhood suffering, fairness of last-minute repentance, Islam vs. Christianity, religion-as-defense-mechanism). Structured with sources/arguments separated from personal reflection per Nykel's explicit request.

Pages updated:
- `skills/cooking.md` — Din Tai Fung cucumber salad added to Cooked (two attempts, notes on cucumber weight + salting); birria tacos, bun bo hue, omurice, jamaican cabbage added to Wanna Cook (pho + hainanese chicken already existed)
- `skills/baking.md` — 5 new Cooked entries (banana nut muffins, oatmeal raisin cookies, rainbow cookies, frozen berry cobbler — too tart, tri-muffin batch); 7 new Wanna Bake entries
- `skills/english.md` — added apoplectic, deepity, idiosyncrasy
- `skills/music.md` — added Kilby Girl, Waymaker, Build My Life to songs table
- `topics/reading.md` — added House of Leaves, The King in Yellow, 1984, Freakonomics, Piranesi
- `topics/quotes.md` — new Relationship Advice section
- `topics/photography.md` — added Gear Curiosities section: Hasselblad, holy trinity of lenses, RAW files, IBIS, ISO/ADC timing
- `topics/curiosities.md` — added: baking soda chemistry, function graphs, human eye resolution, torus coils (3D printability), 3D printer fume safety by material, car drivetrain, combining multiple AI models, funny/random ideas (resealing fortune cookies, "bitten object" STL trick)
- `topics/places to visit.md` — flagged likely duplicates: Cherry Springs vs. "Cherry Valley Dark Sky Park," Downtown Philly trail identified as Schuylkill River Trail
- `you/wishlist.md` — added Converse sizes, bone Swiss bearings, camera gimbal, photo hard drive; added Ninja Creami old-vs-new open question; new Gift Reference Notes section (black-eyed Susans = grandma's favorite flower)
- `you/goals.md` — Fitness section: added muscle up, splits, forearm twist bar workout, yoga workout link; Professional section: linked `career concepts.md`
- `projects/diy battery charger.md` — added note distinguishing battery *pack* (cells + BMS + enclosure) from battery *charger* (this project)
- `wiki/index.md` — added all 11 new pages across You/Skills/Projects/Topics

Flagged for Nykel to confirm:
- Cherry Springs State Park vs. "Cherry Valley National Dark Park" — almost certainly the same place, confirm before merging the row for good
- *How NOT to Read the Bible* author — logged without a confirmed author name, fill in when handy
- Several new projects (Wii remote controller, Google Home x Arduino, shark fin hatches) are solutions without a target application yet — flagged in their own pages, not blocking

---

## [2026-07-25] ingest | Eleventh dump — todo list created, chord progressions, epoxy lesson, new projects

Pages created:
- `you/todo.md` — new page type: running action-item list (urgent/calls/health/admin/projects/questions). Distinct from `priorities.md` (project-tier framework) and `goals.md` (long-term direction) — this is the concrete "did you do the thing" list
- `projects/custom pomodoro timer.md` — brainstorming stage, no defined hook yet
- `projects/potential/engine cad.md` — CAD an engine in Inventor; low conviction, flagged

Pages updated:
- `skills/music.md` — added Music Theory section: chord progressions by key (G, D, A, C, E)
- `projects/clear epoxy.md` — added hard-won lesson: this batch hardened in ~2hrs, faster than expected — embedded objects sank to the bottom before layering happened
- `topics/finance.md` — added trailing stop orders + how to read an earnings report
- `topics/things to learn.md` — added Fusion 360 CAM/router software under Tech & Electronics
- `topics/curiosities.md` — added entry on parenting/respect culture vs. the "poor parenting" stereotype (economic hardship ≠ parenting quality)
- `topics/places to visit.md` — added Hong Kong trip-planning note (text Bailey for local to-do list)
- `you/goals.md` — Professional section: added Ryo/balloon catheter research outreach + med school funding as open questions
- `wiki/index.md` — added `[[todo]]`, `[[custom pomodoro timer]]`, `[[engine cad]]`

Flagged for Nykel to confirm:
- "Separate and document ICs" + "make Excel sheet of requirements" — reads like the same unnamed electronics build as the purchase-list/PCB item, but no project name given. Filed together in `todo.md` under one bucket — confirm which project so it can move there.
- "Love on the waterfront" paper — "foo" is unclear (placeholder or an actual name?). Filed as-is in `todo.md`.
- Google Sheet ("what I've been up to since summer 2026 start") — categories captured in `todo.md`; actual sheet creation is external, on Nykel.
- `skills/instruments.md` is an orphan — not linked from `index.md`, both it and `skills/music.md` are titled "# Music" with overlapping (stale) song lists. Merge into `music.md` and delete, or is it kept for a different purpose?

---

## [2026-05-14] session-start | Wiki initialized

Vault created. Architecture established: `raw/` for sources, `wiki/` for maintained pages, `CLAUDE.md` as schema. Starting from a blank slate — no sources ingested yet.

Pages created this session:
- `CLAUDE.md` — schema
- `wiki/index.md` — master catalog
- `wiki/log.md` — this file
- `wiki/overview.md` — starter overview

Ready to receive the first source or question.

---

## [2026-05-14] ingest | Nykel self-introduction

Nykel shared a full personal profile — personality, hobbies, goals, skills, quirks. First real content in the brain.

Pages created:
- `you/person — nykel.md`
- `you/goal — career and money.md`
- `you/goal — social and relationships.md`
- `you/goal — fitness and athletics.md`
- `you/goal — language and vocab.md`
- `you/goal — quit YouTube.md`
- `skills/skill — balisong.md`
- `skills/skill — chinese.md`
- `skills/skill — guitar.md`
- `projects/project — NAS build.md`

Folder structure established: `you/`, `projects/`, `skills/`, `topics/`, `sources/`

Open questions seeded across multiple pages — needs Nykel to fill in details over time.

---

## [2026-05-14] update | Restructure — naming, goals consolidated, NAS removed

- Merged all goal pages → single `you/goals.md`
- Removed "skill —" prefix from all skill filenames
- Created `skills/music.md` (guitar, drums, guzheng)
- Created `skills/chinese.md` and `skills/balisong.md`
- Deleted `project — NAS build.md`
- Updated index and person page to match

## [2026-05-16] update | Restructured cooking + created baking

- skills/cooking.md — split into Cooked (table w/ date + notes) and Wanna Cook; first entry: beef noodle 牛肉面 (2026-05-16, forgot noodles used rice)
- skills/baking.md — created; same structure (Cooked table + Wanna Bake list); moved egg tarts, rice pudding, matcha pudding from cooking
- Updated index

## [2026-05-17] update | Created wishlist page

- `you/wishlist.md` -- new page, first item: power sliding skateboard wheels

## [2026-05-20] ingest | New project -- zen sand table

- `projects/zen sand table.md` -- kinetic sand art table, software mapping solved, open problems are actuation mechanism and hidden drive system

## [2026-05-20] update | Added wood cutting board project

- `projects/wood cutting board.md` -- created

## [2026-05-29] update | Added Ollama project + useful websites additions

- `projects/ollama local llm.md` — Ollama local LLM runner; use case TBD
- `topics/useful websites.md` — added CircuitLab, CircuitJS, Mindluster

## [2026-05-29] update | Created useful websites page

- `topics/useful websites.md` — new page, first entry: coddy.tech (Duolingo-style coding practice)

## [2026-06-02] update | Added Bechdel test to curiosities

- `topics/curiosities.md` — Bechdel-Wallace test entry added (3 criteria, origin, why it matters, known failures, limitations)

---

## [2026-06-02] update | Le'bama — Pi 4 vs 5 comparison + Ollama confirmed viable

- `projects/raspberry pi ai assistant.md` — LLM options table updated (Ollama now a confirmed path alongside Claude API); Pi 4 vs Pi 5 comparison table added specific to Le'bama's stack; Ollama model performance benchmarks on Pi hardware included

---

## [2026-06-02] update | Le'bama stack update

- `projects/raspberry pi ai assistant.md` — renamed to Le'bama; stack updated: Rhasspy (voice pipeline) + Home Assistant (smart home) + Claude (brain) + Piper (TTS); architecture diagram updated with simple intent vs. open query branching; added ⚠️ note on Claude "locally hosted" (API vs. Ollama trade-offs); new open questions (Rhasspy 2 vs 3, same Pi vs dedicated HA Pi, wake word)

---

## [2026-06-02] update | Tenth dump — songs list, culture, Raspberry Pi project

Pages created:
- `projects/raspberry pi ai assistant.md` — Pi-hosted voice assistant; Faster-Whisper STT + Piper TTS + Claude API + internet search layer; 3 reference videos noted; full build path checklist

Pages updated:
- `skills/music.md` — songs table expanded from 5 → 33 entries; added Artist column; new songs: Riptide, I'm Yours, Hey Soul Sister, Country Roads, Sweet Home Alabama, 4× Yorushika (Blur, Emerald Green Window, Sunny Day for You, Spring Thief), Mia & Sebastian's Theme, Howl's Moving Castle, River Flows in You, NGNL OP, Cannon in D, Carry On Wayward Son, Come Sail Away, Again (YUI), Adventure of a Lifetime, Tongue Tied, Until I Found You, Start Me Up, Mr. Brightside, 7 Nation Army, Iron Man, Veil, Wistoria Ending, Glorious Day, Silent Night
- `you/culture.md` — restructured into Chinese and Indian sections; Chinese etiquette table added (tea tapping, teapot lid refill signal, don't step over people); Indian section placeholder

Note: All vocab/phrases/books from dump already existed in english.md and reading.md — no changes needed.

---

## [2026-06-01] update | Ninth dump — home ownership, Nietzsche, guitar, EagleCAD, cooking

Pages created:
- `topics/home ownership.md` — buying checklist, house maintenance schedule, landlord responsibilities, house flipping

Pages updated:
- `topics/people of interest.md` — added Friedrich Nietzsche (full entry: Will to Power, Übermensch, amor fati, eternal recurrence, master-slave morality, misappropriation note)
- `skills/music.md` — added Overwhelmed to songs to learn
- `skills/english.md` — added vocab YouTube resource link
- `skills/cooking.md` — added Hainanese chicken to Wanna Cook
- `topics/useful websites.md` — EagleCAD entry expanded with Jeremy Blum tutorial series + Gerber file guide; added Vaughn Gene "Teach Yourself Anything" to Learning section

Note: Most food items from dump already existed (Chow mein, Pho, Tandoori, Chazuke, Hot green peas, Fermented Rice Alc in Beverages). Egg tarts/rice pudding/matcha pudding already in baking.md.

---

## [2026-06-01] update | Eighth dump — voltage regs, new projects, drawing skill, employers

Pages created:
- `projects/custom usb stick chassis.md` — custom USB drive housing; wood/resin/metal options
- `projects/custom chessboard.md` — maple/walnut chessboard; storage base option
- `skills/drawing.md` — new skill, not started; fundamentals → figure → perspective path

Pages updated:
- `you/potential employers.md` — added Spacelabs Healthcare + JPL (the dream)
- `projects/wood cutting board.md` — full feature brainstorm: shape, grain, juice groove, inlay, rubber feet, finish
- `skills/music.md` — added Song of Storms fingerstyle
- `topics/quotes.md` — added "Why not you?" to Personal Mantras
- `topics/curiosities.md` — added voltage regulators entry (linear/LDO vs switching, LM317 design steps, reference link)
- `topics/youtube watch later.md` — added: voltage regulators (Tech/DIY), Why You're Always Tired + What Your Dad Forgot (Personal Dev), 1hr meme anime loop (Entertainment)

---

## [2026-06-01] ingest | Seventh dump — planetary gears, BMS, steppers, gardening

Pages created:
- `skills/gardening.md` — green onions, shampoo ginger lily, tomatoes, cabbage; per-plant tips; wildlife defense table (birds/squirrels); best practices

Pages updated:
- `topics/curiosities.md` — added: planetary gear system (uses + project potential), BMS (functions, balancing types, key ICs), unipolar vs bipolar steppers, internal cycloidal robotic actuator (MIT Mini Cheetah, Mjbots, build path)

## [2026-06-01] ingest | Sixth dump — family reflection, math, options, electronics, projects

Pages created:
- `projects/dad's guitars database.md`
- `projects/pole dropper reflex machine.md`

Pages updated:
- `topics/quotes.md` — "Why I Do This" section added directly under Kant — family reflection + video link + commitment to try
- `skills/cooking.md` — added biryani, chili oil, kimchi
- `topics/youtube watch later.md` — added: progress in life, overwhelmed (HealthyGamerGG), 43min communication advice (placeholder), diff eq (Zach Star), chain rule visual, Maxwell's equations, stock market, motor speed controller, optocouplers
- `topics/curiosities.md` — added: brush vs brushless motors, chain rule/parametric/Jacobian, ISO 17025, engineering consulting benefits, stock options (full Greeks + IV explanation), future investments, to-do list project, JDK 17, galvo laser, cycloidal vs harmonic drive
- `you/potential employers.md` — added engineering consulting as career path
- Confirmed: `projects/pharmacy for noobs.md` exists ✓

## [2026-05-31] ingest | Fifth dump — curiosities, games page, guzheng notation, metronome update

Pages created:
- `topics/fun games.md` — Chameleon, Codenames, Throw Throw Burrito, Exploding Kittens, Poker quick ref

Pages updated:
- `topics/curiosities.md` — added: CO density, broken laptop inspiration, cross product with determinant, Vandermonde/higher-power curves, recommendation systems, SVM, fiction consistency rule (Sanderson's Laws/verisimilitude), NSF/ANSI 456, current vs voltage transformers, Janney couplers, trusses, cool stuff (electrostatic dust-repelling solar panels), connector types (spade, BNC, barrel, compression, JST, XT60, Dupont)
- `topics/entertainment.md` — added Kimi no Na Wa (Your Name)
- `projects/diy metronome.md` — added reference video + slip ring note for spinning display
- `wiki/skills/music.md` — added Jianpu notation guide for guzheng
- `topics/quotes.md` — added child's joy mantra
- `topics/useful websites.md` — added GreatScott! YouTube channel

Note: "tensity table" in dump = tensegrity table — already filed. Confirmed with user.

## [2026-05-31] ingest | Fourth dump — curiosities, books, anime, wishlist, cars

Pages created:
- `topics/cars.md` — comprehensive placeholder: maintenance, components, brands, drivetrain, mods, driving knowledge

Pages updated:
- `topics/entertainment.md` — added Summertime Rendering, Your Lie in April
- `topics/reading.md` — added Secrets of the Immortal Nicholas Flamel, Magisterium; added short story recs (thinking + eldritch horror) — confirmed Renegades + Usuzumi no Hate already present
- `you/wishlist.md` — added Big Purchases section: Ninja Creami 👑, Genmitsu Cubiko CNC, Carvera Air
- `topics/quotes.md` — added Personal Mantras section with hard work quote
- `you/goals.md` — added Steinbach Pianos as potential employer
- `wiki/skills/music.md` — added Lost in Paradise (2nd JJK opening)
- `topics/youtube watch later.md` — added Life Church sermon
- `topics/useful websites.md` — added Humble Bundle to Games section
- `topics/curiosities.md` — added: Schmitt trigger, reed switch vs Hall effect, how to blacken metal, biosignals
- `topics/curiosities.md` — car knowledge redirects to [[cars]] page

## [2026-05-31] ingest | Third dump — quotes, media, keyboards, channels, personal

Pages created:
- `you/love and relationships.md` — Sisyphus 55, OliSUNvia, Love of Kill/Call of the Night reflection (post-D breakup), A Day Before Us

Pages updated:
- `topics/quotes.md` — Kant categorical imperative added to top; "jack of all trades" full quote added
- `you/goals.md` — Kant quote added at very top per request
- `topics/youtube watch later.md` — added: strategic thinking, ages 1–100 regrets, tiny home robotics lab, rich/poor controversial questions, You vs You (religion section added)
- `topics/curiosities.md` — added DC offset; confirmed Secure Boot + TPM already present
- `topics/keyboards.md` — added TKL definition, TFT screen, QMK/VIA explained, Zuoya GMK87, Akko 5087S; expanded layout table
- `topics/entertainment.md` — added: The Summer Hikaru Died, Blood-C, The Empty Box and Zeroth Maria, A Day Before Us
- `topics/useful websites.md` — added Robonyx, Sisyphus 55, OliSUNvia to YouTube channels

## [2026-05-31] ingest | Second big info dump — consolidation session

Pages created:
- `projects/custom speakers.md` — full build + dead earbud conversion
- `projects/diy battery charger.md` — needs battery chemistry learning first
- `projects/throwing hook game.md` — wooden ring-hook game
- `projects/diy metronome.md` — rotary encoder deep-dive + build plan
- `projects/mechatronics beginner.md` — IK, servo arms, starting point
- `topics/quotes.md` — David Gemmell, procrastination
- `topics/finance.md` — clawbacks, HYSA, CD rates, finance people
- `topics/entertainment.md` — anime, music playlists
- `topics/people of interest.md` — Ray Kurzweil, Bulwer-Lytton
- `you/bible verses.md` — Proverbs 16

Pages updated:
- `skills/english.md` — added flippant, percolate
- `skills/baking.md` — added 5 new wanna-bake items
- `languages/chinese.md` — added full vocab table (characters/pinyin/english/direct/type); 慢慢吃, 笨蛋, 厚, 薄, plus existing phrases
- `topics/curiosities.md` — massive additions: device drivers, biphasic defib, CS algorithms, ghost scrolling, pipe leaks, hydrofoils, Geneva mechanism, 3-phase power, impedance, Reynolds/Prandtl/Nusselt, Newtonian fluids, vacuum physics, Gauss, non-lethal weapons, Travis picking, tinkering section (Teensy 4, ESP32)
- `topics/useful websites.md` — added PCB fabrication/design tools, CAD software costs, MongoDB, Fluxbench channel
- `topics/youtube watch later.md` — added 7 new videos across categories
- `topics/things to learn.md` — added Git/GitHub section
- `projects/clear epoxy.md` — added casting vs epoxy resin + floating objects technique
- `you/goals.md` — added Philips Healthcare + Reliant Medical as potential employers

Note: efficient compute frontier was ALREADY in curiosities — confirmed, not a duplicate.

## [2026-05-31] ingest | Big info dump — new pages, updates, priority system

Pages created:
- `topics/photography.md` — favorite styles, plain-English settings
- `topics/pc parts.md` — monitor types (IPS/TN/VA/OLED) + specs
- `topics/things to learn.md` — math, EIT, philosophy, tech, finance
- `you/priorities.md` — tiered priority framework (Now/Soon/Queue/Someday) + frequency table
- `projects/gyroscope visualization.md` — idea stub
- `projects/clear epoxy.md` — research checklist
- `projects/windshield washer cannon.md` — car mod idea
- `projects/pharmacy for noobs.md` — needs parent input
- `projects/drum repair.md` — needs dad input
- `projects/youtube channel.md` — document the journey

Pages updated:
- `you/goals.md` — added professional goals (EIT, medical consideration), things to quit/reduce, YouTube channel
- `projects/woodwork clock.md` — major update: discrete oscillator circuit direction, full parts list, build path, circuit review flags
- `projects/moon cycle clock.md` — added motor type + shaft adapter as open questions
- `projects/wood radiator cover.md` — marked HIGH URGENCY
- `topics/keyboards.md` — added PCB section, modding techniques table, external peripherals
- `projects/game farming bot.md` — confirmed MCOC, marked active

Pending (needs Nykel's input before Claude can process):
- 2–3 dozen notes dump
- YouTube watch later / open tabs
- Flashcard app decision (Anki vs Quizlet cross-device)
- Radiator measurements
- Spreadsheet / "sheet of everything"
- Japan trip photos situation

## [2026-05-27] update | Three new projects logged

- `projects/discord wiki bot.md` — Discord bot powered by Claude API, queries the wiki, answers questions from Discord
- `projects/game farming bot.md` — automated game farming via screen capture + mouse control; game TBD
- `projects/copper plating oxidized gift.md` — electroplate an object + patina/oxidize for a gift; object + recipient TBD
- `projects/symmetrical gear arm gripper.md` — rack & pinion parallel gripper driven by spring-loaded rod; normally open/closed TBD, actuation TBD
- `projects/3d printed pascal triangle.md` — 3D printed Pascal's triangle display piece; representation TBD
- `projects/woodwork hangboard.md` — wooden fingerboard for climbing training
- `projects/wood radiator cover.md` — decorative wood cover for mom's radiator; waiting on measurements