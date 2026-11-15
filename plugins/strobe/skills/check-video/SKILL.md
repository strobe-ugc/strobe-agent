---
name: check-video
description: Use when the user asks where a Strobe video is, what it is doing, whether it is done, or why it failed.
---

# Check a video

1. Run `strobe whoami -o json`. If it fails, ask the user to run `strobe login` in their terminal, then stop.
2. Run `strobe get tasks -o json`. If the user named a task or a video, find it. Otherwise show the five most recent with their name, id, and status.
3. Run `strobe get task TSK… -o json` for the chosen task. Report each item with its id, and explain the state in one sentence:
   - `draft`: not started
   - `generating`: in progress
   - `ready`: the video is ready to download
   - `review`: it needs the user's attention
   - `completed`: done
   - `failed`: it did not finish; include the message
4. For one item, run `strobe get item TSK…/TI… -o json` and report the state, the latest status line, and the failure message when present.
5. Offer the next step: download it, wait, or retry. `strobe start item TSK…/TI…` retries a failed item; run it only with consent.

This skill is read-only. Never retry, delete, or start anything without consent.
