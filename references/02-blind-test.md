# The Blind Test

Steps 3 and 4. This is where the guide stops being a guess.

## What you are building

For 10 to 15 pieces from the corpus, two versions sit side by side:

- the piece they actually wrote
- an AI draft of the same piece, written from a situation brief and the voice guide, and nothing else

They grade the pairs without knowing which is which.

Fewer than 8 pairs and one strange pair swings the whole result. More than 15 and grading becomes a chore, which shows up as shorter comments, and the comments are the point.

## The contamination firewall

**Whatever writes the draft must not have seen the original.**

If the original is in context, the draft will echo it. The drafts will look excellent, the human will be pleased, and you will have measured nothing at all. This is the single easiest way to waste the entire exercise, and it fails silently.

In order of preference:

1. Write all the briefs in one session. Start a clean session holding only the guide and the briefs, and draft there.
2. Spawn a subagent whose entire context is the guide and one brief.
3. If neither is possible, say so plainly when the results come in, and discount them.

Do not tell yourself you will simply ignore the original. You will not.

## Writing the situation briefs

The brief carries the facts. It must not carry the phrasing.

```
For each sample, write a situation brief containing ONLY:

- Reader: who they are and my relationship to them
- Situation: what happened, in neutral words
- Goal: what I want this piece to accomplish
- Must include: facts, names, dates, numbers, links that have to appear
- Constraints: length, format, anything non-negotiable

Never include: phrasing from the original, its structure, its opening or
closing, or any word that was chosen for tone. If you catch yourself
reusing a distinctive word from the original, replace it with a plain one.
```

The last sentence is the one to actually enforce on yourself. Distinctive words leak more than structure does, and they leak without feeling like leaking.

## Drafting

In the clean session:

```
Write a [GENRE] from the brief below. Your only other input is the voice
guide, which is attached. Do not ask me clarifying questions. Produce the
finished piece, ready to send.
```

No questions is deliberate. A real drafting request will not get a clarifying round either, and questions here would pull information that the brief was supposed to be tested on.

## Building the pairs file

```
Produce a JSON array for the test tool. One object per pair:

[
  {
    "id": 1,
    "label": "Short description of the situation",
    "reader": "Who it is addressed to",
    "mine": "The full text of the piece I actually wrote",
    "draft": "The full text of your version, from the brief and the guide"
  }
]

Plain text in "mine" and "draft". Keep real line breaks. Use "- " at the
start of a line for bullets. Do not add commentary, headers, or markdown
emphasis. Output only the JSON array.
```

Save it as `pairs.json`. The tool shuffles which side is A and which is B for every pair, so you do not need to randomize, and neither of you can leak the answer key by accident.

## Grading

Open `assets/voice-test.html` in a browser and paste in `pairs.json`. Everything runs locally.

Two rules make this work, and both are counterintuitive.

**They are not spotting the AI.** They pick the version they would rather have sent. Whether something reads as AI matters far less than whether it is better, and detection tests reward writing that is merely idiosyncratic over writing that is good.

**No answer key until the end.** Every pair gets graded before anyone learns which side was theirs. Once you know, you cannot unknow it, and people start defending their own work without noticing they are doing it.

### The scale

| Score | Means |
|---|---|
| A clearly better | Would send A, and would be annoyed if someone sent B on their behalf |
| A slightly | Both fine, A edges it |
| Toss-up | Genuinely cannot pick, or would send either |
| B slightly | Both fine, B edges it |
| B clearly better | Would send B, and would be annoyed if someone sent A on their behalf |

### The comment is the deliverable

The score says where things stand today. **The comments are the only thing the next guide gets built out of.** A graded pair with no comment is a wasted pair, and this is the step people rush.

Three things make a comment useful:

1. **Quote the specific sentence.** Not "the tone is off." Point at the words.
2. **Say what is wrong with it,** framed as what they would or would not do.
3. **Give the fix if they have one.** The sentence they would have written usually becomes the rule almost verbatim.

Comment on the pairs they *preferred* too. "This nailed the close, I would not have gotten there" produces a rule as surely as a complaint does, and positive rules are underrepresented in most guides.

The tool requires a comment on every pair for exactly this reason.

### What a useful comment looks like

| Useless | Useful |
|---|---|
| B feels off. Something about it is not me. | "I really enjoyed the conversation, sharing about myself and what I'm looking for, and hearing your thoughts thus far." A comma list where one item carries two ideas joined by "and" is not a structure I would ever use. I would have written: "sharing about myself, talking about what I'm looking for, and hearing your thoughts so far." |
| Too formal. | "in neither one did I have enough runway." I use "runway" for the time an initiative or a company has, not the time left in a conversation. It does not feel authentic. Also "in neither one" is not a phrase I would reach for. |
| A is better. | B has no greeting, and it opens with a caveat about the idea instead of the idea itself. That is painful to read. A states the thing first and puts the warning underneath, which is right. |

## Reading the result

The tool reports how often they preferred their own writing, how often they preferred the draft, and how many were toss-ups.

Hold it loosely. The test has three weaknesses baked in, and they should be said out loud rather than discovered later:

- **One judge.** Their preferences on a Tuesday afternoon are not a stable measuring instrument.
- **Small sample.** Twelve pairs is twelve pairs. A three-point swing is noise.
- **The drafts had hindsight.** The brief was written by someone who had read the original, so the draft knew which facts mattered. Real drafting does not get that.

What matters more than the score is **whether the comments repeat**. Three separate comments about the same habit is a rule. One comment about it is a mood. Sort by repetition, not by how strongly they felt in the moment.

One thing worth telling them directly: if the drafts beat their own writing on some pairs, that is not a verdict on them. It means their real writing contains habits they do not endorse, which is true of everyone and is exactly what this loop exists to surface.

Next: `03-rules-from-results.md`.
