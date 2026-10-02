# The four honesty rules

A ladder with three rungs is easy to build. Keeping it honest is the work. These four rules
are what stop it from becoming a list of things I happen to believe this week.

## 1. Thresholds live in the data file, not the skill

The table that says "2 sources for `suggest`, 3 for `auto-apply`" sits at the top of
`learnings.md` and of every substrate file. The synthesis skill reads it from there.

Why: the procedure should not decide how much evidence a part of the business needs. A
hiring substrate might want 4 sources for a binding rule, because a bad hiring rule is
expensive. A content substrate might be happy with 3. If the threshold is buried in the
skill, every substrate gets the same one, and changing it means editing the procedure.

What breaks without it: someone tweaks the skill "just for this run" and every file promotes
on the new number, silently.

## 2. Distinct-source counting is defined per substrate, and the definitions differ

Each file states its own unit: different customers, different deals, different completed
projects. The master file is looser (different documents or different people's feedback),
because it is where hunches start.

Why: independence means different things in different parts of a business. Three notes from
one project are three documents but one project. See `what-counts-as-a-source.md`.

What breaks without it: a pattern from one big client fills every substrate at once and
looks like a market truth.

## 3. Demotion is symmetric

Supporting evidence from a distinct source moves an entry up one tier. Contradicting
evidence from a distinct source moves it down one tier. Every demotion writes a Growth Log
entry that says what contradicted it and what that might mean.

Why: a system that only promotes is a system that only collects agreement. The value of a
rule is that it can lose.

What breaks without it: rules accumulate, nobody remembers why they were earned, and the
first time one fails, the team stops trusting all of them.

Notes:
- Nothing is deleted. A demoted entry keeps its full history.
- One contradiction, one tier. Never jump two tiers in either direction in one run.
- A contradicted `watch` entry stays at `watch`, with the contradiction recorded, and is
  flagged for the owner to rewrite or retire.

## 4. Context check on apply

Every entry carries a context cue: where it was earned. Before a rule binds a decision, the
skill checks the current situation against that cue. If they do not match, the rule does
not bind, however many sources it has.

Why: "three sources" means three sources in a particular kind of situation. A rule earned
with small private firms says nothing yet about co-operatives with boards.

What breaks without it: a rule that was true in one setting gets applied everywhere, fails
somewhere it never claimed to cover, and gets wrongly demoted.

## And one entry requirement: falsifiable

Every entry names the observation that would prove it wrong. "Clients value trust" cannot be
contradicted, so it can never be demoted, so it should never be promoted. Rewrite it until
it can lose.
