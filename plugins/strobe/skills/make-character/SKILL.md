---
name: make-character
description: Use when the user wants to create a Strobe character from photos, or pick a voice for a character they started.
---

# Make a character

1. Run `strobe whoami -o json`. If it fails, ask the user to run `strobe login` in their terminal, then stop.
2. Ask for a name and two or more photo paths.
3. Run `strobe create character --name "<name>" --photos "<a.jpg>,<b.jpg>" -o json`.
   Without a voice, the command prints the voice options with preview links and exits. It also prints the draft id and the command to resume.
4. Show the voice lines to the user exactly as printed. Ask which one they want. Never choose for them.
5. Resume: `strobe create character --draft CD… --voice <number> -o json`.
6. Report the character id, name, and voice. Tell the user they can now use it in a video.

If the command fails on a photo, report the message and ask for another photo. Never reuse a draft for a different person.
