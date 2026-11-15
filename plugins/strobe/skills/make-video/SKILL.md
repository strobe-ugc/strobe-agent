---
name: make-video
description: Use when the user wants to make a Strobe video from a template and a character, start production, follow it, or download the result.
---

# Make a video

1. Run `strobe whoami -o json`. If it fails, ask the user to run `strobe login` in their terminal, then stop.
2. Run `strobe credits -o json`. Tell the user the balance and ask for consent: "This starts a paid video."
3. Resolve the inputs:
   - `strobe get templates -o json`
   - `strobe get characters -o json`
   If the user did not name a template and a character, show the names and ids and ask them to pick.
4. Start it: `strobe create video --template TP… --character CH… --name "<name>" -o json`.
   Read `task_id` and `item_id`. If the command reports a missing template or character, go back to step 3.
5. Follow it: `strobe get item TSK…/TI… -o json` every 60 seconds. Report each change in plain words. Stop when the item is `ready`, `review`, `completed`, or `failed`.
6. Ready or completed: `strobe download video TSK…/TI… --out "<path>" -o json`. Ask before adding `--acknowledge`.
7. Review or failed: give the user the message the command printed, then offer the next step. `strobe start item TSK…/TI…` retries it; run that only with consent.
8. After 30 minutes, stop waiting. Give the user the item id and the command to check again.

Never pick a template, a character, or a name on the user's behalf. Never retry or delete anything without consent.
