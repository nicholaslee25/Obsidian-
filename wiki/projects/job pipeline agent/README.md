# Job Pipeline: setup

Dashboard: https://claude.ai/artifact/HXWmEZZwXDjc2x5Ugu7Giq

## When your laptop is back
1. Install the Claude desktop app and the Claude in Chrome extension. Sign in to both with this account.
2. Add the skill: claude.ai → Settings → Capabilities → Skills → Upload, then pick `job-pipeline.zip`.
   Keep your existing `job-apply-batch` skill on too, because this one uses its form-filling rules.
3. In the desktop app, connect your JobApps folder (the one with `answer_bank.md`).
4. Open the dashboard and fill in "What to search for".
5. Run it once by hand in the desktop app: "Run the job pipeline." Watch the first run.
6. If that run looks good, make it a scheduled task in the desktop app with the same prompt.
   Twice a day (say 8:40am and 5:40pm) is a good start. It only runs while the laptop is awake.

## Your loop
- Found: tick the jobs you want. The next run fills them out.
- Ready to review: the tab is open on the review page. Check it, click Submit on the site, then "I submitted it".
- Action items: do the thing (make the account, answer the question in answer_bank.md), then "Done, retry it".
