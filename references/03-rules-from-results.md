# Turning Grades Into Rules

Step 5, and then back around to step 3.

This is the step that separates a voice guide from a one-time writeup. Everything the human said while grading is raw material. None of it is useful until it becomes a rule that applies to writing nobody has produced yet.

## The extraction

```
Here are my graded results: [PASTE JSON]

For each comment, extract the underlying rule, stated generally enough that
it applies to writing you have not seen yet.

- Where I criticized something, write the rule that prevents it.
- Where I praised something, write the rule that reproduces it.
- Where the same issue shows up in three or more comments, mark it as a
  primary rule and say so.
- Where a new rule conflicts with an existing rule in the guide, do not
  quietly pick one. Show me both and ask which wins.

Then give me the full updated guide, followed by a changelog of what you
added, changed, and removed.
```

## Generalize, but not too far

The failure mode on both sides is easy to hit.

**Too specific** is a rule that only fires on the exact sentence that produced it. "Do not write 'in neither one did I have enough runway'" is not a rule, it is a note about one email.

**Too general** is a rule that swallows things the human likes. "Avoid metaphors" is not what they said. They said this metaphor was used outside the domain they use it in.

The version that works sits in between and names the principle plus its boundary:

> Metaphors have to match the domains he actually uses them in. "Runway" means time for an initiative or a company, never time left in a conversation. When unsure, use the plain word.

That rule fires on metaphors this guide has never seen, and it leaves the metaphors he does use alone.

## Weight by repetition, not by heat

A comment written in frustration is not more informative than a calm one. It is just louder.

Sort the comments by how many times the same underlying issue appears:

- **Three or more:** a primary rule. Put it high in the guide, state it flatly, and expect it to matter on every draft.
- **Two:** a real rule. Include it.
- **One:** hold it. Write it down in the changelog as a watch item, but be cautious about promoting a single reaction into a standing constraint. If it shows up again next round, it earns its place.

Single-instance comments are where guides accumulate junk. A rule that fires constantly on the strength of one Tuesday afternoon reaction will quietly degrade every future draft.

## Conflicts

New rules will contradict old ones. This is normal and it is information, not a mistake.

Most conflicts are actually missing context. "Keep it short" and "explain your reasoning" only conflict until you notice one applies to logistics and the other to a proposal. The fix is usually a condition, not a deletion:

> Short by default. Two to four sentence paragraphs, no preamble. Exception: when the piece is making an argument the reader has not heard before, the reasoning gets its own paragraph and does not get compressed.

**Gate:** never resolve a conflict on your own. Show the human both rules, say where you think the boundary is, and let them draw it. They are the only one who knows which they actually meant.

## Overcorrection in round two

Expect it. A rule written to stop one irritating habit almost always stomps on something adjacent that they liked.

The classic version: they complain that a draft was too formal, a rule gets written to loosen the register, and the next round produces something too casual for a hiring manager. The rule was not wrong. It was missing the audience condition.

This shows up immediately in round two and is easy to fix once visible, which is why the second pass matters more than it sounds like it should.

## Running the next pass

Regenerate the drafts against the updated guide and grade again. Either works:

- **Same pairs.** Cleaner comparison, since only the guide changed. But they have seen these situations before and their memory of the last round leaks in.
- **Fresh pairs.** Better test of generalization, which is what you actually care about. Costs more setup.

Fresh pairs are the better choice if there is enough corpus left. Keep the earlier results files. `changelog.md` plus the round-by-round result files are the record of what actually changed and whether it helped.

## When to stop

**Stop when the comments stop producing new rules.** Not when the score hits a number.

The signal is that a round produces comments that are all restatements of rules already in the guide, or preferences so mild the human has trouble articulating them. At that point the guide has absorbed what this corpus can teach it.

Chasing a score past that point is overfitting to one judge on one afternoon, and the guide gets worse, not better, while the number goes up.

Next, if the human wants corpus advice for a specific genre: `04-genre-notes.md`.
