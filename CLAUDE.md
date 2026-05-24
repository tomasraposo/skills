# Skills

Personal Claude Code skills plugin. Installed via `claude plugin add tomasraposo/skills`.

## Structure

```
skills/
  personal/     — tied to my setup, published in plugin.json
  in-progress/  — drafts not yet ready
```

Each skill = directory with `SKILL.md` (frontmatter `name:` + `description:`) plus optional reference files.

## Conventions

- `SKILL.md` is the entry point (not `skill.md`)
- Frontmatter `description:` drives model discovery — be specific
- Reference docs go alongside SKILL.md in the same directory
- Plugin manifest (`.claude-plugin/plugin.json`) lists published skill paths
