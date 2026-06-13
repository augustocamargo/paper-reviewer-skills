---
name: paper-reviewer-sim
description: >
  Simulate a hostile, multi-persona peer reviewer for an empirical / systems
  manuscript and return a publication-risk verdict. Use when the user says
  "review my paper like a reviewer", "what would a reviewer attack", "find the
  weak spots", "is this ready to submit", or "estimate my acceptance odds".
  Produces per-section skepticism, top concerns/strengths, and reject/major/
  minor/accept percentages. Venue-agnostic — parameterize by the target venue's
  bar and decision process.
---

# Hostile reviewer simulation + risk verdict

## Personas
Read the paper through several lenses (e.g., theory/algorithms, HPC/systems,
applied ML/domain). Note when an objection is **wrong-venue** (a bar from a
different venue) rather than a real flaw.

### Venue-mechanics editor persona
Derive the editor's strictness from the **target venue's actual decision
process**, not a generic ideal. Look up, for that venue: is there a major-
revision round or is the decision **binary** (accept/reject)? acceptance rate?
how reviewers are recruited? Then calibrate the persona:
- **If the process is binary / no second chance**, then **verifiable compliance**
  (placeholder author bios, missing funding footnote, wrong affiliation, style-
  manual violations) becomes an **unforgivable** category — a clean-science
  paper can still be desk-rejected on a checklist item. Keep the **compliance
  gate separate from the science score** in the verdict.
- **If a revision round exists**, compliance items are usually fixable later;
  weight the science/novelty critique more heavily.

(For an IEEE Access-style example of how venue mechanics can change the review
persona, see the `ieee-access-review` skill. Treat any acceptance rate, revision
mechanic, AE-load estimate, reviewer-recruitment pattern, or policy detail as
venue- and date-specific; verify against the current venue pages before using it
as a premise.)

### 30-minute triage order
Editors/reviewers read in this order: title → abstract → contribution bullets →
tables → conclusion → references; **equations last**. Prioritize fixes by what a
fast triage hits first.

## Per-section sweep
For Abstract, Intro, Related Work, Method, Setup, Results, Discussion,
Limitations, Conclusion, flag: claims likely to trigger skepticism; claims
needing stronger evidence; exaggerations; advertising/grant-proposal tone;
unsupported assertions. Tag severity Critical / Major / Minor with the
reviewer's likely reaction.

## Key framings to test
- **Novelty vs venue-fit.** Surprise-driven conferences (e.g., ICASSP,
  Interspeech) reward novelty; validation-driven journals reward rigorous
  validation of useful work. A "no-novelty" hit may be a venue mismatch. The
  defense against a "no-novelty"/engineering attack is to name the *design move*
  and its lineage, not to claim it isn't simple.
- **The "obvious / presumption" trap.** If the result sounds obvious, the fix is
  to **lead with the non-obvious finding the work already contains** (e.g., a
  counter-intuitive result, an inversion, an honest negative), stated up front —
  not to argue it isn't obvious.
- **Honest negatives are armor**, not weakness — keep them visible.
- **The zero-concession comparison-table trap.** An all-"Yes"/all-green feature
  matrix reads as an advertisement — the trigger is **zero concessions, not the
  win ratio** (0-of-N = ad; 1-of-N = comparison). Each cell is a fact-checkable
  claim, so a wrong "Yes" given to a rival is a *factual error*. Fix structurally:
  a 3-way positioning matrix where each column owns one axis and your method is
  the visible intersection, plus an **honest inversion row** where a rival wins.
- **Comparison-coverage audit.** Inventory every comparison surface; check you
  are **above the genre bar** (e.g., nnAudio-2020 compared only one baseline).
  Name the strongest **unbenchmarked** competitor and decide measure-vs-classify.
- **Name the unnamed competitor by taxonomy, not benchmarking.** If a competitor
  is itself an instance of the problem you solve (e.g., a CUDA-only op library),
  one sentence classifying it converts a "why no comparison?" exposure into
  evidence for your thesis — no new experiment needed.
- **Macro attacks are the residual.** Closing every cheap, checkable kill forces
  reviewers onto macro/taste objections; in a binary process a macro attack that
  can't point to a fixable defect reads as taste and loses to checkable rigor.
  Map the realistic macro attacks with pre-built, grounded answers.

## Output
1. Per-section issue table (location, issue, severity, reaction).
2. Top-5 concerns; Top-5 strengths.
3. Risk: Reject % / Major-revision % / Minor-revision % / Accept %.
4. Brutally honest one-paragraph overall assessment: what, specifically, keeps
   it from looking like a strong submission, and the cheapest fixes with the
   highest impact on acceptance probability.

## Guardrail
Be candid but fair; engage objections in good faith. Distinguish "fatal" from
"misread/wrong-venue/scope". Don't inflate or deflate the verdict to please.
