# Voice Guide Kit

A method and a tool for getting an AI assistant to draft in your own writing voice, and for finding out whether it actually worked.

Most attempts at this fail the same way. You tell the model to write like you, it produces something that is not quite right, you say "that doesn't sound like me," and the two of you repeat that forever without either one learning anything. The complaint never turns into a rule, so the next draft has the same problem.

This kit treats it as a measurement problem instead of a taste problem. Write down what your voice actually is, then test whether the writeup works by drafting blind against your real writing and grading the pairs without knowing which is which.

## The loop

**0. Pick one kind of writing.** A voice guide belongs to a genre, not to a person. The way you write a text message is not the way you write a cover letter. Build the guide from samples of the exact thing you want written.

**1. Gather a corpus.** 15 to 40 pieces you wrote yourself, across a range of readers. Include the awkward ones. Exclude anything an AI already touched.

**2. Write the guide.** The assistant reads the corpus and produces a written guide: register, structure, openings, closings, vocabulary, banned phrases, how you signal confidence. Every rule has to trace to evidence in the samples.

**3. Draft blind.** For 10 to 15 of those pieces, write a situation brief that carries the facts but none of the phrasing. Then, in a session that has never seen the original, draft each one from the brief and the guide alone.

**4. Grade blind.** Put your real version and the AI version side by side, without knowing which is which, and pick the one you would rather have sent. Say why every time.

**5. Turn the grades into rules.** Every comment becomes a rule, stated generally enough to apply to writing that does not exist yet. Then run it again.

Two or three passes is normal. The first guide is always wrong in ways nobody could have predicted from the samples alone, which is the entire reason the test exists.

## Two design choices that matter

**Preference, not detection.** The test asks which version you would rather have sent, not which one is the AI. Detection tests reward writing that is merely idiosyncratic. Preference tests reward writing that is better, which is what you actually want.

**Aim for you on your best day.** Your real writing contains habits you do not like. A guide that reproduces them faithfully has locked in your bad days along with your good ones. The audit is asked to flag habits you might not defend, and you decide which ones to keep.

## Where the numbers came from

The method came out of a run on professional email: 14 pairs, one judge, first pass.

The AI drafts won 8, the original emails won 2, and 4 were toss-ups.

That result is directional and not much more. One judge is not a stable measuring instrument, 14 pairs is a small sample, and the drafts had an advantage: the briefs were written by someone who had already read the originals, so the drafts knew which facts mattered. Real drafting does not get that.

The useful part was never the score. It was the comments. Several of the sharpest criticisms in that run landed on sentences from the real emails, including one the judge rewrote as an example of what not to do before learning he had written it himself two days earlier. Those comments became the rules that the audit alone had missed.

## Install

### As a Claude skill

```bash
git clone https://github.com/claywaters13/voice-guide-kit.git ~/.claude/skills/voice-guide-kit
```

Then ask your assistant to help you write something in your voice, or invoke it directly. It reads the state directory each session and picks up where you left off.

### Without installing anything

Read this file and `references/`, and run the prompts by hand in whatever tool you use. The method does not depend on Claude. The only piece you need either way is the grading tool, which is a single HTML file that runs in your browser.

## What is in here

| Path | What it is |
|---|---|
| `SKILL.md` | The loop, the gates, and the stopping rule, written for the assistant |
| `references/01-corpus-and-audit.md` | Picking the genre, building the corpus, the audit prompt |
| `references/02-blind-test.md` | Situation briefs, the contamination firewall, the grading rubric |
| `references/03-rules-from-results.md` | Turning graded comments into rules |
| `references/04-genre-notes.md` | Corpus advice per genre |
| `assets/voice-test.html` | The blind preference test. Runs locally, uploads nothing. |

## What this does not do

**Resumes.** A resume is evidence selection and bullet compression, not voice. Running this loop on one will produce very little.

**Content.** Sounding like you is necessary and not sufficient. A hiring manager reading a cover letter is scanning for specific evidence against a job description. Getting the voice right removes a penalty. It does not make your case for you.

**Other genres.** Worth repeating, because it is the common failure: the guide is good for the genre you built it from and no others. A second genre means a second corpus and a second pass.

## License

MIT. See [LICENSE](LICENSE).
