# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

This repo IS the **opensquad** framework — a Node.js CLI that scaffolds a multi-agent orchestration setup into a user's project (Claude Code, Codex, Cursor, VS Code+Copilot, or Antigravity). It is published to npm as `opensquad` and consumed via `npx opensquad <command>`.

The repo also dogfoods opensquad on itself: `_opensquad/`, `skills/`, and `squads/` at the root are this project's own opensquad install. **Do not confuse these with the source files that get distributed to users — those live under `templates/` and `skills/`.**

## Common commands

```bash
npm test                              # node --test tests/**/*.test.js
node --test tests/init.test.js        # run a single test file
node --test --test-name-pattern "init creates" tests/init.test.js  # run a single test by name

npm run version                       # sync templates/_opensquad/.opensquad-version with package.json version (auto-runs on `npm version`)

# Manual smoke-test of the CLI in a sandbox dir
node bin/opensquad.js init <target-dir>
node bin/opensquad.js update <target-dir>

# Dashboard (separate workspace)
cd dashboard && npm run dev           # vite dev server
cd dashboard && npm run build         # tsc -b && vite build
```

There is no lint script and no CI config in this repo — `npm test` is the only check.

## Architecture

### CLI entry → src/ modules

`bin/opensquad.js` is a thin parseArgs dispatcher. Each subcommand maps to one module in `src/`:

- `init.js` — `npx opensquad init`. Prompts for language/IDE, copies `templates/` → target, installs all bundled skills, runs `npm install` and `npx playwright install chromium`, writes `_opensquad/_memory/preferences.md`. The "common templates" pass copies everything under `templates/` *except* `ide-templates/`, and skips files that already exist (so re-running init is non-destructive). The "ide templates" pass then copies `templates/ide-templates/<ide>/` for each selected IDE on top.
- `update.js` — `npx opensquad update`. Re-copies templates while honoring `PROTECTED_PATHS` (`_opensquad/_memory`, `_opensquad/_investigations`, `agents`, `squads`) which are never overwritten. Also auto-installs newly-bundled non-MCP skills that the user doesn't have yet. Reads saved IDE list from `preferences.md` to know which `ide-templates/<ide>/` to refresh.
- `skills-cli.js` / `skills.js` — `install`/`uninstall`/`update`. Skills are folders under `skills/` containing a `SKILL.md` with YAML frontmatter (`name`, `type: mcp|script|hybrid`, `version`, `env`, localized `description_pt-BR` / `description_es`). Installing copies the whole skill folder to `<target>/skills/<id>/`.
- `agents-cli.js` / `agents.js` — same shape as skills but for agents. Source agents live in a top-level `agents/` directory (declared in `package.json` `files` but currently not present in this checkout — added at publish time or in a feature branch). Each agent is a single `AGENT.md` file copied to `<target>/agents/<id>.agent.md`.
- `i18n.js` — loads `src/locales/{en,es,pt-BR}.json`. Language label → code map: `'Português (Brasil)' → pt-BR`, `'English' → en`, `'Español' → es`. `t(key, vars)` falls back to English if key missing.
- `prompt.js` — wraps `@inquirer/{input,select,checkbox}`.
- `readme/README.md` — the trilingual README that gets written into every initialized project (NOT this repo's own README.md).

### Templates layout (what gets distributed)

```
templates/
  _opensquad/                 # core opensquad runtime (copied as-is)
    .opensquad-version        # version string, kept in sync via `npm run version`
    core/
      architect.agent.yaml    # the Architect agent definition (~58KB)
      runner.pipeline.md      # Pipeline Runner instructions
      skills.engine.md        # how skills are dispatched at runtime
      prompts/sherlock.prompt.md
      best-practices/         # ~25 markdown guides for content formats
    config/playwright.config.json
    _investigations/          # protected on update
  squads/.gitkeep             # users put their squads here
  dashboard/                  # full Vite+React+Pixi dashboard project
  ide-templates/
    claude-code/   → CLAUDE.md, .mcp.json, .claude/skills/opensquad/SKILL.md
    codex/         → AGENTS.md, .agents/skills/opensquad/SKILL.md
    cursor/        → .cursorignore, .cursor/{mcp.json,rules/opensquad.mdc}
    antigravity/   → .antigravity/rules.md, .agent/workflows/opensquad.md
    vscode-copilot/→ .github/prompts/opensquad.prompt.md, .vscode/{mcp.json,settings.json}
  package.json                # the package.json shipped to users (has playwright dep)
```

The IDE-specific entry-point files (`CLAUDE.md`, `AGENTS.md`, `.cursor/rules/opensquad.mdc`, etc.) all wire up the same opensquad skill — they're translations of the same instructions for each IDE's convention.

### Important: when editing `templates/`

- **Files in `templates/_opensquad/core/` are the runtime brain of every installed squad.** Editing `architect.agent.yaml`, `runner.pipeline.md`, or `skills.engine.md` changes behavior for all users on the next `npx opensquad update`. Treat them as production code.
- **The user-facing `CLAUDE.md` lives at `templates/ide-templates/claude-code/CLAUDE.md`**, not at the repo root. The root `CLAUDE.md` (this file) is for framework development only.
- The `.opensquad-version` file under `templates/_opensquad/` must match `package.json` version. The `version` npm script does this automatically — never bump version without it.

### Bundled skills (`skills/`)

Skills under `skills/` are bundled with the package and auto-installed by `init.js` via `installAllSkills`. `update.js` only auto-installs *new* non-MCP skills (MCP and skills with required `env` are opt-in via `npx opensquad install <name>`).

`opensquad-skill-creator` is special-cased — `listInstalled` excludes it because it's a meta-skill always present in the source.

Skill IDs are validated against `/^[a-z0-9][a-z0-9-]*$/`.

### Tests

`tests/` uses `node:test` (no test framework dependency). Tests create temp dirs with `mkdtemp`, run `init({ _skipPrompts: true, _ides: [...], _language: '...' })`, and assert on the resulting filesystem. Use the same pattern when adding tests for new init/update behavior.

The `_skipPrompts` flag also skips `npm install` and `playwright install` — use it for any test that exercises init.

### Distribution model

`package.json` `files` ships only `bin/`, `src/`, `agents/`, `skills/`, `templates/`. Anything not under those paths (including this `CLAUDE.md`, `tests/`, `docs/`, `dashboard/` at the root) is dev-only and not published.

## Conventions

- ES modules everywhere (`"type": "module"`); use `node:` prefix on built-ins.
- Node 20+ (`engines` enforces this).
- User-facing strings go through `t()` — add the key to all three locale files in `src/locales/`.
- The IDE list in `init.js` is the source of truth for supported IDEs; adding one means adding `templates/ide-templates/<ide>/`, a step-instructions branch in `init()`, and locale strings.
- Don't edit the consumer-facing `_opensquad/` and `skills/` at the repo root expecting them to ship — they're this project's own dogfood install. Edit `templates/_opensquad/` and the source `skills/` (which is both the dev install and the bundled source — they're the same directory because we publish the dev skills).

## Design docs

`docs/plans/` contains historical design + implementation plans dated `YYYY-MM-DD-<feature>-{design,plan}.md`. Read the relevant plan before significantly changing skills registry, run folders, checkpoints, IDE onboarding, formats system, or sherlock investigator.

## Git

Develop on the branch specified by the task instructions. Don't push to `main` directly.
