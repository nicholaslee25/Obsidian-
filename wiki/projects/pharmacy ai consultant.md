# Pharmacy AI Consultant

**Type:** Project
**Tags:** #project #education #family #ai
**Status:** Active — data organization phase
**Last updated:** 2026-08-23

---

## Overview

Started as "Pharmacy for Noobs" — an educational resource explaining medications, dosages, interactions, and pharmacy basics in plain language for non-medical people. Grew into something bigger: a full structured drug reference database ([[pharmacy overview]]), organized by category/subcategory/drug, sourced from the Pharmacy Times OTC Guide.

End goal: train a local AI on this data so family can ask it things like pros/cons, use cases, allergies, and symptoms for any OTC drug, at home, without needing a pharmacist on hand.

## Phases

1. **Organize** (current) — mirror the OTC Guide's category structure, one file per subcategory with ranked brands + % pharmacist recommendation. One page per unique drug, stubbed for research.
2. **Research** — fill in each drug page: pros, cons, use cases, allergies, symptoms, interactions.
3. **Train** — build/fine-tune a local model on the completed database.
4. **Deploy** — make it queryable at home for family.

## Original Open Questions (from "Pharmacy for Noobs")

- Format: website, PDF, printed guide, app? → superseded by the local AI plan
- Scope: OTC meds only, or prescription too? — still open; starting OTC-only via the guide, prescription scope TBD
- What specifically confuses mom and dad most? — still need their input
- Audience: just family, or shareable publicly? — still open

## Next Step

Finish building out the remaining 13 OTC Guide categories (see [[pharmacy overview]]), then start the research phase per drug. Talk to mom and dad about what confuses them most — that should shape what the AI prioritizes explaining.

---

## Related

- [[pharmacy overview]]
- [[goals]]
