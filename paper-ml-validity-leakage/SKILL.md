---
name: paper-ml-validity-leakage
description: >
  Check ML/AI validity hazards: data leakage, contamination, benchmark overlap,
  confounding, label noise, metric gaming, calibration, subgroup failure, prompt
  leakage, and evaluation by LLM judges. Use when reviewing machine-learning,
  deep-learning, or LLM papers for science fidelity.
---

# ML validity, leakage & contamination audit

## Leakage surfaces
- Preprocessing fitted on all data rather than train only.
- Duplicate or near-duplicate items across splits.
- Temporal, user, patient, repository, or document-level entities split
  incorrectly.
- Model pretraining contamination with benchmark/test data.
- Prompt examples, few-shot demonstrations, or retrieval corpora containing
  answers or paraphrases of test items.
- Hyperparameters, thresholds, prompts, or checkpoints selected on the test set.

## Validity hazards
1. **Confounding.** The model may learn source, artifact, length, style, or
   dataset identity rather than the claimed signal.
2. **Label quality.** Check annotator agreement, adjudication, label drift,
   ambiguity, and whether label noise changes the conclusion.
3. **Metric fit.** Accuracy can hide imbalance; F1 can hide calibration; average
   score can hide subgroup collapse; win rate can hide judge bias.
4. **LLM-as-judge.** Require judge prompt, judge model/version, randomization,
   blinded ordering, tie policy, calibration against humans, and bias checks.
5. **Distribution shift.** Separate in-distribution gains from robustness,
   transfer, multilingual, long-tail, or deployment claims.
6. **Ablation confounding.** Removing a component may also change parameter
   count, compute, context length, training time, or data exposure.

## Output
- Leakage table: `surface | evidence checked | risk | required fix`.
- Confounder map: possible shortcut, how to test it, and whether the paper does.
- Metric adequacy verdict with better metric/reporting suggestions.
- Claims to downgrade unless additional validity evidence is added.
