# Career Skills

A set of [Agent Skills](https://agentskills.io) for managing your performance
goals, tracking daily work, and building career documents like brag docs,
self-assessments, and promotion cases.

Works with any agent that supports the Agent Skills standard, including
Claude Code, GitHub Copilot, Cursor, Gemini CLI, and others.

## Skills

| Skill | What it does |
|---|---|
| [`perf-goals`](./perf-goals/SKILL.md) | Create and manage yearly performance goals |
| [`work-log`](./work-log/SKILL.md) | Capture daily work notes linked to goals |
| [`brag-doc`](./brag-doc/SKILL.md) | Generate an accomplishment summary from work logs |
| [`review-prep`](./review-prep/SKILL.md) | Write a self-assessment for a performance review |
| [`one-on-one-prep`](./one-on-one-prep/SKILL.md) | Generate talking points for a manager 1-on-1 |
| [`promo-case`](./promo-case/SKILL.md) | Build a promotion case mapped to a leveling rubric |

## Installation

### Any Agent Skills compatible agent

```bash
npx skills add p-m-p/career-skills
```

### Claude Code

Add this repository as a plugin marketplace, then install:

```
/plugin marketplace add p-m-p/career-skills
/plugin install career-skills@p-m-p-career-skills
```

## How it works

The skills follow a simple cycle: set goals at the start of the year, log work
as you go, then synthesise that log into career documents when you need them.
The more consistently you log, the less effort everything else takes.

### 1. Set your goals

At the start of a review cycle, tell your agent what you're working toward.
The agent will help you shape goals that cover both your core role and areas
where you want to grow or increase your visibility — using OKR thinking as a
guide: a clear objective and measurable outcomes that tell you when you've
got there.

> "Help me set my performance goals for this year. My team is focused on
> reliability and I want to grow into more of a technical lead role."

Goals are saved to your vault and used as reference by every other skill.

### 2. Log as you go

The most important habit is capturing work while it's fresh. After a
meaningful piece of work — shipping something, unblocking a team, running
a cross-functional meeting — take thirty seconds to log it.

> "Log that I finished the payment retry logic today. It was blocking the
> iOS team and we'd had three incidents because of it."

The agent links the entry to your goals and prompts for the outcome if you
haven't mentioned one. Over time this builds a precise record that's almost
impossible to reconstruct from memory at review time. Log entries follow
STAR principles — capturing the situation, what you did, and the result —
so they're already shaped for use in review documents later.

### 3. Prep for 1-on-1s

Before each manager 1-on-1, ask your agent to pull together what you've been
working on. It reads your recent logs and surfaces wins, blockers, and anything
that needs a conversation — including goals that are drifting off track.

> "I've got a 1-on-1 tomorrow, what should I raise?"

This keeps your manager informed without you having to remember everything,
and creates a habit of surfacing asks — decisions you need, introductions,
feedback — rather than just reporting status.

### 4. Generate a brag doc each quarter

Every quarter or half-year, synthesise your logs into a brag document. This
is a structured record of your impact, grouped by goal, with raw activity
reframed into outcomes. It's the source material for everything else.

> "Write up my accomplishments for Q2."

The agent flags gaps where coverage is thin and asks for any outcomes you
didn't capture at the time. The result is a document you could share with
your manager or use verbatim in a self-assessment.

### 5. Prepare for performance reviews

When review season arrives, your brag doc does most of the work. The agent
uses it — alongside your goals — to write a self-assessment in the language
your company uses, with accomplishments framed using STAR (Situation, Action,
Result) so every claim is backed by evidence.

> "My performance review is next week, help me write my self-assessment."

If your company has a specific review form or rubric, share it and the agent
will adapt the output to match.

### 6. Build a promotion case

When you're ready to make a case for promotion, the agent maps your strongest
accomplishments to the criteria for the next level. It shows where the evidence
is strong, where it's thin, and what work would close the gaps before the next
cycle.

> "I want to make a case for promotion to staff engineer. Here's our leveling
> guide."

---

All output is plain Markdown stored in a vault folder of your choosing —
works great with [Obsidian](https://obsidian.md).
