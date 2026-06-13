---
name: paper-novelty-positioning
description: >
  Audit a CS/AI paper's novelty, related-work positioning, contribution claims,
  and venue-fit story. Use when the user asks "is this novel", "is the related
  work convincing", "will reviewers say incremental", "how do I position this",
  or "what is the contribution". Focuses on novelty defensibility, not number
  correctness.
---

# Novelty & positioning audit

## Core question
Can a skeptical reviewer state what is new, why it matters, and why prior work
does not already cover it?

## Checks
1. **Contribution unit.** Identify the smallest defensible unit of novelty:
   algorithmic idea, system design move, empirical finding, dataset, benchmark,
   analysis, negative result, or integration. Do not let the paper claim a
   stronger novelty type than it can defend.
2. **Nearest-neighbor prior art.** Name the closest 3-5 works and state the
   exact delta against each. If the delta is "we combine X and Y", require a
   mechanism/result that makes the combination nontrivial.
3. **Incremental-risk test.** Flag sentences that make the work sound like an
   engineering wrapper, parameter sweep, prompt variant, benchmark re-run, or
   obvious application. Replace with the specific design constraint, empirical
   inversion, or failure mode the paper exposes.
4. **Venue novelty calibration.**
   - Top AI/ML conferences: novelty, insight, and broad relevance must be clear.
   - Systems venues: design constraints, real workload, ablation, and artifact
     quality carry more weight.
   - Journals: validation depth, reproducibility, and scope clarity can beat
     surprise.
5. **Negative-result value.** If the paper has an honest negative or null result,
   decide whether it is the novelty rather than an embarrassment. Make the
   learning visible early.
6. **Overclaim boundary.** Separate "first", "state of the art", "general",
   "robust", and "safe" claims into defensible / needs evidence / delete.

## Output
- Novelty verdict: strong / moderate / incremental / unclear, with one sentence.
- Table: `nearest work | what it already does | defensible delta | evidence`.
- Contribution rewrite: 2-4 bullets, each tied to evidence already in the paper.
- Reviewer attack map: the 5 most likely "not novel / incremental" attacks and
  the best honest answer.
