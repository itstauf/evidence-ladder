---
name: log-observation
description: Capture a new observation as a watch-tier entry with its source and context cue, in learnings.md or the right substrate file. Never promotes. Triggers on "log this observation", "note this pattern", "add a learning", "I noticed that", "record this as a hunch", "/log-observation".
---

# log-observation

Writes down something you noticed, with enough attached that a future run can tell whether
it happened again somewhere else. One observation is a note. It is never applied.

## Inputs

- The observation, in the user's words.
- The source: a file path (a call note, an email saved to `raw/`, a retro). If there is no
  file, ask for one or save the user's account to `raw/notes/YYYY-MM-DD-short-name.md`
  first, then cite that.
- Who is logging it (actor), and who said it if that is someone else.

## Output

One new entry appended to `learnings.md` or to one file in `substrates/`, at `watch`.
One line in `log/runs.jsonl`.

## Procedure

1. **Check for a match first.** Search `learnings.md` and `substrates/` for an existing
   entry that says the same thing. If one exists, do not create a duplicate. Add this source
   under the existing entry's sources as "pending recount" and tell the user that the next
   synthesis run will decide whether it counts as a new distinct source.

2. **Pick the file.** If the observation is clearly about one substrate (a customer type,
   an objection, a delivery step), write it there. Otherwise write it to `learnings.md`.
   Use that file's entry format.

3. **Make it falsifiable.** Rewrite vague claims until you can fill the "Falsifiable as"
   line. "Clients like workshops" becomes "Teams under 30 people book a second workshop
   within a quarter more often than teams over 30." If you cannot get there, log it anyway
   and mark it `(needs sharpening)` in the title.

4. **Write the context cue.** Where was this seen? Team size, industry, stage, who was in
   the room, what was going on. The cue is what stops a rule from binding in the wrong place
   later. Be specific even when it feels narrow.

5. **Set tier `watch`, distinct sources 1.** This skill never sets a higher tier, even if
   the user says "I've seen this loads of times". Ask for those other sources and log each
   one. Synthesis does the counting.

6. **Log the run.**

```json
{"ts":"2026-10-03T14:10:00Z","actor":"your-name-or-agent","skill":"log-observation","inputs":{"source":"raw/calls/2026-10-03-intro-call.md"},"outputs":{"file":"substrates/sales-objections.md","entry":"Security review is raised before price","tier":"watch","matched_existing":false},"decision":"logged","notes":""}
```

## Quality gate

- No source path, no entry.
- No actor, no entry.
- No context cue, no entry.
- Never a tier above `watch`.
- No real names of people or companies in files that leave your machine. Keep them in
  `raw/`, which is gitignored by default here.
