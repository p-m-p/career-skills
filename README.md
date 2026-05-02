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

## Getting started

Once installed, just talk to your agent naturally. The skills activate
automatically when relevant:

> "I want to set up my performance goals for this year"

> "Log that I finished the API refactor today — it unblocked the mobile team"

> "Write up my accomplishments for H1"

> "I've got a 1-on-1 with my manager tomorrow, help me prep"

On first use, the agent will ask where you want to store your career files and
set everything up from there. All output is plain Markdown — works great with
[Obsidian](https://obsidian.md).

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


