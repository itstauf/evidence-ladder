# learnings.md (synthetic example)

> Every company, person and event in this file is invented. Quillon Works is a fictional
> six-person studio that builds internal tools for operations teams. The rules header is the
> same as `learnings.template.md` and is shortened here.

## Promotion ladder (load-bearing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding. Still context-checked. |

**Distinct source in this file:** a different source document (call note, retro, recorded
decision) or feedback from a different person. Repeats inside one document count once.

Tags in use: `[CUSTOMER]` `[SALES]` `[DELIVERY]` `[PRICING]` `[TEAM]` `[MARKET]` `[BRAND]` `[OPS]`

---

## 2026-02-12 | Buying a better tool never fixes a team that keeps failing the same way | tier: `auto-apply` | tags: [CUSTOMER] [DELIVERY]

**Learning:** When a team has abandoned two or more tools at the same step, the next tool
fails at that step too, unless the step itself is redesigned first.
**Falsifiable as:** A team that abandoned two tools at the same step, adopts a third with no
process change, and is still using it after a quarter.
**Distinct sources:** 3
  - `raw/calls/2026-02-11-juno-freight-intro.md` (two dispatch apps dropped at driver check-in)
  - `retros/2026-06-20-brackwater-clinics-intake.md` (two intake forms dropped at insurance check)
  - `raw/calls/2026-08-19-kestrel-row-housing-discovery.md` (two ticketing tools dropped at triage)
**Context cue:** Operations teams of 20 to 150 people with a repeated abandonment at the same
step. Does not bind when the earlier tools failed for unrelated reasons (vendor closed,
merger).
**Actor:** mira-okafor
**Status updates:**
  - 2026-02-12: logged at `watch`
  - 2026-06-22: promoted to `suggest` (second source: Brackwater retro)
  - 2026-08-21: promoted to `auto-apply` (third source: Kestrel Row discovery call)
**Routing:** `substrates/customer-profile.md`, `substrates/delivery-process.md`

---

## 2026-03-02 | Proposals that name the daily user get signed faster | tier: `auto-apply` | tags: [SALES]

**Learning:** A proposal that names the person who will use the tool daily, and describes
their day before and after, is signed in fewer rounds than one written for the signer.
**Falsifiable as:** A proposal naming the daily user that needs more revision rounds than our
median.
**Distinct sources:** 3
  - `raw/calls/2026-03-01-halden-proposal-feedback.md`
  - `raw/calls/2026-05-06-pellbrook-dental-signoff.md`
  - `log/feedback.jsonl` line from theo-vance, 2026-07-09
**Context cue:** Proposals for tools that replace a manual daily routine.
**Actor:** mira-okafor
**Status updates:**
  - 2026-03-02: logged at `watch`
  - 2026-05-08: promoted to `suggest`
  - 2026-07-10: promoted to `auto-apply`

---

## 2026-04-15 | Weekly check-in calls beat status emails for small customers | tier: `suggest` | tags: [DELIVERY]

**Learning:** For customers under 30 people, a fifteen-minute weekly call surfaces blockers
a week earlier than a written status email.
**Falsifiable as:** A small-customer project where a blocker first appeared in an email reply.
**Distinct sources:** 2
  - `retros/2026-04-14-osprey-lane-phase-one.md`
  - `retros/2026-09-04-osprey-lane-lettings.md`
**Context cue:** Customers under 30 people. Note: both sources are from one customer, which
counts as two documents here but would count as one in `substrates/delivery-process.md`.
**Actor:** theo-vance
**Status updates:**
  - 2026-04-15: logged at `watch`
  - 2026-09-06: promoted to `suggest`

---

## 2026-05-20 | Fixed-scope offers outsell time-and-materials for first projects | tier: `suggest` | tags: [PRICING] [SALES]

**Learning:** Buyers on a first project with us choose a fixed-scope offer over an hourly one
when both are shown side by side.
**Falsifiable as:** A first-project buyer who picks hourly when both are offered.
**Distinct sources:** 2
  - `raw/calls/2026-05-19-tarnwell-options-call.md`
  - `decisions/2026-08-12-offer-shape.md`
**Context cue:** First projects only. Repeat customers not yet observed.
**Actor:** mira-okafor
**Status updates:**
  - 2026-05-20: logged at `watch`
  - 2026-08-13: promoted to `suggest`

---

## 2026-01-28 | Case studies with screenshots get more replies than case studies with quotes | tier: `suggest` (demoted) | tags: [BRAND]

**Learning:** Outbound emails linking to a case study with product screenshots get more
replies than ones linking to a case study built around a customer quote.
**Falsifiable as:** A send where the quote-led version gets more replies at similar volume.
**Distinct sources:** 3 supporting, 1 contradicting
  - `raw/outbound/2026-01-27-january-send.md`
  - `raw/outbound/2026-03-30-march-send.md`
  - `raw/outbound/2026-05-28-may-send.md`
  - `raw/outbound/2026-09-15-september-send.md` (contradicts: quote-led version won clearly)
**Context cue:** Sends to operations leads. The September send went to finance leads, which
may be the real difference.
**Actor:** theo-vance
**Status updates:**
  - 2026-01-28: logged at `watch`
  - 2026-03-31: promoted to `suggest`
  - 2026-05-29: promoted to `auto-apply`
  - 2026-09-16: contradicted by September send, demoted to `suggest`. Audience difference
    noted; not used to explain the contradiction away.

---

## 2026-06-30 | Customers who ask for an export button in week one are planning to leave | tier: `watch` | tags: [CUSTOMER]

**Learning:** An early request to export all data signals a team that does not expect to keep
the tool.
**Falsifiable as:** A customer who asked for full export in week one and renewed.
**Distinct sources:** 1
  - `raw/calls/2026-06-29-vantor-grain-week-one.md`
**Context cue:** One co-operative. Could equally be a governance requirement there.
**Actor:** mira-okafor
**Status updates:**
  - 2026-06-30: logged at `watch`

---

## 2026-08-05 | Hiring a second developer before a second designer slowed delivery | tier: `watch` | tags: [TEAM]

**Learning:** Adding build capacity without design capacity moved the bottleneck to design
review and did not shorten projects.
**Falsifiable as:** A quarter after a developer hire where average project length fell.
**Distinct sources:** 1
  - `decisions/2026-08-04-q3-hiring-review.md`
**Context cue:** A studio under ten people where one designer reviews everything.
**Actor:** mira-okafor
**Status updates:**
  - 2026-08-05: logged at `watch`

---

## 2026-09-22 | Regional logistics firms are buying earlier in the year | tier: `watch` | tags: [MARKET]

**Learning:** Logistics buyers who used to start projects after their peak season are now
asking to start before it.
**Falsifiable as:** Next year's logistics inquiries arriving after peak season again.
**Distinct sources:** 1
  - `raw/calls/2026-09-21-juno-freight-planning.md`
**Context cue:** One regional freight firm. A single customer's calendar is not a market.
**Actor:** mira-okafor
**Status updates:**
  - 2026-09-22: logged at `watch`

---

# Growth Log

## 2026-09-22 | weekly synthesis | by synthesize-learnings (run for mira-okafor)

**Sources reviewed:** 4 new call notes, 1 outbound report.
**New entries:** "Regional logistics firms are buying earlier" [MARKET], at `watch`.
**Findings:** quiet week. One market hunch, deliberately left at `watch` with a cue that says
how thin it is.

## 2026-09-16 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Demotions:** "Case studies with screenshots get more replies", `auto-apply` to `suggest`.
The September send is a distinct source and the quote-led version won.
**Findings:** the audience changed (finance leads, not operations leads). That is a candidate
explanation, not a reason to skip the demotion. The rule now shows as `(under review)` in
`operating-rules.md` under `[BRAND]`.

## 2026-08-21 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Promotions:** "Buying a better tool never fixes a team that keeps failing the same way",
`suggest` to `auto-apply`. Third distinct source: Kestrel Row discovery call.
**Routing:** tagged for `substrates/customer-profile.md` and `substrates/delivery-process.md`.
Those files count by customer and by completed project, so a copy starts at the bottom of
their own ladders. (In this example the substrate files carry it as a cross-link only, to
keep them short.)
