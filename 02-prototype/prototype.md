# Prototype · Juno

> Module 2 · Prototype. The working build that tests your idea, made with your build tool of choice.

## Prototype link

My organization doesn't allow public share links, so the prototype is committed to this folder instead:

- [`juno-signal-desk.html`](./juno-signal-desk.html): the working prototype. It is a single self-contained file. Download it and open it in any browser, no install needed.

Built with Claude (Claude Code) from this prompt:

- **Role:** a product designer building a lo-fi internal tool for one PM, with Zebra's (my actual organization) look (yellow accent, Red Hat type, greys).
- **Task:** one screen. Email, Teams and Slack signals are ingested on their own and grouped into problems. Each problem opens a Juno draft spec the PM approves or corrects. It has a command bar with dictation, and Knowledge and Analytics tabs as labeled stubs.
- **Constraints:** sample data only, with fictional customers and no personal contact data. No button that sends anything to customers or commits dates. Thin or conflicting signals get questions, not a draft. Stubs are labeled as out of the test. Drafts must follow `01-prompting/skill-file.md`.
- **Format:** drafts follow the skill file's 5 sections, with at most 400 words, at most 5 acceptance criteria, and a "PM decisions needed" section that is never empty.

## What it demonstrates

The flow from signals to a draft spec to the PM's decision. Every morning, Juno turns that day's client signals into problems, and I approve or correct each one-page draft without reopening the original threads.

**Testable assumption:** I can approve or correct a draft in under 5 minutes without clicking "Raw signals", because every claim is tied to a source or labeled as an assumption. If most testers open the raw threads before deciding, the draft isn't trusted yet and the assumption fails.

## Debrief

_I couldn't attend the live session, so I had no partner for Show and Swap. I gave an AI reviewer only the prototype, with no explanation from me, and asked it the debrief questions. It read the tool as "an AI triage desk for a PM", which matches my intent. It guessed the assumption was trust in sourced drafts. Mine is about speed, which builds on that trust._

- **What worked:**
  - State labels ("Draft ready", "Needs your answers", "Watching") show at a glance where to look.
  - The fixed 5-section draft is easy to scan, and each evidence line links to its source signal.
  - "Approve" stays locked until every PM decision is answered, which makes "Juno drafts, the PM decides" tangible.
  - Juno refuses to draft the conflicting onboarding cluster and asks one round of questions instead. It also explains why the 1-signal cluster gets no draft.
- **What broke / felt like a toy:**
  - The command bar refuses blocked requests correctly. But it then says the request was "added to PM decisions", and no row appears. That breaks my own hard refusal "never present a guess as a fact".
  - Dictate always fills in the same canned sentence.
  - "Correct" opens a text box with no way to submit it.
  - "Send answers" accepts empty fields and never produces a draft.
  - Knowledge and Analytics are empty stubs, and the 400-word counter isn't explained.
- **What I'd change next pass:**
  1. A refused command creates a real "PM decisions needed" row, so the prototype agrees with the skill file.
  2. "Correct" redrafts the targeted section, and the structure stays the same.
  3. Answers are validated, and a draft actually appears after them.
  4. Show time-to-decision on screen, so the speed assumption can be measured.
  5. Explain the 400-word cap with a tooltip linked to the skill file's Format section.
