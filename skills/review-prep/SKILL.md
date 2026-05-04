---
name: review-prep
description: >
  Write a self-assessment narrative for a performance review cycle, drawing on
  work logs and goals. Use this skill when the user is preparing for a
  performance review, needs to write a self-assessment, wants to summarise
  their year for a review form, or is drafting a performance statement. Also
  triggers on "self-assessment", "annual review", "mid-year review",
  "performance write-up", or "what to say in my review".
compatibility: Requires read access to the career vault. Output is Markdown, compatible with Obsidian and any text editor.
---

## Overview

A performance review self-assessment translates your work into the language your
company uses to evaluate performance. Unlike a brag document (which captures
everything), a self-assessment is selective — it presents the strongest evidence
for your performance rating and any claims about your impact or level.

Output is stored at `{vault}/reviews/YYYY.md` or `{vault}/reviews/YYYY-midyear.md`.

## Configuration

Read vault location from `~/.career-skills.toml`. If this file does not exist:
1. Ask the user where they want to store their career files (suggest `~/career`
   on Mac/Linux or `C:\Users\<name>\Documents\career` on Windows)
2. Write `~/.career-skills.toml` with their chosen path
3. Create `{vault}/reviews/` if it does not exist
4. Then proceed

## Generating a self-assessment

1. **Establish the review period and context** — ask if not already clear:
   - Review period (full year, mid-year, Q-based)
   - Any specific questions or sections in the company's review form
   - The user's target rating or level claim, if they have one

2. **Read the goals** — load the index at `{vault}/goals/YYYY.md` and read
   each individual goal file from `{vault}/goals/YYYY/` to understand what
   the user committed to at the start of the year.

3. **Read or generate the brag doc** — if `{vault}/brag/` contains a document
   for this period, use it as the source material. If not, read the log files
   directly from `{vault}/logs/` and synthesise accomplishments inline.

4. **Draft the self-assessment** — write in first person, professional tone.
   Use STAR (Situation, Action, Result) as the underlying structure for each
   accomplishment: what was the context or challenge, what did you do, and what
   was the outcome? Apply it with judgment — not every sentence needs all three
   elements, but every claim needs a result. For each goal:
   - State whether it was met, exceeded, or partially met
   - Cite specific evidence from logs or the brag doc
   - Quantify impact where possible
   - Be honest about anything that fell short — reviewers notice omissions

5. **Review with the user** before writing. Ask:
   - Are there accomplishments missing from the logs that should be included?
   - Is there a specific rating or level claim to build toward?
   - Does the company form have specific sections to match?

6. **Write** to `{vault}/reviews/PERIOD.md`.

## Output template

```markdown
---
period: [2025 / 2025-H1]
generated: YYYY-MM-DD
---

# Performance Self-Assessment: [Period]

## Summary

[2–3 sentences capturing the overall shape of the year: what you focused on,
your headline impact, and any growth. This is the first thing a reviewer reads.]

## [Core Goal Title]

[1–3 paragraphs covering what you set out to do, what you achieved, and the
impact. Use specific examples. If the goal was exceeded, say why. If it fell
short, briefly note what happened and what you learned.]

## [Another Core Goal Title]

[Same structure.]

## Growth & Visibility

[Highlight cross-functional work, new skills, and contributions beyond your
core role. These matter for level and promotion decisions.]

## Looking ahead

[Optional: 1–2 sentences on what you're focused on in the next period. Shows
self-awareness and forward momentum.]
```

## Gotchas

- Self-assessments are not the place to be modest. Passive framing ("I was
  involved in...") undersells impact. Use active, direct language.
- Match the language in your company's review rubric. If the rubric says
  "drives results" and "builds relationships", use those phrases where earned.
- If the user's logs are thin for part of the period, ask what happened in
  those weeks before writing — don't let gaps become unearned omissions.
- The "looking ahead" section is optional but strengthens reviews that feed
  into promotion decisions.
