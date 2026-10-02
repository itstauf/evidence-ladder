# Substrate: delivery process

> Synthetic example. Quillon Works is a fictional studio. Every company, person and project
> below is invented.

How projects actually run once signed: where they stall, which handoffs fail, and which
habits keep them on track. Tracked so that project plans carry what the last projects
taught, not what we hoped.

This substrate promotes slowly on purpose. A project takes weeks, and it only counts once
its retro is written. Most entries here will sit at `watch` for months.

---

## Ladder (load-bearing)

| Tier | Threshold | Behaviour |
|---|---|---|
| `watch` | 1 distinct source | Recorded only. Never applied. |
| `suggest` | 2 distinct sources | Applied, marked `(under review)`. |
| `auto-apply` | 3 or more distinct sources | Binding. Still context-checked. |

## What counts as a distinct source here (load-bearing)

A different completed project, counted only once its retro exists in `retros/`.

What does not count: an in-flight project (log it, but it does not count until the retro);
two phases of one project for the same customer; a stand-up where the whole team agreed.

---

## Stable definition

The sequence from signed scope to a tool in daily use: kick-off, discovery, build, handover,
and the first month after.

## Observable signals

- Days from kick-off to first daily use.
- Who attended kick-off, by role.
- Number of scope changes after week two.
- Whether the handover runbook was opened in the month after.

## Observed manifestations

### 2026-03-11 | Kick-off without the daily user stalls week three | tier: `auto-apply`

**Observation:** When the person who will use the tool every day is absent from kick-off,
week three produces a rework request that resets the build.
**Falsifiable as:** A project where the daily user missed kick-off and week three passes
without rework, or one where they attended and rework still hits.
**Sources:** 3
  - `retros/2026-03-10-juno-freight-dispatch-board.md` (project: Juno dispatch board)
  - `retros/2026-06-20-brackwater-clinics-intake.md` (project: Brackwater intake)
  - `retros/2026-07-30-tarnwell-bakeries-stock-tool.md` (project: Tarnwell stock tool)
**Context cue:** Tools replacing a manual daily routine. Not tested on reporting tools used
weekly by managers.
**Actor:** mira-okafor
**Status updates:**
  - 2026-03-11: logged at `watch`
  - 2026-06-22: promoted to `suggest` (second project retro: Brackwater)
  - 2026-08-01: promoted to `auto-apply` (third project retro: Tarnwell)

### 2026-06-21 | A shared glossary in week one cuts scope changes | tier: `suggest`

**Observation:** Writing down the customer's own words for their objects and statuses in
week one led to fewer scope changes after week two.
**Falsifiable as:** A project with a week-one glossary and more than the usual scope changes.
**Sources:** 2
  - `retros/2026-06-20-brackwater-clinics-intake.md` (project: Brackwater intake)
  - `retros/2026-09-04-osprey-lane-lettings.md` (project: Osprey Lane lettings desk)
**Context cue:** Customers with their own internal vocabulary for statuses. Seen in
healthcare intake and lettings.
**Actor:** mira-okafor
**Status updates:**
  - 2026-06-21: logged at `watch`
  - 2026-09-06: promoted to `suggest` (second project retro: Osprey Lane)

### 2026-09-25 | Handover runbooks go unread unless walked through live | tier: `watch`

**Observation:** The written runbook for the Halden scheduling tool was not opened in the
month after handover. Questions came by message instead.
**Falsifiable as:** A runbook delivered without a live walk-through that is opened in the
first month.
**Sources:** 1
  - `retros/2026-09-24-halden-scheduling.md` (project: Halden scheduling)
**Context cue:** One project, one customer with a high-turnover front desk.
**Actor:** mira-okafor
**Status updates:**
  - 2026-09-25: logged at `watch`

### 2026-04-02 | Fixed two-week sprints suit every project | tier: `watch` (demoted)

**Observation:** Two-week build sprints with a demo at each end kept projects on schedule.
**Falsifiable as:** A project where two-week sprints caused a slip a shorter cadence would
have avoided.
**Sources:** 2 supporting, 1 contradicting
  - `retros/2026-03-10-juno-freight-dispatch-board.md` (project: Juno dispatch board, supports)
  - `retros/2026-06-20-brackwater-clinics-intake.md` (project: Brackwater intake, supports)
  - `retros/2026-07-30-tarnwell-bakeries-stock-tool.md` (project: Tarnwell stock tool,
    contradicts: a seasonal deadline needed weekly demos, and the first two-week sprint
    shipped the wrong screen)
**Context cue:** Projects without a hard external deadline. The title claimed "every
project", which the Tarnwell retro disproved.
**Actor:** mira-okafor
**Status updates:**
  - 2026-04-02: logged at `watch`
  - 2026-06-22: promoted to `suggest` (second project retro: Brackwater)
  - 2026-08-01: contradicted by Tarnwell retro, demoted to `watch`. Flagged: the title is
    too broad to survive. Rewrite as a narrower entry with the deadline condition in the cue.

## Anti-patterns

- Counting a project before its retro because it "felt" finished.
- Letting a retro be written by the person who ran the project, alone. Add one other voice.

## Evolution

A studio of six finishes perhaps one project a month. Three distinct sources therefore
means a quarter or more. That pace is the price of honesty here, and it is fine.

## Cross-links

- `substrates/customer-profile.md` > "A named internal owner by week two predicts renewal"
- `learnings.md` > "Score the changes that held, not the ones that were announced"

## Growth Log

### 2026-09-25 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**New:** "Handover runbooks go unread" at `watch`, from the Halden retro. **Findings:** the
Halden project also had two scope changes, but no week-one glossary was written, so it
neither supports nor contradicts the glossary entry. Left untouched.

### 2026-09-06 | weekly synthesis | by synthesize-learnings (run for mira-okafor)

**Promoted:** "A shared glossary in week one cuts scope changes" to `suggest`.

### 2026-08-01 | on-event synthesis | by synthesize-learnings (run for mira-okafor)

**Promoted:** "Kick-off without the daily user stalls week three" to `auto-apply`.
**Demoted:** "Fixed two-week sprints suit every project", `suggest` to `watch`, on the same
Tarnwell retro. **Findings:** one retro moved two entries in opposite directions. That is
expected. A source supports what it supports and contradicts what it contradicts.
