# Walkthrough: one hunch, eight months, up and down the ladder

> Synthetic. Quillon Works, its people and its customers are invented. This follows a single
> entry in `substrates/sales-objections.md` from a passing remark to a binding rule, and then
> back down when the evidence turned.

## 1. The hunch (no file yet)

March. Mira Okafor, who runs the studio, comes off a call with Halden & Co and says to her
colleague: "Showing them the prototype did more than any proposal ever has."

That is a hunch. It lives in her head. If she forgets it, nothing is lost but also nothing is
learned. If she acts on it as a rule, she is acting on one call.

## 2. The note: `watch`

She runs the `log-observation` skill.

```
/log-observation Showing a working prototype in the second call moved the Halden deal faster
than a written proposal would have. Source: raw/calls/2026-03-04-halden-demo.md
```

The skill checks for an existing entry (none), sharpens the claim until it can be proven
wrong, asks for a context cue, and writes:

```
### 2026-03-05 | A live demo beats a written proposal for operations buyers | tier: `watch`

**Observation:** Deals where we showed a working prototype in the second call closed faster
than deals where we sent a written proposal first.
**Falsifiable as:** A deal where a demo-first approach stalls while a proposal-first deal of
similar shape closes.
**Sources:** 1
  - `raw/calls/2026-03-04-halden-demo.md` (deal: Halden scheduling)
**Context cue:** Privately owned firms where one operations lead can say yes.
**Actor:** mira-okafor
```

At `watch`, nothing changes in how the studio sells. The proposal skill does not see it.

## 3. A second deal: `suggest`

April. Juno Freight, a different deal with a different buying group, goes the same way.
Mira logs it; the skill finds the existing entry and adds the source as "pending recount".

The weekly `synthesize-learnings` run reads the substrate's own rule: a distinct source is a
different deal. Halden scheduling and Juno yard board are different deals. Count: 2.

```
  - 2026-04-24: promoted to `suggest` (second deal: Juno yard board)
```

`operating-rules.md` is regenerated. Under `[SALES]` it now says:

```
### A live demo beats a written proposal for operations buyers | tier: `suggest` | tags: [SALES]

**Rule:** Offer a working prototype in the second call before sending a written proposal.
**Context cue:** Privately owned firms where one operations lead can say yes.
**Sources:** 2 distinct. Earned in: `substrates/sales-objections.md`
```

The proposal skill now suggests a demo, and its output says `(under review)` next to it.
Mira can ignore it. She mostly does not.

## 4. What did not count

June. On a single demo call with Tarnwell Bakeries, four people say some version of "the demo was
what sold it". Twenty repeats in one meeting still count as one. The count goes from 2 to 3
because Tarnwell is a third distinct deal, not because four people agreed.

## 5. The rule: `auto-apply`

Two days later, synthesis recounts: three distinct deals.

```
  - 2026-06-13: promoted to `auto-apply` (third deal: Tarnwell ordering)
```

Now the rule binds. The proposal skill plans a demo-first second call by default, without
the `(under review)` mark, but only after it checks the context cue against the deal in front
of it. A buyer with a procurement committee does not match "one operations lead can say yes",
so the rule does not bind there.

## 6. The contradiction: demoted

September. Vantor Grain, a member-owned co-operative, declines the demo outright. Its board
wants a written paper before it will meet at all. The deal stalls until the paper arrives.

This is a distinct deal, and it contradicts the entry. Demotion is symmetric: one
contradiction, one tier.

```
  - 2026-09-11: contradicted by Vantor Grain, demoted to `suggest`. Context cue narrowed
    proposal: "single decision-maker" may be the boundary. Needs one more board-governed
    deal to confirm.
```

The Growth Log says why, in plain words:

```
### 2026-09-11 | on-event synthesis | by synthesize-learnings

**Demoted:** "A live demo beats a written proposal", `auto-apply` to `suggest`. Vantor Grain
is a distinct deal and contradicts it. **Findings:** all three supporting deals had a single
decision-maker. The rule is now applied `(under review)` and only where one person can say yes.
```

`operating-rules.md` is regenerated again, and the rule reappears under `[SALES]` marked
`(under review)`.

## What the run left behind

| Before (March) | After (September) |
|---|---|
| A remark after a good call | An entry with four dated sources, one of them against it |
| No way to tell if it was true | A falsifiable claim and a named boundary (single decision-maker) |
| Would have been applied everywhere, or forgotten | Applied where it was earned, under review, and waiting for the next board-governed deal |

Two things are worth noticing. The rule was never deleted; it was demoted with its history
intact. And the contradiction was not explained away. It was written down, and it sharpened
the context cue. That is the job.

The full entry, with all its status lines, is in `../substrates/sales-objections.md`.
