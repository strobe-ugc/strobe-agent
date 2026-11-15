---
name: check-credits
description: Use when the user asks about their Strobe balance, what they spent, or whether they have enough credits.
---

# Check credits

1. Run `strobe whoami -o json`. If it fails, ask the user to run `strobe login` in their terminal, then stop.
2. Run `strobe credits -o json`. Report the balance, what is reserved, and whether spending is blocked, in plain words.
3. Run `strobe charges --per-page 10 -o json`. List the ten most recent charges with the date, what it was for, and the amount.
4. If the balance is low, say so and point the user to the Strobe app to add credits.

This skill is read-only. Never start a video or a reference video from it.
