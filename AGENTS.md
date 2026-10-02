# AGENTS.md

Instructions for any coding agent (Cursor, Codex, Claude Code, others) working in a brain
that uses the evidence ladder.

## What this is

A three-tier ladder that promotes business patterns by counting distinct sources:
`watch` (1, never applied), `suggest` (2, applied "under review"), `auto-apply` (3 or more,
binding after a context check). Contradicting evidence demotes one tier.

## Files

| File | Role | Who edits it |
|---|---|---|
| `learnings.md` (from `learnings.template.md`) | master file of entries + Growth Log | append via `log-observation`; tiers change only via `synthesize-learnings` |
| `substrates/*.md` (from `substrates/_template.md`) | one part of the business each, own source definition | same as above |
| `operating-rules.md` (from `operating-rules.template.md`) | regenerated digest by tag | only `synthesize-learnings`; never by hand |
| `log/runs.jsonl` | one line per run, with `actor` | every skill |
| `log/synthesis-cursor.json` | timestamp of the last synthesis | `synthesize-learnings` |

## Procedures

Follow these files as written. They are plain markdown and do not depend on Claude Code:

- `.claude/skills/log-observation/SKILL.md`: capture a new observation at `watch`.
- `.claude/skills/synthesize-learnings/SKILL.md`: recount, promote, demote, regenerate.

## Rules you must not break

1. Read thresholds and the source definition from the top of each file. Do not use defaults.
2. Count distinct sources by that file's unit. Repeats within one source count once.
3. Demote one tier on contradicting evidence from a distinct source, and log it.
4. Before applying any rule, check its context cue against the current situation.
5. Never write a tier above `watch` for a new entry.
6. Never hand-edit `operating-rules.md`.
7. Every log line and every entry carries an actor.
8. Do not invent sources, customers, quotes or numbers.

When reading rules to inform other work, read `operating-rules.md` by tag rather than the
whole learnings file.
