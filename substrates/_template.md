# Substrate: {name}

One part of the business you chose to track. This file compounds on its own, with its own
definition of a source and its own Growth Log. Copy this template to
`substrates/{name}.md` and fill the two load-bearing blocks before adding any entry.

---

## Ladder (load-bearing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding. Still context-checked. |

Change the numbers if this substrate needs a stricter ladder. The synthesis skill reads
them from here.

## What counts as a distinct source here (load-bearing)

{One sentence. Name the unit. "A different customer account." "A different deal." "A
different completed project, counted only once its retro is written."}

What does not count: {the usual traps for this substrate. Repeats inside one meeting.
Two people from the same team. The same client across two projects in one quarter.}

See `docs/what-counts-as-a-source.md` before you settle this.

---

## Stable definition

{What this part of the business is, in two or three sentences. Rarely changes.}

## Observable signals

{What you can actually see or hear that tells you something about it. Evolves.}

- {signal}

## Observed manifestations

{Entries, oldest first. Each one dated, tiered, sourced, with a context cue.}

### YYYY-MM-DD | {short title} | tier: `watch`

**Observation:** {what happened, falsifiable}
**Falsifiable as:** {what would prove it wrong}
**Sources:** 1
  - `{path}` ({unit of counting, e.g. customer, deal, project})
**Context cue:** {where it was seen and where it should not be assumed to apply}
**Actor:** {who logged it}
**Status updates:**
  - YYYY-MM-DD: logged at `watch`

## Anti-patterns

{What this looks like when it is going wrong.}

## Evolution

{How this part of the business changes as it matures.}

## Cross-links

- `learnings.md` > {entry}
- `substrates/{other}.md` > {entry}

## Growth Log

{Newest on top. One block per synthesis run that changed this file.}

### YYYY-MM-DD | synthesis | by {actor}

**New:** ... **Promoted:** ... **Demoted:** ... **Findings:** ...
