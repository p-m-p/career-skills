---
name: career-init
description: >
  Set up the career skills vault for the first time. Use this skill when the
  user wants to get started with career skills, when no configuration exists
  at ~/.career-skills.toml, or when another career skill has indicated that
  setup is required. Also triggers on "set up career skills", "initialise my
  career vault", or "get started with career tracking".
compatibility: Requires a writable filesystem. Creates Markdown files compatible with Obsidian and any text editor.
---

## Overview

This skill creates the configuration file and vault directory structure used
by all career skills. It only needs to be run once.

## Setup steps

1. **Check for existing config** — if `~/.career-skills.toml` already exists,
   read it and confirm the current settings with the user. Ask if they want to
   change anything. If nothing needs changing, stop here.

2. **Ask for the vault location** — suggest a sensible default for their
   platform (e.g. `~/Documents/career` on Mac/Linux,
   `C:\Users\<name>\Documents\career` on Windows). Let the user provide any
   absolute path they prefer.

3. **Write `~/.career-skills.toml`**:

```toml
vault = "/path/chosen/by/user"
```

4. **Create the vault directory structure**:

```
{vault}/
  goals/
  logs/
  brag/
  reviews/
  one-on-ones/
  promo/
```

5. **Confirm** — tell the user setup is complete and which skills are available
   to them: `perf-goals`, `work-log`, `brag-doc`.

## Gotchas

- On Windows, remind the user to use either forward slashes or escaped
  backslashes in the path (e.g. `C:/Users/name/Documents/career` or
  `C:\\Users\\name\\Documents\\career`).
- Do not overwrite an existing config without explicit confirmation from
  the user.
