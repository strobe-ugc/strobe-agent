---
name: strobe
description: Use when the user asks about Strobe, wants to make a Strobe video, character, or reference video, or needs the right strobe command. The starting point for every Strobe request.
---

# Strobe

`strobe` is the Strobe command line. These skills use it to make videos, characters, and reference videos, and to check credits.

## Session

Run `strobe whoami -o json` first. If it fails, ask the user to run `strobe login` in their terminal, then stop. Never ask for a password or a login code.

## Commands

```
strobe login [--email E]        sign in
strobe logout                   sign out
strobe whoami                   the signed-in user and team
strobe config view              settings and session expiry
strobe version                  version

strobe get characters           list characters
strobe get character CH…        one character
strobe create character --name N --photos a.jpg,b.jpg [--voice <n>]
strobe create character --draft CD… [--voice <n>]
strobe update character CH… [--name] [--description] [--voice]
strobe delete character CH… [--yes]

strobe get tasks                list tasks
strobe get task TSK…            one task and its items
strobe create video --template TP… --character CH… [--task TSK…] [--wait]
strobe get item TSK…/TI…        one item
strobe wait item TSK…/TI…       follow an item
strobe start item TSK…/TI…      start or retry an item
strobe delete item TSK…/TI… [--yes]
strobe download video TSK…/TI… [--out f.mp4] [--acknowledge]

strobe get templates            list templates
strobe get template TP…         one template
strobe get references           list reference videos
strobe get reference TB…        one reference video
strobe create reference --file ref.mp4 --name X [--wait]
strobe wait reference TB…       follow a reference video
strobe retry reference TB…      retry a reference video
strobe delete reference TB… [--yes]

strobe credits                  balance
strobe charges [--page N]       recent charges
```

## Rules

- Add `-o json` to every command that reads or creates something, and read the fields from the result.
- Ids: `CH` character, `CD` draft, `TSK` task, `TI` item, `TP` template, `TB` reference video. An item is `TSK…/TI…`.
- A video and a reference video spend credits. Run `strobe credits -o json` and ask for consent before starting one.
- Never guess a command that is not in this list. Tell the user what is missing.
- Tell the user what to do next, in their words. Do not explain how Strobe works inside.
