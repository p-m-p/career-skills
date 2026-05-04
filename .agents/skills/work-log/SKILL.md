---
name: work-log
description: >
  Capture a work log entry for what you worked on today, linked to your
  performance goals. Use this skill when the user wants to log what they did,
  record an accomplishment, note a meeting outcome, track progress on a goal,
  or keep a daily work journal. Also triggers on phrases like "log my work",
  "what I did today", "add to my notes", "note that I", or anything about
  recording work activity.
compatibility: Requires a writable filesystem. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

Work logs are stored in `{vault}/logs/YYYY-MM-DD.md`, one file per day. Each
entry is a timestamped block linked to one or more goals via relative Markdown
links. These logs feed into the `brag-doc` skill when it is time to write a
performance summary.

## Configuration

1. Read vault location from `.career-skills.toml` in the user's home directory. If the file does not
   exist, ask the user where they want to store their career files (suggest
   `~/career` on Mac/Linux or `C:\Users\<name>\Documents\career` on Windows),
   then write `.career-skills.toml` in the user's home directory with their chosen path.
2. Create `{vault}/logs/` if it does not exist.

## Logging an entry

1. **Identify the date** — use today's date unless the user specifies otherwise.

2. **Capture the work** — ask for or infer from the user's message:
   - What was done
   - Which goal(s) it relates to — read goal files from `{vault}/goals/YYYY/`
     to find the correct filenames; otherwise use a placeholder
   - Type of work: `delivery` | `learning` | `visibility` | `collaboration`
   - Any outcome or impact worth noting (optional but valuable for brag-doc)

3. **Append the entry** to `{vault}/logs/YYYY-MM-DD.md`. Create the file with
   a date header if it does not exist yet.

4. Keep entries factual and brief. Capture what happened now; synthesis happens
   later in `brag-doc`. Where possible, nudge the user to note the outcome or
   impact alongside the action — even a rough result ("unblocked the team",
   "reduced errors by half") makes STAR reconstruction much easier later.

## Goal links

Link goals using relative Markdown links from the log file to the goal file.
A log at `{vault}/logs/YYYY-MM-DD.md` links to a goal at
`{vault}/goals/YYYY/goal-slug.md` using:

```markdown
[Goal Title](../goals/YYYY/goal-slug.md)
```

## Log file template

```markdown
---
date: YYYY-MM-DD
---

# Work Log — Weekday, Month DD YYYY

## HH:MM — [Brief Title]
**Goals:** [Goal Title](../goals/YYYY/goal-slug.md)
**Type:** delivery
[Description of what was done and any notable outcome or impact.]

---

## HH:MM — [Brief Title]
**Goals:** [Goal Title](../goals/YYYY/goal-slug.md), [Another Goal](../goals/YYYY/another-goal.md)
**Type:** visibility
[Description.]

---
```

## Multiple entries in one session

If the user wants to log several things at once, capture each as a separate
block with its own heading. Use approximate times if exact times are not given.

## Gotchas

- If the goals directory does not exist, still create the log entry. Use a
  placeholder goal name and suggest the user set up their goals with `perf-goals`.
- For visibility or collaboration entries, prompt the user to note who was
  involved and which team or stakeholder was impacted. This detail is hard to
  reconstruct later and is valuable in a brag doc.
- Do not reframe or summarise the user's description at this stage. Capture what
  they said faithfully. The `brag-doc` skill handles synthesis.
