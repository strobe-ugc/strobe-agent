---
name: build-reference
description: Use when the user wants to turn an mp4 into a Strobe reference video they can make videos from.
---

# Build a reference video

1. Run `strobe whoami -o json`. If it fails, ask the user to run `strobe login` in their terminal, then stop.
2. Run `strobe credits -o json`. Tell the user the balance and ask for consent: "This starts a paid reference video."
3. Ask for the mp4 file path and a name.
4. Run `strobe create reference --file "<path>" --name "<name>" -o json`. Read `template_build_id`.
5. Follow it: `strobe get reference TB… -o json` every 60 seconds. Report each change in plain words. Stop when the reference video finishes, waits for review, or fails.
6. Finished: report `template_id`. The user can now make videos from it.
7. Waiting for review: tell the user it is in review with Strobe and that the template appears when it is approved. Stop.
8. Failed: show the message. If it says the video is not a supported type, do not retry. Otherwise offer `strobe retry reference TB…` and run it only with consent.
9. After 30 minutes, stop waiting. Give the user the id and the command to check again.

Never upload a file the user did not name. Never retry without consent.
