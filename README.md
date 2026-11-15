# strobe-agent

Strobe skills for Claude Code and Codex. They call the Strobe command line, so install it and sign in once:

```sh
npm i -g @strobeaiugc/cli
strobe login --email you@example.com
```

## Claude Code

```sh
claude plugin marketplace add strobe-ugc/strobe-agent
claude plugin install strobe@strobe
```

## Codex

```sh
codex plugin marketplace add strobe-ugc/strobe-agent
codex plugin add strobe@strobe
```

## Skills

- `strobe`: the command map and the rules every other skill follows.
- `make-video`: pick a template and a character, start a video, follow it, download it.
- `check-video`: where a video is, what it is doing, and why it failed.
- `build-reference`: turn an mp4 into a reference video and follow it to review.
- `make-character`: create a character from photos and pick a voice.
- `check-credits`: balance and recent charges.

## Cost

A video and a reference video spend credits. Every skill checks the balance and asks before starting one. `check-credits` and `check-video` are read-only.

## Sign-in

The skills never ask for a password or a code. If the session has expired, they tell the user to run `strobe login` in their terminal.
