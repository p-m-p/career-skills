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
entry is a timestamped block linked to one or more goals. These logs feed into
the `brag-doc` skill when it is time to write a performance summary.

## Configuration

Read vault location from `~/.career-skills.toml`:

```toml
vault = "/path/to/your/career/folder"
```

If this file does not exist, ask the user where they want to store their career
files, create `~/.career-skills.toml` with their answer, then create the vault
directory before proceeding.

## Logging an entry

1. **Identify the date** — use today's date unless the user specifies otherwise.

2. **Capture the work** — ask for or infer from the user's message:
   - What was done
   - Which goal(s) it relates to — reference titles from `{vault}/goals/YYYY.md`
     if the file exists; otherwise ask or use a placeholder
   - Type of work: `delivery` | `learning` | `visibility` | `collaboration`
   - Any outcome or impact worth noting (optional but valuable for brag-doc)

3. **Append the entry** to `{vault}/logs/YYYY-MM-DD.md`. Create the file with
   a date header if it does not exist yet.

4. Keep entries factual and brief. Capture what happened now; synthesis happens
   later in `brag-doc`.

## Log file template

```markdown
---
date: YYYY-MM-DD
---

# Work Log — Weekday, Month DD YYYY

## HH:MM — [Brief Title]
**Goals:** [Goal title 1], [Goal title 2]
**Type:** delivery
[Description of what was done and any notable outcome or impact.]

---

## HH:MM — [Brief Title]
**Goals:** [Goal title]
**Type:** visibility
[Description.]

---
```

## Multiple entries in one session

If the user wants to log several things at once, capture each as a separate
block with its own heading. Use approximate times if exact times are not given.

## Gotchas

- If the goals file does not exist, still create the log entry. Use a
  placeholder goal name and suggest the user run `perf-goals` to set up their
  goals file.
- For visibility or collaboration entries, prompt the user to note who was
  involved and which team or stakeholder was impacted. This detail is hard to
  reconstruct later and is valuable in a brag doc.
- Do not reframe or summarise the user's description at this stage. Capture what
  they said faithfully. The `brag-doc` skill handles synthesis.
