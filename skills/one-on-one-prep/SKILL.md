---
name: one-on-one-prep
description: >
  Generate talking points for an upcoming manager 1-on-1, drawing on recent
  work logs and goal progress. Use this skill when the user has a 1-on-1 coming
  up and wants to prepare, wants to know what to raise with their manager, or
  wants to surface blockers and wins from recent work. Also triggers on
  "1-on-1 prep", "one on one", "meeting with my manager", "what to discuss
  with my manager", or "weekly sync prep".
compatibility: Requires read access to the career vault. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

A well-prepared 1-on-1 agenda keeps your manager informed, surfaces blockers
early, and creates a paper trail of your progress. This skill reads recent work
logs and goal status to generate a focused agenda you can bring to the meeting.

Output is stored at `{vault}/one-on-ones/YYYY-MM-DD.md`.

## Configuration

Read vault location from `~/.career-skills.toml`. If this file does not exist,
use the `career-init` skill to set it up before proceeding.

## Generating talking points

1. **Identify the period** — default to the last 7 days unless the user
   specifies a different range (e.g. since the last 1-on-1).

2. **Read recent logs** — scan `{vault}/logs/` for entries within the period.

3. **Read the goals** — load the index at `{vault}/goals/YYYY.md` and read
   individual goal files from `{vault}/goals/YYYY/` to check status and surface
   any that are at risk or stalled.

4. **Build the agenda** — group talking points into:
   - **Wins** — completed work and progress worth highlighting
   - **In progress** — what's underway, any context the manager needs
   - **Blockers** — anything slowing progress that needs manager input
   - **Goals check** — any goals that are off track or need a conversation
   - **Asks** — specific requests: decisions, introductions, feedback, support

5. **Keep it short** — a 1-on-1 agenda should be scannable. Bullet points,
   not paragraphs. The user drives the conversation; this is a prompt, not a
   script.

6. **Confirm with the user** before writing — ask if there is anything specific
   they want to raise that isn't in the logs.

7. **Write** to `{vault}/one-on-ones/YYYY-MM-DD.md` using today's date.

## Output template

```markdown
---
date: YYYY-MM-DD
period: [last 7 days / since YYYY-MM-DD]
---

# 1-on-1 Prep — Month DD, YYYY

## Wins
- [Accomplishment or progress worth sharing]
- [Another win]

## In progress
- [What's underway and any useful context]

## Blockers
- [Anything slowing work that needs manager input or a decision]

## Goals check
- [Any goal that is off track, stalled, or needs a conversation]

## Asks
- [Specific request: a decision, an introduction, feedback, or support]
```

## Gotchas

- If the logs for the period are sparse, ask the user to recall what they
  worked on before generating the agenda — a thin agenda reads as a slow week.
- The "Asks" section is the most important for career growth. Prompt the user
  to think about what they need from their manager, not just what to report.
- When framing blockers or sensitive topics, use SBI as a soft guide (Situation,
  Behaviour, Impact): what happened, what was observed, and why it matters. This
  keeps feedback concrete and non-personal without requiring the user to follow
  a rigid script.
- Visibility work (cross-functional meetings, stakeholder interactions) often
  gets forgotten in 1-on-1s. Check for entries tagged `visibility` or
  `collaboration` in the logs and include them in Wins.
