# Life.MD

A second brain you run inside Claude Code. The files hold your context. Claude reads them when a session starts and writes them back when it ends.

I built this because chat memory kept failing me. It forgot the things that actually mattered, "remembered" other things wrong, and ran out of room right when conversations got useful. Plain text files I own and edit myself fixed it. Files load directly into context. Full recall. I can read every byte.

This repo is the empty template. Clone it, fill in your own life locally, point Claude Code at the folder. The system stays on your machine.

---

## How it works

You keep your context in MD files. Claude reads them at session start, acts on them during the session, updates them at the end. Three layers:

- `Life.MD`: current state, this week's priorities, who you are. Stays lean.
- Folder READMEs (Work, Health, Finance, Relationships, Goals, etc.): domain context. Fill in what's relevant, skip what isn't.
- `Archive/Sessions/`: one file per session. `Archive/Header.MD` is the index Claude checks when you reference something old.

`memory/MEMORY.md` carries the things you don't want to re-teach Claude every time: cross-session rules, hard facts. Kept under 200 lines.

No RAG, no embeddings, no vector DB. Files.

---

## Setup

1. Clone or download this repo. Rename the folder to `[YourName]_Life/`.
2. Open `Life.MD`. Replace every `[PLACEHOLDER]` with your actual situation. 15-30 min.
3. Open the folder READMEs (Work, Health, Finance, Relationships) and fill in what's true. Skip what isn't.
4. Move the folder somewhere your machine always reaches it. Desktop works. iCloud or Dropbox too.
5. Open Claude Code and point it at the folder:
   ```
   claude --add-dir /path/to/YourName_Life
   ```
   Or `cd` into the folder before opening Claude Code.

First message in the new session:

> Read Life.MD and the relevant folder READMEs. I'm just getting started. Help me fill in the blanks.

Claude walks you through what's missing.

---

## Folder map

```
YourName_Life/
├── CLAUDE.md               instructions for Claude (do not edit)
├── Life.MD                 current state, priorities, who you are
├── memory/
│   └── MEMORY.md           cross-session rules + hard facts (index)
├── Archive/
│   ├── Header.MD           one-line summary per session
│   └── Sessions/           individual session files
├── Work/README.md          clients, projects, deliverables
├── Health/README.md        habits, metrics, medical
├── Finance/README.md       budget, bills, runway
├── Relationships/README.md key people and context
└── Goals/
    ├── Learning.MD         what you're studying and why
    └── Projects.MD         side projects
```

Add folders for whatever your life actually needs. `Travel/`, `Reading/`, `Hobbies/`, `Side_Project/`. Update `CLAUDE.md` so Claude knows when to read them.

---

## The hardcoded rules

These live in `CLAUDE.md` and run on every session:

- **Read first, respond second.** No "what's going on?" greetings. Claude reads `Life.MD` and the relevant folder READMEs before saying anything.
- **Full dates, never relative.** "January 15, 2026" not "last Tuesday."
- **No em dashes.** Use commas, colons, parens.
- **No meta-commentary in files.** Never "Update:" or "Note:" or "Correction:" labels. Write the correct content directly.
- **Life.MD stays lean.** Session detail goes in `Archive/Sessions/`, not in Life.MD.
- **End-of-session updates are not optional.** Life.MD + any folder README touched + a new session file + a Header.MD entry. Every time.

You can change any of these. Edit `CLAUDE.md`, they take effect next session.

---

## Why this works

**Files don't drift.** Chat memory is fuzzy and silent. You don't know what it kept. You don't know what it dropped. Files load directly into context with no retrieval layer in the middle. Full recall, every session.

**The tree does the routing.** When you mention work, Claude reads `Work/README.md`. Health goes to `Health/README.md`. Add a folder for whatever your life needs (`Travel/`, `Reading/`, `Family/`), update the routing table in `CLAUDE.md`, done. You don't think about where things go.

**Life.MD never bloats.** Session content moves into `Archive/Sessions/` at the end of every session. `Archive/Header.MD` carries a one-line summary per session. After a year of daily use, Life.MD is still small. `Header.MD` is how Claude finds anything older than the current week, in seconds, without scanning every file.

**memory/MEMORY.md is the ratchet.** When you teach Claude something the hard way (a writing rule, a hard fact, a thing it kept getting wrong), it goes here. Every future session inherits it. Mistakes become one-shot, not recurring.

**It survives everything.** Different Claude version, different interface, different machine, multiple instances open at once. The files are the source of truth. None of it depends on a session cache or a vendor's memory implementation.

**You stay in the loop.** You can read every byte. Edit any file. Correct something Claude got wrong. Grep across the whole system. The context is yours.

**Neglect surfaces.** Out-of-date folder README, stale Life.MD section, missing session file: visible. Chat memory hides that kind of decay. Files don't.

**Sessions are receipts.** Two weeks from now when you reference "that decision we made," the session file is there. Verbatim. Searchable. Yours.

---

## License

MIT. Use it, fork it, change it. Open a PR if you find a sharper way to structure any of this.
