---
name: perf-goals
description: >
  Create, update, and review yearly performance goals aligned to business
  objectives and personal growth. Use this skill when the user wants to set
  or update their performance goals, define objectives for a review cycle,
  align goals to business priorities, add stretch or visibility goals outside
  their core role, or check progress on existing goals. Also use when the user
  mentions OKRs, performance objectives, review cycle planning, or what to
  focus on this year.
compatibility: Requires a writable filesystem. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

This skill creates and maintains yearly performance goals. Goals are structured
across two tracks:

- **Core role goals** — deliverables and outcomes expected of your role
- **Growth & visibility goals** — scope expansion, new skills, and cross-functional
  work that increases your profile beyond your immediate responsibilities

Each goal is stored as its own file at `{vault}/goals/YYYY/goal-slug.md` where
the slug is the kebab-case of the goal title. An index file at
`{vault}/goals/YYYY.md` links to all goals for the year.

## Configuration

1. Read vault location from `.career-skills.toml` in the user's home directory. If the file does not
   exist, ask the user where they want to store their career files (suggest
   `~/career` on Mac/Linux or `C:\Users\<name>\Documents\career` on Windows),
   then write `.career-skills.toml` in the user's home directory with their chosen path.
2. Create `{vault}/goals/` if it does not exist.

## Creating goals

1. **Read config** — load `.career-skills.toml` from the user's home directory.
   If missing, follow the Configuration steps above before proceeding.

2. **Gather context** — ask for anything not already provided:
   - Current role and level
   - Company or team priorities for the year
   - Areas the user wants to grow or gain visibility in
   - Any goals already discussed with their manager

3. **Draft goals** — produce a set of core goals and at least one growth or
   visibility goal. Use OKR thinking as a guide: each goal has a qualitative
   Objective (what you want to achieve and why it matters) and measurable Key
   Results (how you'll know you got there). Apply this with judgment — not every
   company uses OKR language, but the underlying structure (intention + evidence
   of success) is universally useful. For each goal, define:
   - A clear, outcome-focused title
   - A 1–2 sentence objective
   - 2–3 measurable success criteria
   - The business priority it supports
   - Whether it is core role or growth/visibility

4. **Confirm with the user** before writing anything to disk.

5. **Write the files** — for each goal, create `{vault}/goals/YYYY/goal-slug.md`
   using the individual goal template below. Then create or update the index
   at `{vault}/goals/YYYY.md`.

## Updating goals

1. Read the relevant goal file from `{vault}/goals/YYYY/`.
2. Make the requested change.
3. Update the `updated` field in the frontmatter.
4. Show the diff to the user before writing.

## Checking progress

1. Read the index at `{vault}/goals/YYYY.md` and load each linked goal file.
2. Note which goals have no recent log activity (reference `{vault}/logs/`).
3. Suggest goals that may need attention or a status update.

## Individual goal file template

```markdown
---
year: YYYY
track: core-role
status: Not started
updated: YYYY-MM-DD
---

# [Goal Title]

**Objective:** [One or two sentences describing the desired outcome.]

**Success criteria:**
- [Measurable outcome 1]
- [Measurable outcome 2]

**Business alignment:** [Which company or team priority this supports]
```

For growth & visibility goals, add:

```markdown
**Why this matters for growth:** [What skill, scope, or relationship this builds]
```

## Index file template

```markdown
---
year: YYYY
role: [Job Title]
updated: YYYY-MM-DD
---

# Performance Goals YYYY

## Core Role Goals

- [Goal Title](YYYY/goal-slug.md)

## Growth & Visibility Goals

- [Goal Title](YYYY/goal-slug.md)

## Notes

[Context about goals, manager feedback, or priorities to revisit.]
```

## Gotchas

- Growth goals are frequently skipped in favour of core role goals. If the user
  hasn't included any, prompt them to add at least one.
- Success criteria should describe outcomes, not activities. "Ship feature X" is
  an activity; "Feature X is in production and used by Y customers" is an outcome.
- If the user's company uses a specific framework (OKRs, SMART), ask and adapt
  the template structure to match it.
