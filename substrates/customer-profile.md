# Substrate: customer profile

> Synthetic example. Quillon Works is a fictional six-person studio that builds internal
> tools for operations teams. Every company, person and event below is invented.

Who buys from us, who gets value, and who leaves. Tracked so that qualification and
proposals stop relying on the founder's memory of the last good client.

---

## Ladder (load-bearing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding. Still context-checked. |

## What counts as a distinct source here (load-bearing)

A different customer account. Evidence can come from a call, a retro or a renewal
conversation, but it is counted by account.

What does not count: three calls with the same account; two departments of the same
company; a prospect who never bought (that evidence goes to `sales-objections.md`).

---

## Stable definition

The organisations that buy internal tooling from us, described by what they share at the
moment they buy and at the moment they renew or leave.

## Observable signals

- Who signs, and whether that person uses the tool.
- Whether a named internal owner exists by the second week.
- How the customer describes the problem in the first call, in their words.
- Renewal or expansion inside two quarters.

## Observed manifestations

### 2026-03-12 | A named internal owner by week two predicts renewal | tier: `auto-apply`

**Observation:** Accounts that name one internal owner for the tool by the end of week two
renew or expand. Accounts that leave ownership to "the team" do not.
**Falsifiable as:** An account with a named owner by week two that does not renew, or an
account with no owner that does.
**Sources:** 3
  - `retros/2026-03-10-juno-freight-dispatch-board.md` (customer: Juno Freight)
  - `raw/calls/2026-05-21-halden-renewal.md` (customer: Halden & Co)
  - `retros/2026-07-30-tarnwell-bakeries-stock-tool.md` (customer: Tarnwell Bakeries)
**Context cue:** Operations teams of 20 to 150 people buying a first internal tool. Not
tested on teams that already run several in-house tools.
**Actor:** mira-okafor
**Status updates:**
  - 2026-03-12: logged at `watch`
  - 2026-05-24: promoted to `suggest` (second account: Halden & Co)
  - 2026-08-02: promoted to `auto-apply` (third account: Tarnwell Bakeries)

### 2026-04-18 | The buyer who says "we tried a tool already" is the best fit | tier: `suggest`

**Observation:** Customers who open with a failed off-the-shelf tool get value faster than
customers buying their first tool, because they already know which step broke.
**Falsifiable as:** A customer with a failed prior tool whose time to first weekly use is
slower than the median.
**Sources:** 2
  - `raw/calls/2026-04-16-pellbrook-dental-intro.md` (customer: Pellbrook Dental Group)
  - `retros/2026-09-04-osprey-lane-lettings.md` (customer: Osprey Lane Lettings)
**Context cue:** Service businesses with front-desk or dispatch teams. Seen only where the
failed tool was abandoned, not where it is still half in use.
**Actor:** mira-okafor
**Status updates:**
  - 2026-04-18: logged at `watch`
  - 2026-09-06: promoted to `suggest` (second account: Osprey Lane Lettings)

### 2026-06-03 | Co-operatives take twice as long to sign | tier: `watch`

**Observation:** A member-owned co-operative needed two board cycles to approve a scope
that a privately owned firm of the same size approved in one meeting.
**Falsifiable as:** A co-operative that signs within one board cycle.
**Sources:** 1
  - `raw/calls/2026-06-02-vantor-grain-board-followup.md` (customer: Vantor Grain Co-op)
**Context cue:** One agricultural co-operative. Do not assume this for other member-owned
bodies yet.
**Actor:** mira-okafor
**Status updates:**
  - 2026-06-03: logged at `watch`

### 2026-02-20 | Founder-led firms renew faster | tier: `watch` (demoted)

**Observation:** Firms where the founder still runs operations renew faster than firms run
by a hired operations lead.
**Falsifiable as:** A founder-led firm that churns, or a manager-led firm that renews faster
than founder-led ones.
**Sources:** 2 supporting, 1 contradicting
  - `retros/2026-02-18-juno-freight-phase-one.md` (customer: Juno Freight, supports)
  - `raw/calls/2026-04-30-brackwater-clinics-renewal.md` (customer: Brackwater Clinics, supports)
  - `raw/calls/2026-08-14-halden-expansion.md` (customer: Halden & Co, contradicts: manager-led, expanded fastest of any account)
**Context cue:** Was seen in firms under 60 people. The contradiction came from a firm of
120, so the size boundary may be the real variable.
**Actor:** mira-okafor
**Status updates:**
  - 2026-02-20: logged at `watch`
  - 2026-05-02: promoted to `suggest` (second account: Brackwater Clinics)
  - 2026-08-16: contradicted by Halden & Co, demoted to `watch`. Flagged for rewrite: test
    "team size under 60" as the variable instead of "founder-led".

## Anti-patterns

- Qualifying on industry alone. The pattern so far follows team shape, not sector.
- Treating the person who signs as the person who will own the tool.

## Evolution

Early customers came through the founder's network and looked alike. As referrals widen,
expect `suggest` entries to meet more contradicting evidence. That is the ladder working.

## Cross-links

- `substrates/delivery-process.md` > "Kick-off without the daily user stalls week three"
- `substrates/sales-objections.md` > "Who will own this after you leave?"
- `learnings.md` > "Buying a better tool never fixes a team that keeps failing the same way"

## Growth Log

### 2026-09-06 | weekly synthesis | by synthesize-learnings (run for mira-okafor)

**Promoted:** "The buyer who says we tried a tool already" to `suggest`. Osprey Lane is a
different account from Pellbrook, so it counts. **Findings:** both accounts had abandoned
the earlier tool completely. I added that to the context cue rather than generalise past it.

### 2026-08-16 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Demoted:** "Founder-led firms renew faster", `suggest` to `watch`. Halden & Co is
manager-led and expanded faster than any founder-led account. **Findings:** the two
supporting accounts were both under 60 people and Halden is 120. The real variable may be
size. Proposed a rewrite as a fresh `watch` entry rather than editing this one in place.

### 2026-08-02 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Promoted:** "A named internal owner by week two predicts renewal" to `auto-apply` after
the Tarnwell Bakeries retro. Third distinct account. Now binding in qualification, for
operations teams of 20 to 150 buying a first tool.
