# Paper Reviewer Skills

Skills for reviewing computer science and AI papers with two goals:

1. **Science fidelity:** claims should be true, traceable, reproducible, and
   honestly scoped.
2. **Acceptance readiness:** the paper should survive real CS/AI review dynamics:
   novelty pressure, baseline demands, venue fit, reviewer triage, compliance,
   and rebuttal strategy.

This repository is a skill pack for paper review. It is meant to help authors,
reviewers, and research groups run structured pre-submission audits on papers in
AI, ML, NLP, CV, systems, security, HCI, data management, software engineering,
and adjacent CS venues.

## Design Principles

- **Verify before fixing.** A criticism can be wrong; check the paper, data,
  rendered PDF, references, or venue policy before changing anything.
- **Trace claims to evidence.** Numbers should come from tables, figures, logs,
  CSVs, or scripts, not memory or prose.
- **Separate truth risk from review risk.** A paper can be scientifically sound
  but poorly positioned; it can also be compelling but under-supported.
- **Do not invent evidence.** Reframe or downgrade unsupported claims instead of
  making the paper sound stronger than the data allow.
- **Venue details change.** Acceptance rates, revision mechanics, AI-use policy,
  formatting rules, funding placement, and artifact expectations must be checked
  against the current venue guidance at submission time.

## Contributions Welcome

This project is open to contributions from researchers, reviewers, and engineers
interested in scientific writing, peer review, and publication quality.

Feel free to:

- Open issues
- Suggest new review skills
- Improve existing prompts
- Add journal-specific reviewers
- Report problems
- Submit pull requests

## Skills

The two orchestrators are for full reviews; the focused skills are for specific
review lenses.

| Skill | Use when | What it checks |
| --- | --- | --- |
| `cs-ai-paper-review` | You want a broad pre-submission audit for a CS/AI paper. | Orchestrator, routes through venue fit, reviewer triage, novelty, structure, experiments, baselines, leakage, claims vs data, formulas, artifacts, limitations, compliance, and rebuttal if needed. |
| `ieee-access-review` | IEEE Access, or a similar journal process, is the target. | Orchestrator, applies the core review workflow with IEEE Access-style example calibration; venue-specific details must be verified against current guidance. |
| `paper-busy-reviewer` | You want a fast first-impression or area-chair triage pass. | Abstract, introduction, main figures/tables, conclusion, reviewer reports, apparent importance, clarity, and slot-worthiness. |
| `paper-reviewer-sim` | You want to know what skeptical reviewers will attack. | Weak spots, exaggerated claims, unsupported assertions, venue-fit problems, top concerns/strengths, and publication-risk verdict. |
| `paper-venue-fit-strategy` | You are choosing a venue or adapting to a target venue. | Audience fit, contribution type, review culture, evidence bar, fallback venues, and framing changes. |
| `paper-novelty-positioning` | The paper may be seen as incremental, obvious, or poorly positioned. | Defensible novelty unit, closest prior work, contribution claims, related-work deltas, and reviewer novelty attacks. |
| `paper-abstract-title-contribution` | The title, abstract, or contribution bullets need to survive triage. | First-page clarity, title promises, contribution statement, evidence sentence, scope sentence, and overclaim risk. |
| `paper-claim-evidence-auditor` | You need to map important claims to visible evidence and catch overreach. | Claim type, evidence source, support strength, evidence gap, recommended action, and evidence-faithful rewrites. |
| `paper-structure-pertinence` | The paper feels confusing, defensive, or structurally overloaded. | Section roles, misplaced content, title-term substantiation, local negative-result framing, and missing overview/navigation elements. |
| `paper-experiment-design` | You need to know whether the experiments support the claims. | Claim-to-test mapping, endpoints, datasets, comparators, metrics, seeds, statistical tests, ablations, and missing experiments. |
| `paper-baseline-benchmark-audit` | You are worried about missing baselines or unfair comparisons. | Baseline classes, benchmark credibility, tuning fairness, SOTA expectations, compute matching, and apples-to-apples evaluation. |
| `paper-ml-validity-leakage` | The paper is ML/deep learning/LLM-heavy and needs validity checking. | Train/test leakage, benchmark contamination, prompt leakage, confounding, label noise, metric gaming, and LLM-as-judge validity. |
| `paper-claims-vs-data` | Results changed, numbers may have drifted, or submission is near. | Quantitative claims against tables, figures, raw data, CSVs, logs, captions, and hand-written artifacts. |
| `paper-figure-table-auditor` | Figures or tables need to be clear, self-contained, readable, and publication-ready. | Captions, legends, units, axis labels, table readability, formatting consistency, decimal precision, significant digits, and accessibility. |
| `paper-formula-audit` | The paper contains equations, derivations, or Big-O claims. | Dimensions, indices, bounds, sign conventions, implementation consistency, and complexity/asymptotic claims. |
| `paper-theory-proof-audit` | The paper includes theorems, guarantees, convergence, or formal claims. | Assumptions, theorem statements, lemmas, proof dependency, quantifiers, boundary cases, tightness, and counterexamples. |
| `paper-systems-performance-audit` | The paper reports latency, throughput, speedup, scaling, memory, energy, or cost. | Measurement protocol, stack disclosure, workload realism, baseline fairness, bottlenecks, variance, and regime-specific claims. |
| `paper-dataset-benchmark-paper` | The contribution is a dataset, benchmark, leaderboard, challenge, or evaluation suite. | Dataset need, collection, licensing, annotation quality, documentation, splits, baselines, metrics, and saturation risk. |
| `paper-user-study-audit` | People are participants, annotators, judges, users, or subjects. | Recruitment, consent, IRB/exemption, study design, randomization, sample size, instruments, qualitative coding, and human-eval validity. |
| `paper-citation-check` | References were imported quickly or the bibliography needs a reality check. | Cited vs defined keys, undefined/uncited entries, placeholders, author/title/venue/year correctness, and DOI resolution. |
| `paper-security-ethics-safety` | The paper involves user data, scraping, security, privacy, safety, dual use, or deployment risk. | Data rights, consent, PII, privacy, human-subject risk, threat model, misuse paths, model safety, and responsible release. |
| `paper-limitations-threats` | Limitations or threats to validity need to be honest but not self-sabotaging. | Construct/internal/external/statistical/implementation validity, missing caveats, overbroad claims, and scope boundaries. |
| `paper-artifact-evaluation` | Code, data, models, or reproduction materials need to be release-ready. | Repositories, DOI releases, environments, data scripts, checksums, licenses, smoke tests, full reproduction, and artifact appendix. |
| `paper-repro-compliance` | Submission is near and reproducibility or policy compliance needs checking. | Measurement protocol, artifacts, persistent DOI, AI-use disclosure, ethics statements, style rules, funding placement, and PDF gates. |
| `paper-writing-auditor` | You want a scientific writing edit without judging novelty, experiments, statistics, methodology, significance, or contribution. | Grammar, spelling, punctuation, readability, ambiguity, repetition, flow, paragraph structure, transitions, title/acronym consistency, tone, and overclaim wording. |
| `paper-ai-prose-signals` | The writing sounds generic, AI-like, repetitive, or too polished in the wrong way. | Sentence rhythm, repeated openers, overused connectors, vague demonstratives, hollow wrap-ups, and adjectives where numbers belong. |
| `paper-external-review-triage` | Another LLM or automated tool produced a review and you need to decide what to trust. | Macro points, PDF extraction artifacts, decision collisions, generic priors, genuine fixable defects, and routes to focused skills. |
| `paper-rebuttal-response` | Reviews arrived and you need a response, rebuttal, or revision plan. | Reviewer comment triage, fatal vs fixable issues, misreads, response strategy, rescue priorities, and concise rebuttal drafting. |

## Suggested Usage

For a full pre-submission review:

```text
Use cs-ai-paper-review on this paper for a science-fidelity and acceptance-risk audit.
Target venue: <venue name>.
Paper files: <PDF/source/data paths>.
```

For a focused check:

```text
Use paper-experiment-design to check whether the experiments support the claims.
```

For reviewer response:

```text
Use paper-rebuttal-response on these reviewer comments and propose a rescue plan.
```

For venue-specific use, always provide the target venue and submission date when
possible. If a skill mentions venue policy, treat it as a checklist item to
verify, not as authoritative policy text.

## Installation

Copy the skill directories into your skills directory, or symlink this
repository's skill folders from there. Each skill is self-contained and consists
of a `SKILL.md` file inside its own directory.

Example layout:

```text
paper-skills/
  cs-ai-paper-review/
    SKILL.md
  paper-experiment-design/
    SKILL.md
  ...
```

Depending on your LLM setup, local skills may live under a directory such as:

```
~/.codex/skills/
~/skills
```

After copying or symlinking, restart the LLM or refresh the skill index if your
environment requires it.

## Public-Repo Hygiene

This repository is intended to contain only public review procedures, not paper
drafts, private datasets, reviewer comments, API keys, or confidential project
material.

## Scope

These skills help structure a review. They do not replace:

- reading the current venue author instructions;
- verifying citations against authoritative sources;
- checking the rendered PDF;
- recomputing results from raw data;
- domain-expert judgment.

The safest pattern is: **review, verify, then edit**.
