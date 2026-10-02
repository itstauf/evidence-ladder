# learnings.md

The master file of what this business has learned. Append-only between synthesis runs.
Every entry carries a tier, a count of distinct sources, a context cue, an actor and tags.

Copy this file to `learnings.md` in your brain (or wherever your skills expect it), then
delete this paragraph. Everything below the line is load-bearing: the skills read their
thresholds and source definition from here, not from their own instructions.

---

## Promotion ladder (load-bearing, read before editing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding rule. Still context-checked before it binds. |

**What counts as a distinct source in this file:** a different source document. That means
a different file in `raw/`, a different project retro, a different recorded decision, or
feedback from a different person. Twenty repeats inside one meeting count as one.
Edit this definition to fit your business. See `docs/what-counts-as-a-source.md`.

**Thresholds live here, in this file.** The synthesis skill reads them from this table. If
you want a stricter ladder (say, 4 sources for `auto-apply`), change the table, not the skill.

**Demotion is symmetric.** Contradicting evidence from a distinct source demotes the entry
one tier and writes a Growth Log entry. Nothing is deleted. A demoted entry keeps its history.

**Context check on apply.** Before a rule binds a decision, the current situation is
matched against the entry's context cue. If the cue does not match, the rule does not bind.
Binding is never unconditional.

**Entries must be falsifiable.** If you cannot name what would prove an entry wrong, it is
an opinion, not a learning. Rewrite it until you can.

---

## Tags

Tags are yours to define. A skill reads `operating-rules.md` by tag, so pick tags that match
the decisions your skills make. A starter set:

- `[CUSTOMER]` who buys, who stays, who churns
- `[SALES]` objections, deal shape, what moves a deal forward
- `[DELIVERY]` how work gets done, handoffs, where projects stall
- `[PRICING]` how offers are framed and accepted (no figures in entries, link to the source)
- `[TEAM]` hiring, roles, how the team itself works
- `[MARKET]` what is changing outside the business
- `[BRAND]` voice and messaging that lands or misfires
- `[OPS]` how the brain and its tools behave

If a tag matches a substrate file in `substrates/`, the synthesis run also copies the entry
into that substrate at `watch`, with a cross-reference. See `docs/choosing-substrates.md`.

---

## Entry format

```
## YYYY-MM-DD | Short title | tier: `watch` | tags: [TAG] [TAG]

**Learning:** What we now believe, in one to three sentences.
**Falsifiable as:** What observation would prove this wrong.
**Distinct sources:** N
  - `raw/calls/YYYY-MM-DD-short-name.md` (the relevant passage)
  - `retros/YYYY-MM-DD-project-name.md`
**Context cue:** The conditions under which this was earned. A rule only binds where
  the cue matches.
**Actor:** who logged it (a person, or the name of the agent run).
**Attributed to:** (optional) who originally said it, if you are recording on their behalf.
**Status updates:**
  - YYYY-MM-DD: promoted to `suggest` (new source: ...)
  - YYYY-MM-DD: contradicted in `raw/...`, demoted to `watch`
**Routing:** (optional) substrate files this entry was copied to.
```

The tier in the heading is the only tier. When synthesis changes it, it also appends a
status update line, so the heading and the history never disagree.

---

<!-- Entries go here, newest at the bottom of this section. -->

---

# Growth Log

The narrative companion to `log/runs.jsonl`. Each synthesis run that changes this file
appends a dated block, newest on top. The machine log says what happened; this says why.

Block format:

```
## YYYY-MM-DD | synthesis (weekly | monthly | on-event) | by {actor}

**Sources reviewed:** ...
**New entries:** {title} [tags], at `watch`, from {source}
**Promotions:** {title}, `watch` to `suggest`, new source: {source}
**Demotions:** {title}, `auto-apply` to `suggest`, contradicted in {source}
**Routing:** {title} copied to `substrates/{file}.md`
**Findings:** a short paragraph on what changed in what you believe, and why.
```

<!-- Growth Log blocks go here, newest on top. -->
