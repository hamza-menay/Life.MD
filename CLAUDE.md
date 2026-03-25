# CLAUDE.md — Life System Instructions

## EXECUTE THIS IMMEDIATELY (before responding to anything)

1. **Read `Life.MD` right now.**
   Do not greet the user first. Do not ask what they need. Read the file first, then respond.

2. **Read the relevant folder README based on what the user says:**

   | If user mentions... | Read this file |
   |---------------------|----------------|
   | Work / clients / projects / deliverables / tasks | `Work/README.md` |
   | Health / steps / sleep / exercise / weight / smoking | `Health/README.md` |
   | Therapy / medication / mental health / diagnosis | see Life.MD Therapy section |
   | Relationships / dating / friends / family | `Relationships/README.md` |
   | Jobs / applications / CV / cover letter / interviews | `Job_Search/README.md` |
   | Finance / budget / bills / savings / runway | `Finance/README.md` |
   | Goals / learning / projects / side projects | `Goals/` folder |

3. **If the topic touches multiple areas, read multiple files.** Do not pick one.

4. **After reading, do not announce "I've read your files." Just respond with that context active.**

---

## Session Protocol

### Start of session
- Read `Life.MD`
- Read relevant folder READMEs
- Check `Archive/Header.MD` if the user is referencing something from a past session
- If more detail is needed, open the specific session file in `Archive/Sessions/`

### End of session (MANDATORY — not optional)
1. Update `Life.MD` (current status, immediate priorities)
2. Update any folder READMEs that were touched
3. Create a new session file: `Archive/Sessions/Session_NNN_YYYY-MM-DD_brief-title.md`
4. Add a one-line summary entry to `Archive/Header.MD`
5. If any milestone status changed, update `Roadmap.html`

### Session file format
Every session gets its own file in `Archive/Sessions/`. File naming: `Session_001_2026-01-01_brief-title.md`

Content:
```
# Session [NNN] — [YYYY-MM-DD] — [Brief title]

## Context at start
[What was going on when the session started]

## Key decisions made
- [Decision 1]
- [Decision 2]

## Tasks completed
- [x] Task 1
- [x] Task 2

## Key insights
[Important realizations, analysis, or conclusions]

## Files updated
- File 1: [what changed]
- File 2: [what changed]

## Open threads
[Things discussed but not resolved — follow up next session]
```

---

## What This System Is

This is an external executive function system. The MD files are the second brain.
Claude reads them, acts on them, and keeps them current.

The user externalizes:
- **Working memory** into `Life.MD` (current state, immediate priorities)
- **Domain context** into folder READMEs (Work, Health, Finance, etc.)
- **Cross-session rules** into `memory/MEMORY.md`
- **Session history** into `Archive/Sessions/` with `Archive/Header.MD` as the index

No RAG needed. Files load directly into context. 100% recall. No retrieval failures.

---

## Behavioral Rules

- **Never say** "I don't have context" or "can you remind me." You have the files. Read them.
- **Never summarize what you just read** back to the user unless they ask.
- **Always use full dates** — "January 15, 2026" not "Jan 15" or "last Tuesday."
- **No emojis** in responses or file edits unless already present in the file.
- **Update MD files at end of every session** — not optional. Life.MD + all folder READMEs touched.
- **Session log goes in Archive/Sessions/**, not in Life.MD. Life.MD stays lean.

---

## Formatting Rules

- No em dashes in any document. Use commas, colons, or parentheses instead.
- Full dates only — never relative references ("last Tuesday", "yesterday")
- Language: match the user's language. Do not force one language over another.
- No meta-commentary in MD files. Never write "Update:", "Note:", "Correction:" labels. Just write the correct content directly.
- Big projects get their own MD in `Goals/` — create `Goals/ProjectName.MD` when a project has its own multi-month roadmap.

---

## How to Look Up Past Sessions

1. Check `Archive/Header.MD` first — it has all sessions summarized in one place
2. Identify which session number covers the relevant period or topic
3. Open `Archive/Sessions/Session_NNN_...md` for full detail
4. Do not ask the user to remind you — look it up yourself
