---
name: promo-case
description: >
  Build a promotion or leveling case by mapping accomplishments to a role
  rubric or leveling criteria. Use this skill when the user wants to make a
  case for promotion, needs to demonstrate they are operating at the next
  level, wants to identify gaps before a promotion cycle, or is preparing
  materials to share with a manager or review committee. Also triggers on
  "promotion case", "promo doc", "leveling up", "next level", "am I ready
  for promotion", or "evidence for promotion".
compatibility: Requires read access to the career vault. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

A promotion case maps your strongest accomplishments to the criteria your
company uses to evaluate readiness for the next level. It is evidence-based,
not a list of responsibilities — reviewers want to see that you already operate
at the target level, not just that you want to.

Output is stored at `{vault}/promo/YYYY.md`.

## Configuration

Read vault location from `~/.career-skills.toml`. If this file does not exist:
1. Ask the user where they want to store their career files (suggest `~/career`
   on Mac/Linux or `C:\Users\<name>\Documents\career` on Windows)
2. Write `~/.career-skills.toml` with their chosen path
3. Create `{vault}/promo/` if it does not exist
4. Then proceed

## Building the case

1. **Gather the leveling criteria** — ask the user to provide the rubric or
   criteria for their target level. This might be:
   - A company leveling guide
   - A job description for the next level
   - A list of expectations their manager shared
   If none is available, ask the user to describe what "next level" looks like
   in their company and use that as a framework.

2. **Read the goals and brag doc** — load the index at `{vault}/goals/YYYY.md`
   and individual goal files from `{vault}/goals/YYYY/`. Then load the most
   recent brag document from `{vault}/brag/`, or read logs directly if no
   brag doc exists.

3. **Map accomplishments to criteria** — for each criterion at the target level:
   - Find the strongest evidence from logs or brag doc
   - Note whether the evidence is strong, partial, or absent
   - Flag gaps where the user has not yet demonstrated the criterion

4. **Draft the promotion case** using the template below.

5. **Review with the user** — ask:
   - Are there accomplishments not in the logs that should be included?
   - Are any gaps a surprise, or already known?
   - Is there a specific timeline (e.g. next promotion cycle)?

6. **Write** to `{vault}/promo/YYYY.md`.

## Output template

```markdown
---
current-level: [e.g. L4 / Senior / IC3]
target-level: [e.g. L5 / Staff / IC4]
generated: YYYY-MM-DD
---

# Promotion Case: [Current Level] → [Target Level]

## Summary

[2–3 sentences: why you are ready, the headline evidence, and any context
about timing or the review cycle.]

## Evidence by criterion

### [Criterion name, e.g. "Technical impact"]
**Evidence:** [Specific accomplishment with impact]
**Strength:** Strong / Partial / Gap

### [Another criterion, e.g. "Cross-functional influence"]
**Evidence:** [Specific accomplishment]
**Strength:** Strong / Partial / Gap

---

## Gaps and plan

[For each gap, note what work would close it and by when. A promotion case
with honest gaps and a credible plan is stronger than one that ignores them.]

---

## Suggested narrative

[A short paragraph, suitable for sharing with a manager or sponsor, that
makes the case in plain language without referencing the rubric directly.]
```

## Gotchas

- Promotion cases are lost on vague evidence. "Led a project" is weak;
  "Led the migration of X to Y, reducing latency by 40% and unblocking the
  mobile team" is strong. Push for specifics.
- Gaps are not disqualifying — every promotion case has them. The value is
  in making gaps visible so they can be addressed before the cycle closes.
- The "Suggested narrative" section is for the manager or sponsor who will
  advocate for the user in the room. Make it short, clear, and free of
  jargon.
- If the user does not have a rubric, the case is still useful — frame it
  around behaviours and impact at the next level based on what the user
  describes as the expectations.
