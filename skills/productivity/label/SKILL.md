---
name: label
description: "Label the current session (upsert into ~/.claude project session-labels.json, keyed by session name). Requires /rename first. Usage: /label <label-text>"
---

Upsert `$ARGUMENTS` as a label into `~/.claude/projects/<project>/session-labels.json`, keyed by session name.

Empty `$ARGUMENTS` → print `usage: /label <label-text>` and stop.

Strip matching outer quotes from `$ARGUMENTS` (`"…"` or `'…'`).

Run ONE Bash call:

1. Match `$CLAUDE_CODE_SESSION_ID` against `~/.claude/sessions/*.json` → extract `.name`, `.cwd`, `.startedAt`.
2. No `.name` → error, require `/rename` first.
3. `labels_file="$HOME/.claude/projects/$(echo "$PWD" | tr '/' '-')/session-labels.json"`
4. Read existing file (or `{}`), upsert `.[name] = {sessionId, label, labeledAt, startedAt, cwd, branch}`.
5. Write back (pretty-printed). Print: `labeled: <name> -> <labels_file>`

No narration before or after the Bash call.
