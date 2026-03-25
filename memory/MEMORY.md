# MEMORY.md — Index

> This file is an index only. Each memory lives in its own file in this folder.
> MEMORY.md is loaded at every session. Keep it under 200 lines.
> Memory files carry cross-session behavioral rules and hard facts — not task lists or current state.

---

## Behavioral Rules

| Memory | File | Description |
|--------|------|-------------|
| [Rule name] | `memory/rule_name.md` | [One line: what the rule is] |

---

## Hard Facts

| Fact | File | Description |
|------|------|-------------|
| [Fact name] | `memory/fact_name.md` | [One line: what the fact is] |

---

## How to save a memory

1. Write the memory to its own file with this frontmatter:
```
---
name: [memory name]
description: [one-line description]
type: [user / feedback / project / reference]
---

[memory content]
```

2. Add a pointer to this MEMORY.md index.

Types:
- **user**: who the user is, how they work, their preferences
- **feedback**: corrections or guidance the user has given Claude
- **project**: ongoing work, goals, context behind decisions
- **reference**: where to find things in external systems

---

## System Rules (always apply)

- Read relevant folder READMEs before responding to any topic
- Use full dates only — "January 15, 2026" never "last Tuesday"
- No em dashes in any document
- Update MD files at end of every session — not optional
- Session logs go in `Archive/Sessions/`, not in Life.MD
- When asked to list tasks: read files fresh, never from memory
- Check `Archive/Header.MD` when user references past sessions
