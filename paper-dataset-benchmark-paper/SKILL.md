---
name: paper-dataset-benchmark-paper
description: >
  Audit dataset, benchmark, challenge, leaderboard, or evaluation-suite papers in
  CS/AI. Use when the contribution is a dataset, benchmark, annotation protocol,
  task formulation, leaderboard, or measurement suite rather than mainly a new
  model or algorithm.
---

# Dataset & benchmark paper audit

## Dataset contribution checks
1. **Need.** Existing datasets are insufficient for a specific reason, not just
   smaller/older/different.
2. **Collection.** Source, sampling frame, inclusion/exclusion rules, temporal
   coverage, geography/language/domain, duplicates, licenses, consent, and PII.
3. **Annotation.** Guidelines, annotator training, pay/ethics, adjudication,
   agreement, ambiguity policy, label distribution, and quality control.
4. **Documentation.** Datasheet/model card style facts: intended use, out-of-scope
   use, known biases, maintenance, versioning, access, and takedown process.
5. **Benchmark design.** Splits prevent leakage; metrics match the task; baselines
   include trivial, canonical, and strong methods.
6. **Saturation risk.** Show headroom and difficulty; a benchmark solved by
   simple baselines is weak unless that is the finding.
7. **Leaderboards.** Hidden test policy, submission limits, anti-overfitting
   controls, and versioned evaluation.

## Output
- Dataset/benchmark readiness: strong / useful but underdocumented / weak.
- Table: `area | current evidence | reviewer concern | fix`.
- Required documentation additions and release constraints.
- Baseline/metric/split fixes needed before submission.
