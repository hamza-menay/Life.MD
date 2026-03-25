# Life System — Setup Guide

This is a Claude-powered external executive function system. It replaces scattered notes, forgotten to-dos, and "remind me next session" with a persistent, structured second brain that Claude reads and maintains.

---

## How it works

**Claude reads your MD files at the start of every session.**
You never have to re-explain context. It's already there.

**Claude updates your MD files at the end of every session.**
What happened, what was decided, what's next — all written down automatically.

**Sessions are archived individually.**
`Archive/Sessions/` has one file per session. `Archive/Header.MD` has a one-line summary of each. If you need to find something from two months ago, Claude checks the header and opens the right file.

---

## Setup (5 steps)

1. **Copy this folder** and rename it: `[YourName]_Life/`

2. **Fill in `Life.MD`:** Replace all `[PLACEHOLDER]` text with your actual situation. 15-30 minutes.

3. **Fill in folder READMEs:** Work, Health, Finance, Relationships — fill in what's relevant, skip what isn't.

4. **Put the folder somewhere you'll always open it:** Desktop works. Dropbox or iCloud also works.

5. **Open Claude Code CLI and point it at your folder:**
   ```
   claude --add-dir /path/to/YourName_Life
   ```
   Or use the `cd` command in Claude Code to navigate there.

---

## File structure

```
YourName_Life/
├── CLAUDE.md               <- Instructions for Claude (read-only, do not edit)
├── Life.MD                 <- Main context: who you are, what's happening now
├── memory/
│   └── MEMORY.md           <- Cross-session rules and hard facts (index)
├── Archive/
│   ├── Header.MD           <- All sessions summarized — check here for past info
│   └── Sessions/           <- Individual session files (one per session)
├── Work/README.md          <- Clients, projects, tasks
├── Health/README.md        <- Habits, metrics, medical
├── Finance/README.md       <- Budget, bills, runway
├── Relationships/README.md <- Key people and context
├── Goals/
│   ├── Learning.MD         <- What you're studying and why
│   └── Projects.MD         <- Side projects
```

---

## Key rules (hardcoded)

- **Full dates always:** "January 15, 2026" not "last Tuesday"
- **No em dashes** in any document
- **No meta-commentary:** Claude writes clean content, no "Update:" or "Note:" labels
- **Session logs go in Archive/Sessions/**, not in Life.MD — Life.MD stays lean
- **Claude reads files first, responds second** — never asks "can you remind me"

---

## Why this works better than chat memory

Standard AI chat memory is fuzzy, inconsistent, and hits limits. This system is:
- 100% recall (files load directly into context)
- Version-controlled (plain text, git-friendly)
- Portable (works with any Claude interface)
- Transparent (you can read and edit every file yourself)
- Scalable (session archives keep Life.MD small no matter how long you use it)

---

## First session prompt

When you first open Claude Code with this folder, say:
> "Read Life.MD and the relevant folder READMEs. I'm just getting started with this system. Help me fill in the blanks."

Claude will walk you through what's missing and get the system running.
