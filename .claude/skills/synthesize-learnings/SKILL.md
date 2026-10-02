---
name: synthesize-learnings
description: Recount distinct sources for every entry in learnings.md and each substrate file, promote or demote by each file's own ladder, regenerate operating-rules.md, append Growth Log blocks, commit once per substrate and log the run. Triggers on "synthesize learnings", "run synthesis", "promote learnings", "regenerate operating rules", "weekly synthesis", "/synthesize-learnings".
---

# synthesize-learnings

Turns a pile of observations into rules the business has earned, and takes rules back
down when the evidence turns. This is the only skill that changes tiers.

## Inputs

- `learnings.md` (the master file) and every `substrates/*.md` file, except `_template.md`.
- Everything that arrived since the last run, per `log/synthesis-cursor.json`:
  new files in `raw/`, new retros, new entries in `log/feedback.jsonl` and
  `log/decisions.jsonl`, and new entries appended to any substrate.
- If the cursor file is missing or its `last_run` is `null`, treat this as the first run
  and read everything.

Paths are the defaults for this repo. If your brain keeps these files elsewhere, change the
paths here once and leave the procedure alone.

## Outputs

- Updated tiers and status-update lines in `learnings.md` and each substrate.
- A regenerated `operating-rules.md`.
- One Growth Log block in each file that changed.
- One git commit per changed file (master counts as one).
- One line in `log/runs.jsonl`, and an updated `log/synthesis-cursor.json`.

## Procedure

1. **Read the cursor.** Load `log/synthesis-cursor.json`. Collect every input newer than
   `last_run`.

2. **Read each file's own rules first.** Before touching a file, read its ladder table and
   its definition of a distinct source. Those live in the file, not here. Do not carry one
   file's definition into another. A customer-profile file may count different customers;
   a delivery file may count different completed projects. Use what the file says.

3. **Attach new evidence.** For each new input, find the entries it supports or contradicts.
   Record it under the entry's sources (support) or status updates (contradiction), with the
   path and the passage. If it supports nothing existing and is worth keeping, it becomes a
   new entry at `watch` (follow the `log-observation` skill's format).

4. **Recount distinct sources** for every entry that received evidence, using that file's
   definition. Repeats from the same source collapse to one. When unsure whether two items
   are distinct under the definition, count them as one and say so in the Growth Log.

5. **Apply the ladder.**
   - Promote when the distinct count reaches the next threshold in that file's table.
   - Demote one tier when a distinct source contradicts the entry. One contradiction, one
     tier. A `watch` entry that is contradicted stays at `watch` with the contradiction
     recorded, and is flagged for the owner to retire or rewrite.
   - Never jump two tiers in one run, up or down.
   - Every change appends a dated status-update line to the entry.

6. **Route across files.** An entry in `learnings.md` whose tag matches a substrate gets
   copied into that substrate at `watch`, with a cross-reference both ways. The substrate
   then counts it by its own definition, which may be stricter. A substrate entry that turns
   out to be general can be proposed back to `learnings.md` at `watch`. Context cues travel
   with every copy.

7. **Regenerate `operating-rules.md`.** Rebuild it from every `suggest` and `auto-apply`
   entry across all files, grouped by tag, each with its context cue and a link back to
   where it was earned. Before overwriting, compare the file with what the last run wrote.
   If someone hand-edited it, stop and ask. Do not overwrite silently.

8. **Append Growth Log blocks**, newest on top, to each file that changed. Say what moved,
   why it moved, and what you were unsure about. A run that changed nothing still appends
   one line to the master Growth Log: "No movement. Sources reviewed: ...".

9. **Commit once per file.** Example messages:
   `synthesis: learnings.md (+2 watch, 1 promoted)`,
   `synthesis: substrates/sales-objections.md (1 demoted)`,
   `synthesis: operating-rules.md regenerated`.
   One commit per file means a bad promotion can be reverted without undoing the rest.

10. **Log the run** to `log/runs.jsonl` (one line, actor required) and write the new
    cursor.

## Quality gate (hard fail)

- A promotion where the distinct count was not recomputed from the file's own definition.
- A rule in `operating-rules.md` without a context cue.
- A demotion with no Growth Log entry.
- An entry with no actor.
- An entry that is not falsifiable being promoted. Flag it instead.
- A silent overwrite of a hand edit.

## Log line

```json
{"ts":"2026-10-03T09:00:00Z","actor":"your-name-or-agent","skill":"synthesize-learnings","inputs":{"cadence":"weekly","since":"2026-09-26T09:00:00Z","new_inputs":7},"outputs":{"files_changed":3,"new_watch":2,"promotions":{"learnings.md":1,"substrates/sales-objections.md":0},"demotions":{"substrates/sales-objections.md":1},"rules_in_digest":9,"commits":4},"decision":"regenerated","notes":""}
```

## Cursor file

```json
{"last_run": "2026-10-03T09:00:00Z", "actor": "your-name-or-agent"}
```

## Failure modes

- **Counting mentions instead of sources.** One enthusiastic meeting can mention a pattern
  ten times. It is still one source.
- **Borrowing a looser definition.** The master file may count different documents while a
  substrate counts different completed projects. Never promote a substrate entry on the
  master's definition.
- **Softening a contradiction.** If the evidence contradicts the entry, demote. Do not
  rewrite the entry so the contradiction no longer applies, unless you also record that
  you narrowed it and why.
