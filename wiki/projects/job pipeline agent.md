# Job Pipeline Agent

**Type:** Project
**Tags:** #project #career #claude-code #automation
**Status:** Built, waiting on first run
**Last updated:** 2026-11-07

---

## Overview

Background agent that finds job postings, fills out the ones you approve in Chrome (never clicks Submit), and logs everything to a dashboard. Anything that needs you (account, unanswered question, CAPTCHA, assessment) becomes an action item + notification, and it moves on.

- **Dashboard:** https://claude.ai/artifact/HXWmEZZwXDjc2x5Ugu7Giq — 3 columns: Found (checkbox to approve) / Ready to review / Action items, plus a "What to search for" form
- **Skill:** `job-pipeline` ([[job pipeline agent/SKILL]]) — builds on the existing `job-apply-batch` skill and its form-filling rules
- **Answers:** `answer_bank.md` in the JobApps folder on the personal laptop — the only source of answers
- **Runs on:** personal laptop, Claude desktop app + Claude in Chrome. Only runs while the laptop is awake.

## Setup checklist

- [x] Dashboard built + published (2026-10-25)
- [x] Skill written ([[job pipeline agent/README]] has full steps)
- [x] Claude in Chrome installed
- [ ] Desktop app installed, `job-pipeline` skill uploaded
- [ ] JobApps folder connected
- [ ] Search form filled in (see [[potential employers]] — Long Island ME/quality/mfg search)
- [ ] First supervised run; approve job sites as "always allow" in Chrome permissions
- [ ] Scheduled task in desktop app (twice a day to start)

## Files

- [[job pipeline agent/SKILL]] — agent instructions
- [[job pipeline agent/README]] — setup steps
- `job pipeline agent/job-board.html` — dashboard source

---

## Related
- [[potential employers]]
- [[career concepts]]
- [[discord wiki bot]]
