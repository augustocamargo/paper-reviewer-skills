---
name: paper-claim-evidence-auditor
description: >
  Map paper claims to supporting evidence and rate support strength. Use when
  the user asks "is every claim supported", "which claims overreach", "map
  claims to evidence", "does the paper prove what it says", or "find unsupported
  claims". Produces claim-evidence tables such as claim, evidence source, support
  strength, gap, and recommended wording. Does not recompute raw numbers.
---

# Claim-evidence auditor

## Goal
Every important claim should point to visible evidence, and the wording should
match the strength of that evidence.

## Claim classes
- **Descriptive:** what was built, measured, released, or observed.
- **Comparative:** better/faster/smaller/more robust than a baseline.
- **Causal/mechanistic:** X causes Y or component Z explains the gain.
- **Generalization:** works across domains, datasets, languages, models, users,
  hardware, or deployment settings.
- **Safety/security/privacy/fairness:** secure, private, safe, fair, robust, or
  resistant to misuse/failure.
- **Practicality:** usable, scalable, deployable, efficient, low-cost, or easy to
  reproduce.

## Support levels
- **Strong:** direct evidence supports the exact claim and scope.
- **Moderate:** evidence supports the direction, but scope/strength needs
  narrowing.
- **Weak:** evidence is indirect, partial, single-setting, or missing a key
  comparator.
- **Unsupported:** no visible evidence in the paper.
- **Contradicted:** evidence conflicts with the claim.

## Procedure
1. Inventory load-bearing claims in title, abstract, introduction, contribution
   bullets, results, discussion, and conclusion.
2. For each claim, identify the evidence source: figure, table, experiment,
   theorem, citation, artifact, appendix, or qualitative evidence.
3. Rate support strength and explain the gap.
4. Recommend one of: keep, narrow, move to future work, add evidence, route to a
   focused audit, or delete.
5. Preserve honest negatives; do not make the paper sound stronger than the
   evidence.

## Boundary with other skills
- Use `paper-claims-vs-data` to recompute or verify numerical values.
- Use `paper-experiment-design` to judge whether the experiment design is enough.
- Use `paper-baseline-benchmark-audit` for missing/comparison baselines.
- Use `paper-writing-auditor` for grammar and readability after claim strength is
  settled.

## Output
- Claim-evidence table:
  `claim | location | evidence | support | gap | recommended action`.
- List of claims to downgrade before submission.
- Suggested evidence-faithful rewrites for overclaims.
