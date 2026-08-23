# Pharmacy Database — Overview

**Type:** Project Hub
**Status:** In progress — 13 of 14 categories built
**Source:** https://www.pharmacytimes.com/otcguide (Pharmacy Times OTC Guide, 2026-27 edition, ~145 product categories)
**Last updated:** 2026-08-23

---

Mirrors the category structure of the Pharmacy Times OTC Guide. Each category folder contains one file per product subcategory, listing every pharmacist-recommended brand and its % share plus the monthly recommendation volume. Every unique drug/brand also gets its own page under `drugs/` for future deep research (pros, cons, use cases, allergies, symptoms) — that research is a later phase, not this pass.

End goal: train a local AI on this data so family can query it at home. See [[pharmacy ai consultant]] for that side of the project.

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
14. Other — not yet built

## Related
- [[pharmacy ai consultant]]
