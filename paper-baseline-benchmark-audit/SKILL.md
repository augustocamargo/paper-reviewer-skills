---
name: paper-baseline-benchmark-audit
description: >
  Audit benchmark and baseline coverage for CS/AI papers. Use when the user asks
  "are my baselines enough", "what comparisons are missing", "is the benchmark
  fair", "will reviewers complain about SOTA", or "is the evaluation apples to
  apples". Focuses on comparison fairness and benchmark credibility.
---

# Baseline & benchmark audit

## Baseline classes
Check that the paper includes, or explicitly justifies omitting:
- **Strongest known method** for the same task.
- **Canonical method** every reviewer expects.
- **Simple baseline** that exposes whether the proposed method is overbuilt.
- **Ablated self-baseline** isolating the proposed contribution.
- **Compute/latency/parameter-matched baseline** when efficiency is claimed.
- **Domain-specific competitor** for applied papers, even if not SOTA globally.

## Fairness checks
1. Same train/test split, preprocessing, tuning budget, hardware, precision, and
   inference protocol unless the difference is the point.
2. Hyperparameter search effort disclosed for both your method and baselines.
3. No hidden advantage from extra data, test-set tuning, prompt selection,
   checkpoint selection, or benchmark-specific adaptation.
4. For LLM evaluation, report model versions, decoding settings, prompt
   templates, number of samples, judge model/version, and human/judge agreement.
5. For systems/HPC evaluation, separate algorithmic speedup from implementation,
   hardware, batching, precision, compilation, caching, and IO effects.

## Benchmark credibility
- Is the benchmark saturated, toy, too narrow, or misaligned with the claim?
- Are metrics robust to class imbalance, calibration, uncertainty, ranking ties,
  or abstention?
- Are failure cases and per-subgroup results visible?
- Does the benchmark match realistic deployment constraints?

## Output
- Baseline matrix: `baseline class | included? | expected by reviewer? | action`.
- Fairness table: `comparison | possible unfairness | evidence | fix`.
- "Reviewer will ask for..." list, ranked by likelihood.
- Defensible omission wording for baselines that are out of scope or infeasible.
