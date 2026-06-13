---
name: paper-user-study-audit
description: >
  Audit user studies, human evaluations, annotator studies, surveys, interviews,
  usability tests, and HCI-style evidence in CS/AI papers. Use when people are
  participants, annotators, judges, operators, or subjects in the evidence.
---

# User study & human evaluation audit

## Study design checks
1. Research question maps to the study task, participant population, condition,
   measure, and analysis.
2. Recruitment, eligibility, compensation, consent, IRB/exemption, exclusions,
   and demographics are stated when relevant.
3. Between/within-subject design, randomization, counterbalancing, training,
   washout, and order effects are handled.
4. Sample size, power/precision, attrition, failed attention checks, and missing
   data are disclosed.
5. Instruments and tasks are realistic; subjective scales are named and anchored.
6. Qualitative coding reports codebook, coders, agreement/adjudication, and
   representative evidence without cherry-picking.
7. Human eval for AI reports blinding, item sampling, judge agreement, tie policy,
   prompt/order randomization, and conflict resolution.

## Common reviewer attacks
- Convenience sample does not support broad user claims.
- Preference scores are reported as task performance.
- Participants can infer condition, causing demand effects.
- Annotators judge fluency instead of correctness.
- Statistical test ignores repeated measures or clustered items.

## Output
- Study-validity table: `claim | study element | weakness | fix`.
- Ethics/compliance gaps.
- Claims that must be narrowed to the actual participant/sample/task.
- Rebuttal-ready explanation of what the human evidence does and does not show.
