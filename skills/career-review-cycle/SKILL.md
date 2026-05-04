---
name: career-review-cycle
description: >
  Manage your career performance across the full year cycle: set and track
  yearly goals, log daily work, generate brag documents, prepare for
  performance reviews and 1-on-1s, and build promotion cases. Use when the
  user mentions performance goals, OKRs, work logging, accomplishments, brag
  doc, self-assessment, annual review, mid-year review, 1-on-1 prep, promotion
  case, or promo doc. Also triggers on "what did I work on", "log my work",
  "review prep", "set my goals", "career goals", or "am I ready for promotion".
compatibility: Requires a writable filesystem. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

This skill manages your career performance across the full year cycle:

- **Goals** — set and track yearly performance goals aligned to business priorities
- **Work log** — capture daily work linked to goals
- **Brag doc** — synthesise logs into accomplishment summaries
- **Review prep** — write self-assessments for performance reviews
- **1-on-1 prep** — generate talking points for manager meetings
- **Promo case** — build a promotion case mapped to a leveling rubric

## Configuration

1. Read vault location from `.career-skills.toml` in the user's home directory.
   If the file does not exist, ask the user where they want to store their
   career files (suggest `~/career` on Mac/Linux or
   `C:\Users\<name>\Documents\career` on Windows), then write
   `.career-skills.toml` with their chosen path.
2. Create the required output directory if it does not exist (each reference
   file specifies which directory it writes to).

## Routing

Read the user's request and load the appropriate reference file:

| The user wants to… | Load |
|---|---|
| Set, update, or review goals | [references/goals.md](references/goals.md) |
| Log work done today or recently | [references/work-log.md](references/work-log.md) |
| Generate an accomplishment summary | [references/brag-doc.md](references/brag-doc.md) |
| Prepare for a performance review | [references/review-prep.md](references/review-prep.md) |
| Prepare for a 1-on-1 with their manager | [references/one-on-one-prep.md](references/one-on-one-prep.md) |
| Build a promotion or leveling case | [references/promo-case.md](references/promo-case.md) |

If the request spans multiple capabilities (e.g. generate a brag doc and use
it to prep for a review), load both reference files.
