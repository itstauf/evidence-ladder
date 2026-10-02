# Substrate: sales objections

> Synthetic example. Quillon Works is a fictional studio. Every company, person and deal
> below is invented.

The objections buyers raise, what sits underneath them, and which answers move a deal
forward. Tracked so that proposals answer the real objection, not the one we expect.

---

## Ladder (load-bearing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding. Still context-checked. |

## What counts as a distinct source here (load-bearing)

A different deal, with a different buying group. A deal is one proposal cycle, won or lost.

What does not count: the same objection raised by four people on one call; two proposals to
the same buying group in the same quarter; an objection we expected but nobody raised.

---

## Stable definition

What a buyer says, or does, that slows or stops a deal, recorded in their words, plus what
we tried and what happened next.

## Observable signals

- The first objection raised on the second call, verbatim.
- Who raises it (the signer, the daily user, finance, IT).
- Whether the deal moves within two weeks of our answer.

## Observed manifestations

### 2026-02-26 | "Who will own this after you leave?" is the real price objection | tier: `auto-apply`

**Observation:** When a buyer says the project is too expensive, the next question they ask
is about ownership after handover. Answering ownership first (named owner, handover week,
runbook) moves the deal. Discounting does not.
**Falsifiable as:** A deal that closes after a discount with no ownership answer, or a deal
that stalls after a clear ownership answer.
**Sources:** 3
  - `raw/calls/2026-02-25-juno-freight-proposal-review.md` (deal: Juno Freight phase two)
  - `raw/calls/2026-04-09-pellbrook-dental-second-call.md` (deal: Pellbrook front desk)
  - `raw/calls/2026-07-17-tarnwell-bakeries-negotiation.md` (deal: Tarnwell stock tool)
**Context cue:** Buyers who have not run an internal tool before. Not seen with buyers who
have an in-house developer.
**Actor:** mira-okafor
**Status updates:**
  - 2026-02-26: logged at `watch`
  - 2026-04-11: promoted to `suggest` (second deal: Pellbrook)
  - 2026-07-19: promoted to `auto-apply` (third deal: Tarnwell)

### 2026-05-14 | IT security review is raised before price in clinics | tier: `suggest`

**Observation:** In healthcare buyers, the first blocking question is where data is stored,
and it arrives before any discussion of cost.
**Falsifiable as:** A healthcare deal where cost is raised first, or where data location is
never raised.
**Sources:** 2
  - `raw/calls/2026-05-13-brackwater-clinics-it-call.md` (deal: Brackwater patient intake)
  - `raw/calls/2026-08-28-pellbrook-dental-records.md` (deal: Pellbrook records lookup)
**Context cue:** Healthcare providers handling patient records. Pellbrook appears twice in
this file, but these are different deals with different buying groups (front desk vs
records team), so both count.
**Actor:** mira-okafor
**Status updates:**
  - 2026-05-14: logged at `watch`
  - 2026-08-30: promoted to `suggest` (second deal: Pellbrook records lookup)

### 2026-09-18 | "Can we start with one team?" signals a champion without a budget | tier: `watch`

**Observation:** A buyer asking to pilot with a single team had support from one manager
and no budget line. The pilot was approved; the full rollout was not.
**Falsifiable as:** A single-team pilot request where a budget line already exists.
**Sources:** 1
  - `raw/calls/2026-09-17-osprey-lane-pilot-ask.md` (deal: Osprey Lane lettings desk)
**Context cue:** One deal, one lettings agency. Twelve mentions of "pilot" in that call
still make one source.
**Actor:** mira-okafor
**Status updates:**
  - 2026-09-18: logged at `watch`

### 2026-03-05 | A live demo beats a written proposal for operations buyers | tier: `suggest` (demoted)

**Observation:** Deals where we showed a working prototype in the second call closed faster
than deals where we sent a written proposal first.
**Falsifiable as:** A deal where a demo-first approach stalls while a proposal-first deal of
similar shape closes.
**Sources:** 3 supporting, 1 contradicting
  - `raw/calls/2026-03-04-halden-demo.md` (deal: Halden scheduling, supports)
  - `raw/calls/2026-04-22-juno-freight-yard-demo.md` (deal: Juno yard board, supports)
  - `raw/calls/2026-06-11-tarnwell-demo.md` (deal: Tarnwell ordering, supports)
  - `raw/calls/2026-09-09-vantor-grain-board-decline.md` (deal: Vantor Grain, contradicts:
    the board declined the demo and asked for a written paper before it would meet)
**Context cue:** Privately owned firms where one operations lead can say yes. The
contradiction came from a board-governed co-operative.
**Actor:** mira-okafor
**Status updates:**
  - 2026-03-05: logged at `watch`
  - 2026-04-24: promoted to `suggest` (second deal: Juno yard board)
  - 2026-06-13: promoted to `auto-apply` (third deal: Tarnwell ordering)
  - 2026-09-11: contradicted by Vantor Grain, demoted to `suggest`. Context cue narrowed
    proposal: "single decision-maker" may be the boundary. Needs one more board-governed
    deal to confirm.

## Anti-patterns

- Answering the objection we rehearsed instead of the one the buyer raised.
- Logging an objection from our own pre-call notes as if a buyer said it.

## Evolution

Objections shift as the buyer gets more familiar with internal tools. Expect ownership
objections to fade and integration objections to grow.

## Cross-links

- `substrates/customer-profile.md` > "A named internal owner by week two predicts renewal"
- `learnings.md` > "Buying a better tool never fixes a team that keeps failing the same way"

## Growth Log

### 2026-09-18 | weekly synthesis | by synthesize-learnings (run for mira-okafor)

**New:** "Can we start with one team?" at `watch`. **Findings:** the call transcript
repeated the word "pilot" a dozen times. Counted once, as the definition says.

### 2026-09-11 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Demoted:** "A live demo beats a written proposal", `auto-apply` to `suggest`. Vantor Grain
is a distinct deal and contradicts it. **Findings:** all three supporting deals had a single
decision-maker. The rule is now applied `(under review)` and only where one person can say
yes. Proposal-drafting skills reading `[SALES]` will see the change on the next
regeneration of `operating-rules.md`.

### 2026-08-30 | weekly synthesis | by synthesize-learnings (run for mira-okafor)

**Promoted:** "IT security review is raised before price in clinics" to `suggest`. Checked
the Pellbrook evidence against the definition: different deal, different buying group, so
it counts. Noted the judgment call in the entry.
