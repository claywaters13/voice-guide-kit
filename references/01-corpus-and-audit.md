# Genre, Corpus, and the Audit

Steps 0 through 2. By the end of this you have a written voice guide, which is a guess that has not been tested yet.

## Step 0: pick one kind of writing

This is the step people skip and it is the one that breaks everything downstream.

A voice guide belongs to a genre, not to a person. Nobody has one voice. The way someone writes a text message is not how they write a cover letter, and neither is how they write a project memo. A guide built from one genre and applied to another produces writing that is confidently, fluently wrong: their real habits, pointed at the wrong target.

Get them to name exactly one. Some examples:

- Cold outreach email
- Cover letters
- Text messages to friends and family
- Long-form posts or essays
- Internal memos and one-pagers

Then gather samples of that exact thing. Do not substitute. If they want cover letters, the corpus is cover letters, even if their cover letters are not the writing they are proudest of. Auditing their email to build a cover letter voice produces a careful, well-evidenced guide to a genre they did not ask about.

**If they want two genres, run the whole process twice.** Two corpora, two guides, two tests. The guides will share some rules and flatly contradict each other on others. The contradictions are correct. Do not reconcile them.

### Thin corpus

Some genres are low volume by nature. Cover letters are the worst case: most people have a handful, written under deadline, half-assembled from a template.

Run it anyway with what they have. Two things change:

- Mark the guide provisional at the top.
- Lean harder on the iteration passes, because the blind test is now doing more of the work than the audit did.

Do not pad the corpus with a neighboring genre to reach a number. Five real cover letters beat five cover letters and fifteen emails.

## Step 1: gather the corpus

Aim for 15 to 40 pieces, or everything they have if that is fewer.

**Include** things they wrote themselves start to finish, across a range of readers and situations. Include the awkward ones. A corpus of greatest hits teaches the model to write greatest hits for a reader who wanted a two-line answer.

**Exclude:**

- Anything co-written, or heavily edited by someone else
- Anything an AI already touched. This is the important one: it teaches the model its own habits back and turns the whole exercise into a mirror.
- Anything built from a template they were handed
- Purely transactional scraps with no room for voice ("sounds good, thanks")

**Gate:** show them what you excluded and why before you read anything. Getting this wrong quietly poisons every step that follows, and it is invisible later.

## Step 2: the audit

Give the model the whole corpus at once. This prompt is a starting point, not scripture.

```
You are building a voice guide for me, for one specific kind of writing: [GENRE].

Below are [N] pieces of my own [GENRE]. Read all of them before you write anything.

Produce a voice guide with these sections:
  1. Register and stance (how I come across, and what I am doing to the reader)
  2. Structure (how a piece of mine is shaped, start to finish)
  3. Sentence and paragraph habits
  4. Openings
  5. Closings
  6. Words and phrases I actually use
  7. Words and phrases I never use
  8. Confidence and calibration: how I signal how sure I am
  9. How all of the above changes by reader

Rules for the guide itself:
- Every rule traces to something in the samples. Quote the evidence inline.
- Write rules a stranger could follow and produce my writing. "Be warm" is
  not a rule. "Opens with 'Hey [first name],' for professional contacts" is.
- Separate consistent habits from one-offs. Say which is which.
- If you notice something I do that you suspect I would not defend if asked,
  keep it OUT of the guide and list it separately under "candidates to drop."

Do not summarize the samples back to me. Give me the guide.
```

### The candidates to drop list

That last instruction does more work than it looks like it does.

The goal is not a perfect imitation. Everyone's real writing contains habits they do not actually like, and a guide that reproduces them faithfully has locked in their bad days alongside their good ones. The target is **them on their best day**.

**Gate:** walk the human through the candidates list item by item. They decide each one. Do not decide for them, and do not quietly fold any of them back into the guide.

### What a usable rule looks like

| Too vague to use | Usable |
|---|---|
| Warm but professional. | Opens with "Hey [first name]," for professional contacts. Never "Dear," never "I hope this email finds you well." |
| Sounds confident. | Marks how sure I am: "maybe," "probably," "almost certainly," "I suspect," or a flat statement when I am sure. Uniform unmarked confidence does not sound like me, and neither does hedging everything equally. |
| Keeps it short. | Paragraphs run 2 to 4 sentences. Anything longer gets broken apart, even when the ideas are related. |

### Excerpts from a real guide

Anonymized, from a working guide for professional email. These are here to show the resolution to aim for, not to copy. Several of them would be actively wrong for someone else.

**Hard bans**

- Never use em dashes or en dashes. Commas, periods, parentheses, colons, or simple hyphens instead.
- Never sign off with "Best regards," "Cheers," or "Best,". Mid-sentence "thanks again for..." is fine and authentic.
- Cut on sight: "please don't hesitate to," "as per our conversation," "leverage," "circle back," "touch base," "I'm thrilled," "this is a great opportunity."

**Traits to preserve rather than sand off**

- **Candor first.** States his own limits before the reader can get there ("my sample is one," "I'm not a great interviewer"). This is an active trust move, not a hedge to be edited out.
- **Lists are load-bearing.** Bulleted taxonomies and split-out points, even in casual mail. Do not flatten a natural list into paragraphs.
- **Register boundary.** Bullets signal organized and precise, which is the default. But emotional content (gratitude, reflection, connection) gets warm prose. Bullets read cold there.

**Rules that only appeared after the blind test**

- Comma lists must be parallel, one idea per item. Never let one item carry two ideas joined by "and."
- Lead with the idea. Caveats come after. Never open with a disclaimer about the thing before stating the thing.
- Do not start sentences with "And."
- Always greet, even in a two-line personal note.
- Metaphors have to match the domains he actually uses them in. "Runway" means time for an initiative or a company, never time left in a conversation. When unsure, use the plain word.
- Break dense paragraphs apart. White space between separated ideas won blind preference tests repeatedly.

That last group is the argument for doing the rest of this. None of those rules could have come from the audit. They came from the test.

Next: `02-blind-test.md`.
