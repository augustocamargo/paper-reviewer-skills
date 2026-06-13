---
name: paper-experiment-design
description: >
  Audit experimental design and statistical evidence in CS/AI papers: hypotheses,
  baselines, ablations, splits, seeds, sample size, metrics, confidence intervals,
  significance/equivalence tests, and claims supported by the design. Use when
  the user asks "are the experiments enough", "is the evaluation sound", "what
  experiments are missing", or "will reviewers trust the evidence".
---

# Experimental design & statistics audit

## Principle
Judge whether the experiment can answer the claim being made. Do not merely ask
whether the numbers look good.

## Design checks
1. **Claim-to-test map.** For each main claim, identify the endpoint, dataset,
   comparator, metric, sample size, seed protocol, and test. Missing links are
   paper-risk.
2. **Baselines and controls.** Require strongest current baselines, simple
   sanity baselines, ablations, and negative controls where applicable.
3. **Split and leakage.** Check train/validation/test separation, preprocessing
   fit scope, duplicate contamination, temporal leakage, benchmark overlap, and
   prompt/example leakage for LLM work.
4. **Seeds and variance.** Single-seed wins are weak. Require mean/median plus
   dispersion; for stochastic training or prompting, report enough runs to make
   variance visible.
5. **Statistical match.** Use paired tests for paired runs; avoid p-values when
   n makes them meaningless; prefer confidence intervals/effect sizes and
   equivalence/non-inferiority tests when the claim is "not worse".
6. **Multiple comparisons.** Flag cherry-picked metrics, many datasets without
   correction/context, and best-of-N prompt/model selection reported as if it
   were a single trial.
7. **Ablation logic.** Each ablation should isolate one mechanism. If an ablation
   changes several things, call it a variant study, not causal evidence.
8. **External validity.** State the operating regime: data type, hardware,
   model scale, workload, language/domain, and failure envelope.

## Output
- Claim-to-test table: `claim | current evidence | design gap | severity`.
- Missing-experiment list ranked by acceptance impact and cost.
- Statistical-risk notes: seed fragility, insufficient n, wrong test, leakage,
  or over-interpreted p-values.
- Minimal fix plan: what can be repaired by reframing vs what needs new runs.
