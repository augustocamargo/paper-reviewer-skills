---
name: paper-external-review-triage
description: >
  Triage a review of your paper produced by an external LLM (Gemini, ChatGPT,
  Claude) or an automated tool, separating signal from noise before you act on
  it. Use when the user says "I ran my paper through ChatGPT/Gemini and it
  said...", "here's a review from another model", "should I act on these
  comments", or "a tool flagged these issues". Adjudicates suggestions against
  the rendered PDF and a decisions log; does not itself rewrite the paper.
---

# External-review / LLM-review triage

External LLM reviews are useful but have **predictable failure modes**. Triage
them like a human review: verify before fixing, and adjudicate every suggestion.

## What they get right
- They **converge on the headline verdict** (the real top-level strengths and
  weaknesses). When several independent models agree on a macro point, weight it.

## Where they are reliably WRONG (discount these)
- **Anything requiring the rendered PDF.** They review *extracted text*, so they
  present extraction artifacts as defects — a dropped `$t$` math token, glyph
  noise, a merged column. **Trust the rendered PDF** (`pdftoppm` to images), not
  the model's reading of the extracted text.
- **Where generic style priors collide with documented decisions.** They regress
  toward defaults: re-flagging deliberate passive voice, proposing title
  rewrites you already settled, flipping a contribution hierarchy you chose on
  purpose.

## Procedure
1. **Bucket each comment**: (a) macro/verdict-level, (b) needs-the-PDF, (c)
   collides-with-a-decision, (d) genuine fixable defect.
2. **Drop (b)** after checking the rendered PDF; **drop (c)** after checking the
   decisions log (and record *why* the decision stands).
3. **Quantify (a)** before acting — measure the claim (see paper-claims-vs-data /
   paper-ai-prose-signals) rather than trusting the assertion.
4. **Act on (d)**; route to the matching focused skill.

## Principle
Verify before fixing. An external model is a fast, fallible reviewer, not an
oracle — adjudicate every suggestion against the rendered PDF and your own
documented decisions before you change anything.

## Output
- Triage table: `comment | bucket (verdict/needs-PDF/decision-collision/defect) |
  verdict (act / drop + reason)`.
- The short list of genuine fixable defects, routed to the right skill.
