# Choosing substrates

A substrate is one part of your business you decide to track on its own ladder. Each gets
its own file in `substrates/`, its own definition of a source and its own Growth Log.

You do not need any to start. `learnings.md` alone works. Add a substrate when you notice
that a group of entries keeps sharing a tag and needs a stricter, different way of counting.

## What makes a good substrate

- **A decision reads from it.** If no skill or person would look up its rules before acting,
  do not track it. Customer profile feeds qualification. Sales objections feed proposals.
- **It has a natural unit of independence.** Customers, deals, projects, hires, sends. If you
  cannot name the unit, it is a tag, not a substrate.
- **Evidence arrives often enough to move.** A substrate that gets one source a year will
  never leave `watch`. That may still be worth it for high-stakes areas, but know it going in.
- **It is yours, not a textbook's.** "Leadership" is too broad. "Why our second projects
  stall" is a substrate.

## Start with three or fewer

Every substrate you add is a file someone has to feed. I would rather see three files with
real entries than ten files with seed text. The examples in this repo use three:
customer profile, sales objections, delivery process.

## Common substrates by business type

| Business | Candidates | Unit of a source |
|---|---|---|
| Services studio or consultancy | customer profile, sales objections, delivery process | account, deal, completed project |
| SaaS | churn reasons, onboarding friction, feature requests | churned account, new account cohort, requesting account |
| Agency | brief quality, client feedback rounds, pitch outcomes | brief, project, pitch |
| Retail or e-commerce | returns reasons, supplier issues, promotion results | order, supplier, promotion |
| Recruiting | candidate drop-off, hiring-manager objections, placement retention | candidate, requisition, placement |
| Clinic or practice | intake friction, no-show causes, referral sources | patient journey (anonymised), week, referrer |

## The honest caveat

The stricter the unit, the slower the substrate. Counting "different completed projects"
means a rule needs three finished projects that all point the same way. In my own business
the master learnings file has earned its first rules, and my business substrates have barely
started compounding. That is by design. Do not loosen the unit to make it move faster.

## Agent-guided setup prompt

Paste this into Claude Code, a Claude or ChatGPT Project, or any agent with this repo loaded.

```
I want to set up substrates for the evidence ladder in this repo. Read
docs/choosing-substrates.md, docs/what-counts-as-a-source.md and substrates/_template.md first.

Then interview me, one question at a time:
1. What does my business sell, to whom, and how does a typical piece of work run start to end?
2. Which three decisions do I make most often where I wish I had better evidence?
3. For each decision: what would count as one independent piece of evidence? Push back if my
   answer would let one meeting, one customer or one project count more than once.
4. Roughly how often does that evidence arrive?

After the interview, propose at most three substrates. For each give: a name, the decision
it feeds, the unit of a distinct source, what does NOT count, and how long the first
promotion to auto-apply is likely to take at my pace. Flag any that will promote too slowly
to be useful and say so plainly.

When I approve, create each file from substrates/_template.md, fill the ladder table and the
source definition, and add a matching tag to learnings.md if one is missing. Do not invent
any entries. Log the run to log/runs.jsonl with my name as actor.
```
