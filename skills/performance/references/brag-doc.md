# Brag Doc

A brag document synthesises work logs into a narrative of impact, grouped by
goal. It is not a diary — it should read like evidence. Output is stored at
`{vault}/brag/PERIOD.md` (e.g. `2025-H1.md`, `2025-Q3.md`).

Create `{vault}/brag/` if it does not exist.

## Generating a brag doc

1. **Establish the period** — ask if not already clear: Q1/Q2/Q3/Q4, H1/H2,
   full year, or a custom date range.

2. **Read the goals** — load the index at `{vault}/goals/YYYY.md` and read
   each individual goal file from `{vault}/goals/YYYY/` to understand titles
   and structure.

3. **Read the log files** — read all daily logs in `{vault}/logs/` within the
   period, in date order.

4. **Synthesise** — for each goal, collect all linked log entries and reframe
   them as accomplishments using STAR as a guiding lens (Situation, Action,
   Result): what was the context or challenge, what did the user do, and what
   was the outcome? Not every bullet needs all three elements, but the Result
   should always be present:
   - Lead with impact, not activity ("Reduced deploy time by 40%" not "Worked
     on the deployment pipeline")
   - Quantify where the logs include numbers; where they do not, ask the user
     if they have a metric before leaving it vague
   - Merge related entries into a single bullet rather than listing every log

5. **Draft the document** using the template below.

6. **Review with the user** before writing to disk. Ask if anything is missing
   or needs stronger framing.

7. **Write** to `{vault}/brag/PERIOD.md`.

## Output template

```markdown
---
period: [Q1 2025 / H1 2025 / 2025]
generated: YYYY-MM-DD
---

# Accomplishments: [Period]

## [Core Goal Title]
- [Accomplishment with impact framing]
- [Accomplishment with impact framing]

## [Another Core Goal Title]
- [Accomplishment]

## Growth & Visibility
- [Cross-functional work, new skills, or stakeholder relationships]
- [Work done outside core role that increased profile or scope]

---

## Summary

[2–3 sentences suitable for a self-assessment or sharing with a manager.
First person, professional tone, concrete and impact-focused.]

---

## Gaps

[Goals or periods where log coverage was sparse. Prompts the user to fill
in missing context before a review. Remove this section if there are no gaps.]
```

## Gotchas

- Visibility and growth work is often untagged or tagged inconsistently in logs.
  Scan all entries, not just those linked to a named goal, before writing the
  Growth & Visibility section.
- If log coverage is thin for some weeks, say so in the Gaps section rather than
  silently producing a thin doc. Better to prompt the user to fill in what they
  remember.
- The Summary section is the highest-value output. Make it concrete and
  impact-focused; cut filler phrases like "I contributed to" or "I helped with".
- Do not invent impact. If a log entry says "worked on X" with no outcome noted,
  ask the user for the outcome before upgrading it to "delivered X".
