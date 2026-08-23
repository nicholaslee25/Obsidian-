# Pharmacy Database — Overview

**Type:** Project Hub
**Status:** Complete — 14 of 14 categories built; ingredients/ research layer built (73 pages) and cross-referenced into drugs/
**Source:** https://www.pharmacytimes.com/otcguide (Pharmacy Times OTC Guide, 2026-27 edition, ~145 product categories)
**Last updated:** 2026-08-23

---

Mirrors the category structure of the Pharmacy Times OTC Guide. Each category folder contains one file per product subcategory, listing every pharmacist-recommended brand and its % share plus the monthly recommendation volume. Every unique drug/brand also gets its own page under `drugs/` for future deep research (pros, cons, use cases, allergies, symptoms) — that research is a later phase, not this pass.

End goal: train a local AI on this data so family can query it at home. See [[pharmacy ai consultant]] for that side of the project.

## The ingredients/ Research Layer

`projects/pharmacy/ingredients/` holds 73 active-ingredient evidence pages — organized by ingredient (guaifenesin, ibuprofen, calcium, proton-pump-inhibitors, etc.), not by brand. They were transcribed from two ChatGPT-compiled evidence dossiers ([[source — otc guide master dossier volume 2]] and [[source — otc evidence corpus chatgpt continuation]]) rather than from the Pharmacy Times category pages, and each one carries actual clinical evidence: study design, N, PMID/DOI, effect sizes, and an evidence grade (High/Moderate/Low/Very Low/No product-specific evidence), plus Pros, Cons/Safety Limitations, Contraindications, and Special Population Flags where the source discusses them.

**Two-layer rule (never merge these):**
- **`drugs/*.md` "Appears In" data** = a pharmacist-recommendation percentage from the Pharmacy Times survey (e.g. "Imodium — 81%"). This is a preference/market-share statistic — it says nothing about whether the drug works.
- **`ingredients/*.md` evidence** = actual clinical trial data for the active ingredient (design, population, result, PMID). This is the efficacy/safety layer.

A brand's `drugs/*.md` page now points to the relevant `ingredients/*.md` page(s) in its Overview section wherever the two source dossiers plausibly support the connection, hedged with "formulation not verified against actual label" language whenever the specific SKU-to-ingredient link isn't independently confirmed in source. Brands with no clear, source-supportable ingredient link are deliberately left unlinked rather than guessed at from name or category alone.

## Categories (site order)

1. **Cough, Cold & Allergy** — built (`cough-cold-allergy/`, 18 subcategories)
   - antihistamines-oral
   - cold-remedies
   - cough-suppressants
   - cough-cold-flu-combinations-daytime
   - cough-cold-flu-combinations-nighttime
   - decongestants-nasal-spray
   - decongestants-oral
   - expectorants
   - flu-products
   - homeopathic-cold-products
   - homeopathic-cough-products
   - homeopathic-flu-products
   - intranasal-allergy-products
   - intranasal-corticosteroids
   - topical-cough-suppressants-lozenges
   - topical-vapor-therapy
   - zinc-cold-remedies
   - zinc-lozenges
2. **Diabetic Healthcare** — built (`diabetic-health-care/`, 3 subcategories)
   - diabetic-cough-products
   - diabetic-foot-cream
   - diabetic-neuropathy-products
3. **Diagnostics** — built (`diagnostics/`, 4 subcategories; devices not drugs, filed under `drugs/` for consistency)
   - at-home-covid-test
   - blood-glucose-monitors
   - blood-sampling-devices-lancets
   - digital-thermometers
4. **Durable Goods** — built (`durable-goods/`, 2 subcategories; devices not drugs, filed under `drugs/` for consistency)
   - joint-support-braces
   - support-hosiery
5. **EENT (Ear, Eye, Nose & Throat)** — built (`eareyesnosethroat/`, 8 subcategories)
   - artificial-tears-ophthalmic-lubricants
   - contact-lens-solutions-saline
   - ear-pain-relief
   - ear-wax-removal
   - ophthalmic-antihistamines-decongestants
   - saline-nasal-moisturizers
   - snore-aids
   - sore-throat-products
6. **First Aid** — built (`first-aid/`, 8 subcategories)
   - bandages-covers-and-gauze
   - burn-treatments
   - insect-bite-and-sting-management
   - liquid-bandages
   - sun-burn-relief
   - thermal-relief-products
   - topical-anesthetics
   - topical-antibiotics-antiseptics
7. **Oral Care** — built (`oral-care/`, 9 subcategories)
   - canker-sore-treatments
   - cold-sore-treatments
   - cosmetic-mouthwashes-oral-rinses
   - dry-mouth-therapy
   - night-guards-nocturnal-bruxism-management
   - therapeutic-mouthwashes-oral-rinses
   - toothache-products
   - toothpaste-general-use
   - toothpaste-sensitive-gums-teeth
8. **Pain and Inflammation** — built (`pain-and-inflammation/`, 7 subcategories)
   - headache-products
   - migraine-headache-products
   - oral-anti-inflammatory-products
   - oral-arthritis-pain-relievers
   - oral-pain-relievers-adult
   - sleep-aid-analgesic-combination-products
   - transcutaneous-electrical-nerve-stimulation-tens-products
9. **Pediatrics** — built (`pediatrics/`, 11 subcategories)
   - childrens-allergy
   - childrens-analgesics
   - childrens-cough
   - childrens-cough-cold-combinations
   - childrens-homeopathic-cough-products
   - childrens-motion-sickness-products
   - childrens-mouthwashes
   - childrens-multivitamins
   - childrens-topical-cough-suppressants-ointments
   - diaper-rash-products
   - infant-gas-products
10. **Gastrointestinal** — built (`gastrointestinal/`, 13 subcategories)
    - acid-reducers
    - antacids
    - antidiarrheals
    - antiflatulence-products
    - h2-receptor-antagonists
    - lactose-intolerance-products
    - laxatives-bulk-fiber
    - laxatives-nonfiber
    - laxatives-stimulant
    - nausea-remedies
    - proton-pump-inhibitors
    - stool-softeners
    - upset-stomach-remedies
11. **Topicals** — built (`topicals/`, 22 subcategories)
    - acne-products
    - antibacterial-soaps
    - dandruff-shampoo
    - eczema-care-relief-products
    - foot-care-products
    - hemorrhoidal-preparations
    - homeopathic-topical-analgesics
    - incontinence-related-skin-protectants
    - insect-repellants
    - jock-itch-antifungal-products
    - lice-treatments
    - lip-balms
    - scar-treatments
    - stretch-mark-treatments
    - sunscreen
    - therapeutic-skin-care-cleansers
    - therapeutic-skin-care-moisturizers
    - toe-foot-antifungal-products
    - topical-analgesics
    - topical-analgesics-arthritis-joint-pain
    - topical-poison-ivy-oak-remedies
    - wart-removers
12. **Vitamins and Dietary Supplements** — built (`vitamins-and-dietary-supplements/`, 27 subcategories)
    - letter-vitamin-brand
    - brain-health
    - calcium-supplements
    - cholesterol-management
    - coenzyme-q10-supplements
    - cranberry-supplements
    - diet-aids
    - fiber-supplements
    - flax-seed-oil-supplements
    - garlic-supplements
    - herbal-supplement-brand
    - high-potency-vitamin-c-supplements
    - hydration-support
    - immune-support
    - iron-supplements
    - joint-health
    - magnesium-supplements
    - melatonin-sleep-aids
    - memory-support
    - mood-health-supplements
    - multivitamins
    - nerve-health
    - nutritional-supplements
    - ocular-nutritional-supplements
    - omega-3-fish-oil-supplements
    - prenatal-vitamins
    - probiotic-dietary-supplements
13. **Women's Health** — built (`womens-health/`, 6 subcategories)
    - menstrual-pain-relief
    - urinary-health
    - vaginal-care-and-hygiene
    - vaginal-moisturizers-and-lubricants
    - womens-health-menopause-supplements
    - yeast-infection-prevention-and-relief
14. **Other** — built (`other/`, 4 subcategories)
    - aspirin-recurrent-heart-attack-stroke-prevention
    - leg-cramp-relief
    - motion-sickness-remedies
    - sleep-aids-non-melatonin

## Related
- [[pharmacy ai consultant]]
- [[source — otc guide master dossier volume 2]]
- [[source — otc evidence corpus chatgpt continuation]]
