---
name: paper-structure-pertinence
description: >
  Audit a paper's section-level organization and pertinence: each section does
  only its job, negatives are framed before their numbers, every load-bearing
  title word is substantiated in the body, the operating envelope is symmetric,
  and the reader has an early experimental-design figure and a navigation table.
  Use when the user says "is the paper well organized", "check the structure",
  "is each section doing its job", "does the title match the paper", or "is
  anything in the wrong section". Structure/organization only; pair with
  paper-claims-vs-data for the numbers and paper-ai-prose-signals for wording.
---

# Structure & pertinence audit

## Section specialism (pertinence)
Each section must do **only its job**; content in the wrong section is
contamination:
- **Results** reports — no thesis, causal, or marketing language.
- **Discussion** interprets and makes causal/positioning claims.
- **Related Work** positions against prior art.
- **Methodology** constructs the method.
- **Conclusion** closes; it does not introduce new evidence.

When you move a sentence out of Results into Discussion, **relocate any orphaned
citation with it** so the bibliography still resolves.

## Frame negatives before their numbers — locally
A global framing (e.g., a pre-registered analysis-plan table) does **not** protect
local reading order. **Every subsection** that reports a negative or non-
equivalent result must **open with "we predicted this"** and *then* show the
numbers — otherwise the reader hits the negative cold and reads it as a failure.

## Substantiate every title word
Audit that each **load-bearing promise in the title** is redeemed in the body
(e.g., "single-GEMM" must appear and be supported in the math, not just the
title). Keep an honest 8/10 title over a 9/10 title that breaks a promise.

## Symmetric operating envelope
A "**when to use / when not to use**" pair reads as engineering maturity; a lone
"When Not to Use" reads defensive. State each regime once, point to the
mechanism (don't restate it), and close with a take-home practice.

## The missing-element class (what audits can't see)
Reviewer simulations and checklists evaluate **what is present** — they never
flag **what is missing**. Deliberately ask the author-side question: "is the
experiment visually clear up front?"
- Provide an **early experimental-design overview figure** (also a graphical-
  abstract candidate).
- Provide a **navigation / analysis-plan table** mapping each evaluation to
  endpoint · dataset · n · comparator · test · margin, plus a **"Reported in"**
  column — this answers design/endpoint reviewer asks before they ask.

## Output
- Pertinence table: `content | current section | belongs in | move?`.
- List of negatives not framed-before-numbers, with the missing lead sentence.
- Title-word checklist: `title term | substantiated in body? | where`.
- Missing-element list (figures/tables a reader needs but the paper lacks).
