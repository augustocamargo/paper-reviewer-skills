---
name: cs-ai-paper-review
description: >
  General full-review orchestrator for computer science and AI manuscripts.
  Use when the user asks for a full paper review, pre-submission audit, acceptance
  risk estimate, science-fidelity check, or venue-readiness review for ML, NLP,
  CV, systems, security, HCI, data management, software engineering, theory, or
  interdisciplinary AI venues. Routes to focused paper-review skills.
---

# CS/AI full paper review orchestrator

## Goal
Maximize science fidelity and acceptance odds without inventing evidence or
weakening honest limitations. Keep two scores separate:
- **Truth score:** are the claims supported?
- **Review score:** will the target venue's reviewers value and trust the work?

## Run order
0. **paper-venue-fit-strategy** — target venue, audience, contribution type, and
   review culture.
1. **paper-busy-reviewer** — fast triage surface: abstract, intro, figures,
   conclusion, and reviewer reports if present.
2. **paper-novelty-positioning** — novelty unit, nearest prior work, contribution
   defense, incremental-risk map.
3. **paper-abstract-title-contribution** — first-page/title/abstract/contribution
   bullets.
4. **paper-claim-evidence-auditor** — map load-bearing claims to visible
   evidence and downgrade unsupported or overbroad claims.
5. **paper-structure-pertinence** — section roles, title promises, local framing
   of negatives, missing overview/table elements.
6. **paper-experiment-design** — claim-to-test map, seeds, statistics, ablations,
   missing experiments.
7. **paper-baseline-benchmark-audit** — baseline sufficiency, fairness, benchmark
   credibility.
8. **paper-ml-validity-leakage** — ML leakage, contamination, confounding, metric
   validity, LLM judge quality.
9. **paper-claims-vs-data** — quantitative claims traced to tables/figures/raw
   data.
10. **paper-figure-table-auditor** — captions, legends, units, axes, precision,
   readability, and self-contained figures/tables.
11. **paper-formula-audit** — equations, dimensions, indices, asymptotic claims.
12. **paper-theory-proof-audit** — theorem statements, assumptions, proofs, and
   counterexamples, when theory is present.
13. **paper-systems-performance-audit** — throughput/latency/memory/scaling and
   measurement validity, when systems claims are present.
14. **paper-dataset-benchmark-paper** — dataset/benchmark contribution quality,
   when the paper contributes data or evaluation suites.
15. **paper-user-study-audit** — user studies, annotator studies, HCI, human eval,
   when people are part of the evidence.
16. **paper-citation-check** — bibliography reality and citation graph hygiene.
17. **paper-security-ethics-safety** — privacy, safety, misuse, IRB, data rights,
   responsible release.
18. **paper-limitations-threats** — honest, non-apologetic limitations and
   threats to validity.
19. **paper-artifact-evaluation** — code/data/model package and reproduction path.
20. **paper-repro-compliance** — venue policy, reproducibility, PDF gates.
21. **paper-writing-auditor** — grammar, spelling, punctuation, readability,
   ambiguity, flow, transitions, acronyms, tone, and overclaim wording; writing
   only.
22. **paper-ai-prose-signals** — prose-only cleanup after scientific content is
   stable.
23. **paper-external-review-triage** — only when adjudicating an external review.
24. **paper-rebuttal-response** — only after reviewer comments exist.

## Output
- Executive verdict: acceptance risk, truth risk, and venue-fit risk.
- Top-10 fatal/major issues and top-10 highest-ROI fixes.
- Science-fidelity gate: claims to downgrade, verify, or remove before submit.
- Acceptance strategy: what to fix now, what to reframe, what to defer.
- Focused tables from each triggered skill, not from irrelevant skills.

When the user also requests implementation of the review findings across the
manuscript, hand the verified diagnosis to `paper-surgical-editor` rather than
silently expanding this diagnostic workflow into a rewrite.
