---
name: ieee-access-review
description: >
  Full multi-pass review of an empirical / systems manuscript for an IEEE
  Access–style venue: runs the focused checks together and produces a single
  consolidated report and publication-risk verdict. Use when the user asks for a
  "full review", "review the whole paper", or "complete pre-submission audit".
  For a single isolated check, use the focused skills instead (paper-claims-vs-
  data, paper-formula-audit, paper-citation-check, paper-ai-prose-signals,
  paper-reviewer-sim, paper-busy-reviewer, paper-repro-compliance,
  paper-structure-pertinence, paper-external-review-triage,
  paper-novelty-positioning, paper-experiment-design,
  paper-baseline-benchmark-audit, paper-ml-validity-leakage,
  paper-security-ethics-safety, paper-limitations-threats,
  paper-artifact-evaluation, paper-venue-fit-strategy,
  paper-abstract-title-contribution, paper-rebuttal-response,
  paper-theory-proof-audit, paper-systems-performance-audit,
  paper-dataset-benchmark-paper, paper-user-study-audit,
  paper-writing-auditor, paper-figure-table-auditor,
  paper-claim-evidence-auditor). For broad CS/AI
  venues, prefer cs-ai-paper-review unless IEEE Access is the explicit target.
---

# Full manuscript review (orchestrator)

This is the umbrella. It applies the focused checks in sequence and aggregates
their findings. For an isolated check, invoke the corresponding skill directly.

## Shared principles (apply throughout)
1. **Trace every number to its source** (data/CSV/logs), never to memory or to
   the prose; recompute independently.
2. **Verify before you "fix."** A confident criticism — yours, an external
   reviewer's, or a tool's — can be wrong; check the source first. An unverified
   fix can introduce an error. Don't rubber-stamp; don't invent numbers.
3. **Venue-fit ≠ validity.** Judge against the target venue's actual bar.
4. **Edits are prose-only when the science is correct**; preserve protected
   content (Threats to Validity, limitations, honest negatives). Compile after
   edits and require 0 undefined references and no new content overfulls.

## Run, in order
0. **paper-busy-reviewer** (optional fast pre-pass) — the area-chair triage:
   does the paper survive on abstract/intro/figures/conclusion alone, and is it
   slot-worthy? Use it to set the bar before the deep sweep.
1. **paper-reviewer-sim** — hostile multi-persona sweep (incl. venue-mechanics
   editor persona, zero-concession table trap, coverage audit) + provisional risk.
2. **paper-venue-fit-strategy** — verify the target venue is the right bar and
   note framing adaptations before judging.
3. **paper-novelty-positioning** — nearest prior work, novelty unit,
   incremental-risk map, contribution defense.
4. **paper-abstract-title-contribution** — first-page triage surface: title,
   abstract, contribution bullets.
5. **paper-claim-evidence-auditor** — map load-bearing claims to visible
   evidence and downgrade unsupported or overbroad claims.
6. **paper-structure-pertinence** — section specialism, negatives-framed-locally,
   title-word substantiation, symmetric envelope, missing-element class.
7. **paper-experiment-design** — claim-to-test map, seeds, statistics, missing
   experiments, causal/ablation logic.
8. **paper-baseline-benchmark-audit** — expected baselines, apples-to-apples
   comparison, benchmark credibility.
9. **paper-ml-validity-leakage** — leakage, contamination, confounding, metric
   gaming, LLM judge validity.
10. **paper-claims-vs-data** — every figure-in-text traced to source; flag drift
   (incl. hand-written artifacts + precision unification); SSoT macros.
11. **paper-figure-table-auditor** — captions, legends, units, axes, precision,
   readability, and self-contained figures/tables.
12. **paper-formula-audit** — equations + asymptotic/complexity claims.
13. **paper-theory-proof-audit** — conditional: theorem/proof/guarantee claims.
14. **paper-systems-performance-audit** — conditional: latency, throughput,
   scalability, memory, energy, or deployment performance claims.
15. **paper-dataset-benchmark-paper** — conditional: dataset, benchmark,
   leaderboard, or evaluation-suite contributions.
16. **paper-user-study-audit** — conditional: user studies, annotators, surveys,
   interviews, or human evaluation.
17. **paper-citation-check** — references real & resolving (resolve every DOI,
   verify author lists; trust errors over year/venue warnings); fix placeholders.
18. **paper-security-ethics-safety** — privacy, data rights, human subjects,
   dual-use, threat model, safety, responsible release.
19. **paper-limitations-threats** — limitations and threats to validity that are
   honest, non-apologetic, and acceptance-protective.
20. **paper-writing-auditor** — grammar, spelling, punctuation, readability,
   ambiguity, flow, transitions, acronyms, tone, and overclaim wording; writing
   only.
21. **paper-ai-prose-signals** — generic/AI prose; measurable diagnostics, slice
   from the abstract; sharpen (prose only).
22. **paper-artifact-evaluation** — code/data/model package, reproduction
   commands, environment, checksums, licenses, artifact appendix.
23. **paper-repro-compliance** — measurement protocol, statistical floors,
   artifacts/DOI, pre-submission PDF gates, venue policy (use the IEEE Access
   example calibration below only after verifying current venue guidance).
24. **paper-external-review-triage** — only when adjudicating a Gemini/ChatGPT/
   tool review: bucket comments, drop PDF/extraction artifacts and decision
   collisions, act on genuine defects.
25. **paper-rebuttal-response** — only after real reviewer comments exist:
   response strategy, rescue plan, and revision letter.

(If the focused skills are not installed, perform each step's procedure inline.)

## IEEE Access example calibration
The focused skills are venue-agnostic. Use this section as an **example
calibration for an IEEE Access-style review**, not as timeless venue truth. Before
acting on any item, check the current IEEE Access author instructions, editorial
policies, template, and submission system guidance.

### Decision mechanics → reviewer persona
- **Example premise to verify:** if the venue uses a binary accept/reject process
  or offers no major-revision round, then checklist compliance becomes much more
  important than it would be in a revision-friendly journal.
- **Example calibration data to verify before use:** current acceptance rate,
  revision mechanics, AE workload, reviewer recruitment practices, and whether
  reviewers may be drawn from the manuscript's reference list.
- **If the verified process is binary / no-second-chance**, treat verifiable
  compliance items (placeholder author bios, missing funding footnote, wrong
  affiliation, style-manual violations) as a separate gate from the science
  score. Clean science can still fail on a checklist item.

### IEEE policy & Editorial Style Manual examples
Verify current wording at submission. Do not apply these from memory.
- **AI-use disclosure:** confirm whether disclosure is required, recommended, or
  optional; where it belongs; what level of detail is required; and whether
  AI-assisted editing is treated differently from AI-generated content.
- **Human/animal subjects:** confirm required IRB/ethics approval, exemption,
  consent, and clinical/human-data wording.
- **Editorial style examples to check:** abstract word limit and paragraphing;
  whether math/references are allowed in the abstract; figure/table caption
  style; units, dashes, percent rules; and where funding must be declared.
- **PDF gate:** derive the actual checks from the verified current style manual
  and rendered PDF, not from stale assumptions.

## Consolidated output
- One issue table per check (location, issue, severity, `was → is`).
- The 20 highest-ROI revisions, ranked by impact on acceptance probability.
- Science-fidelity gate: claims that must be downgraded or experimentally
  supported before submission.
- Final verdict: Reject % / Major-rev % / Minor-rev % / Accept %; Top-5 concerns;
  Top-5 strengths; an honest overall assessment.
