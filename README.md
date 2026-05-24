# skills

Workflow tools for [Claude Code](https://claude.ai/code).

## Install

```sh
npx skills@latest add tomasraposo/skills
```

Or manually via Claude Code CLI:

```sh
claude plugin marketplace add tomasraposo/skills
claude plugin install skills@skills
```

Skills are invoked as `/skills:<skill-name>` (e.g. `/skills:label`).

## Skills

| Skill | Description |
|---|---|
| [label](skills/productivity/label/SKILL.md) | Label sessions with context — upserts into project-scoped `session-labels.json` keyed by session name |
