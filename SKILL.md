---
name: voice-guide-kit
description: Build and validate a written voice guide so an AI assistant can draft in a person's own voice for one specific kind of writing (email, cover letters, text messages, long-form posts, internal memos). Use when someone wants their assistant to "write like me" or "sound like me", is tired of rewriting AI drafts by hand, says drafts "don't sound like me", or asks to audit their own writing style. Runs a five-step loop: pick one genre, audit a corpus, draft blind from situation briefs, grade blind in a preference test, then turn the grades into rules. Spans multiple sessions and expects two or three passes.
---

# Voice Guide Kit

A voice guide written from a person's samples is a guess. This skill turns that guess into something measured, by drafting blind against their real writing and letting them grade the pairs without knowing which is which.

## Who does what

You do the reading, drafting, and rule writing. The human picks the genre, supplies the samples, and does every bit of the grading.

You never grade your own drafts. If you find yourself deciding which version is better, stop and hand it to them.

## The loop

```
0. Pick one genre  ->  1. Gather corpus  ->  2. Write the guide
                                                    |
        5. Rules from grades  <-  4. Grade blind  <-  3. Draft blind
                    |
                    +--> back to 3 for the next pass
```

Two or three passes is normal. The first guide is always wrong in ways nobody could predict from the samples alone, which is the reason the test exists.

## State

Keep everything under `voice-guide/<genre>/` in the working directory:

```
voice-guide/cover-letters/
  guide.md              the current voice guide
  corpus/               the human's real samples
  briefs.md             situation briefs, one per test pair
  pairs.json            test pairs for the grading tool
  results-round-1.json  graded output from the tool
  changelog.md          what each pass added, changed, removed
```

**At the start of every session, read this directory first.** Which files exist tells you which step is next. Do not restart the loop from the beginning because the human said something vague like "let's work on my voice." Check the state, then say where things stand and what the next step is.

## Gates

Stop and get the human's input at each of these. Do not carry on past them alone.

1. **Genre.** They name exactly one. Do not accept "email and cover letters."
2. **Corpus.** Show them what you excluded and why before you read anything.
3. **Candidates to drop.** The audit produces a list of habits they may not want kept. They decide each one.
4. **Grading.** Entirely theirs. You only produce the pairs.
5. **Rule conflicts.** When a new rule contradicts an existing one, show both and ask which wins.

## Step detail

Load the reference for the step you are on, not all of them at once.

| Step | Reference |
|---|---|
| 0, 1, 2: genre, corpus, audit | `references/01-corpus-and-audit.md` |
| 3, 4: briefs, drafting, grading | `references/02-blind-test.md` |
| 5: turning grades into rules | `references/03-rules-from-results.md` |
| Corpus advice for a specific genre | `references/04-genre-notes.md` |

## The grading tool

The blind preference test runs in a browser. Use the hosted copy, which needs no download:

**https://claywaters13.github.io/voice-guide-kit/assets/voice-test.html**

Or open `assets/voice-test.html` locally. Both are the same file and both run entirely in the browser.

You produce `pairs.json`, they open the tool and paste it in, they take the test, and they paste the results back to you. The tool shuffles which side is A and which is B for every pair, so neither of you can leak the answer key.

## Two things that break this

**Contamination.** Whatever writes the drafts must not have seen the original. If the original is in your context you will echo it, the drafts will look great, and you will have measured nothing. Write all the briefs in one session, then draft in a fresh session or a subagent that has only the guide and the briefs. If you cannot fully separate them, say so plainly when the results come in.

**Genre drift.** A guide built from one kind of writing does not transfer to another. If the human starts asking you to apply their email guide to cover letters, stop and tell them it needs its own corpus and its own pass.

## When to stop

Stop when their comments stop producing new rules, not when the score reaches some number.

The score is directional at best: one judge, a small sample, and the drafts had hindsight because the briefs were written by someone who had read the originals. What actually matters is repetition. Three comments about the same habit is a rule. One comment about it is a mood.

## After the loop

The guide is worth nothing if it does not load automatically. Help them put it where their tool reads it every time: project instructions, a saved instruction block, a skill, or a file the assistant is told to read at session start. Whichever needs no discipline from them.

Then keep it alive with the cheapest version of the same loop. Every hand edit they make to a draft before sending is free training data. Diff what they changed against what you wrote, and turn the diff into a rule.
