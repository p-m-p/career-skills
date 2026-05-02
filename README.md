# Career Skills

A set of [Agent Skills](https://agentskills.io) for managing your performance
goals, tracking daily work, and building career documents like brag docs,
self-assessments, and promotion cases.

Works with any agent that supports the Agent Skills standard, including
Claude Code, GitHub Copilot, Cursor, Gemini CLI, and others.

## Skills

| Skill | What it does |
|---|---|
| [`career-init`](./career-init/SKILL.md) | First-time setup — creates config and vault directory structure |
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
set everything up from there. All output is plain Markdown, stored in a vault
folder of your choosing — compatible with [Obsidian](https://obsidian.md),
VS Code, or any text editor.

## Installation

### Using the skills CLI

Install all skills at once:

```bash
npx skills add p-m-p/career-skills
```

Install a single skill:

```bash
npx skills add p-m-p/career-skills/tree/main/career-init
```

### Claude Code

Copy the skill directories to your personal skills folder:

```bash
git clone https://github.com/p-m-p/career-skills.git
cp -r career-skills/career-init career-skills/perf-goals career-skills/work-log \
      career-skills/brag-doc career-skills/review-prep career-skills/one-on-one-prep \
      career-skills/promo-case ~/.claude/skills/
```

Skills in `~/.claude/skills/` are available across all your projects. Claude
activates them automatically when relevant, or you can invoke any skill directly
with `/skill-name` (e.g. `/work-log`).

### VS Code (GitHub Copilot)

Copy the skill directories into your project's `.agents/skills/` folder:

```bash
git clone https://github.com/p-m-p/career-skills.git
mkdir -p .agents/skills
cp -r career-skills/career-init career-skills/perf-goals career-skills/work-log \
      career-skills/brag-doc career-skills/review-prep career-skills/one-on-one-prep \
      career-skills/promo-case .agents/skills/
```

### Claude.ai

1. Download this repository as a zip file
2. Go to **Settings > Features** in Claude.ai
3. Upload each skill directory as a zip file

### Other agents

See the [Agent Skills client list](https://agentskills.io/clients) for
installation instructions for Cursor, Gemini CLI, OpenCode, and others.

## Vault structure

Your vault will look like this once you've used the skills for a while:

```
your-vault/
  goals/
    2025.md          # yearly performance goals
  logs/
    2025-01-15.md    # daily work logs
    2025-01-16.md
  brag/
    2025-H1.md       # half-year accomplishment summaries
  reviews/
    2025.md          # self-assessments
  one-on-ones/
    2025-01-20.md    # 1-on-1 agendas
  promo/
    2025.md          # promotion cases
```
