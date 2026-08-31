---
name: paper-surgical-editor
description: >
  Perform an evidence-constrained, whole-manuscript revision after or alongside
  scientific review. Use when the user asks for a senior scientific review plus
  surgical editing, a full-paper revision, a final pre-submission pass, safe
  high-impact corrections, before/after scoring, or an exact change log.
  Preserves the authors' science and voice, edits only what the available
  evidence supports, marks missing evidence instead of inventing it, performs an
  adversarial reread, and reports what changed. For diagnosis without editing,
  use cs-ai-paper-review; for prose-only copyediting, use paper-writing-auditor.
---

# Scientific review and surgical revision

## Mandate

Strengthen the submitted manuscript through the smallest defensible set of
changes. Preserve the contribution, scientific meaning, authorial voice, and
honest limitations. This is a review-and-revision workflow, not a rewrite from
scratch.

The governing rule is **minimum intervention, maximum justified impact**.

## Required material and reading order

Use all material the author provides: manuscript source, rendered PDF,
bibliography, figures, tables, supplements, results, code, prior reviews, and
target-venue guidance. Before editing:

1. Read the complete manuscript in its native order.
2. Inspect the rendered paper when layout, figures, references, or cross-
   references matter. Source inspection alone is insufficient for visual
   defects.
3. Identify the central claim, contribution unit, evidence chain, intended
   audience, and target venue.
4. Inspect the working tree before changing files. Preserve unrelated author
   edits.

If essential material is unavailable, continue with the supported portions and
state exactly what could not be checked.

## Non-negotiable boundaries

- Never invent evidence, results, citations, methods, sample sizes, statistical
  tests, experiments, venue rules, or implementation details.
- Never change a quantitative statement unless its source has been verified.
- Never strengthen causal, comparative, novelty, priority, safety, clinical, or
  generalization language beyond the evidence.
- Preserve technically meaningful repetition, terminology, caveats, and
  definitions. Remove repetition only when it performs no distinct argumentative
  role.
- Preserve valid authorial idiosyncrasy. Do not normalize the manuscript into
  generic, uniformly polished, LLM-like prose.
- Do not hide a limitation that materially affects interpretation.
- Use `[REQUIRES NEW EVIDENCE]`, `[CITATION NEEDED]`, or `[AUTHOR DECISION]` in
  the review record when the text cannot be repaired honestly from available
  material. Do not insert these markers into the manuscript unless requested.
- When the user asks to see proposed wording before modification, stop after the
  before/after proposals and wait for authorization.

## Workflow

### 1. Establish the baseline

State, in one sentence each:

- the paper's main claim;
- its defensible novelty or contribution unit;
- the evidence that carries that claim;
- the most serious scientific weakness;
- the most likely reviewer misreading or attack.

Score the manuscript from 0 to 10 on the dimensions that apply:

| Dimension | Core question |
| --- | --- |
| Contribution clarity | Can a reviewer state what the paper contributes? |
| Novelty positioning | Is the delta from the closest work precise and defensible? |
| Claim-evidence alignment | Does each load-bearing claim match visible evidence? |
| Method transparency | Can the study or system be understood and inspected? |
| Evaluation adequacy | Do the experiments or verification support the stated scope? |
| Reference integrity | Are citations real, accurate, relevant, and sufficient? |
| Structure and argument | Does each section perform its role in a coherent sequence? |
| Figures and tables | Are the visual evidence and captions self-contained? |
| Prose and terminology | Is the writing precise, readable, consistent, and non-generic? |
| Limitations and validity | Are scope boundaries honest and analytically useful? |
| Reproducibility and compliance | Can the work be checked, and does it meet current venue rules? |
| Venue fit | Does the framing match the venue's audience and evidence bar? |

Separate **truth risk** from **review risk**. A sound result may be framed
poorly; a persuasive claim may still lack support.

### 2. Build the revision ledger

Before changing prose, map each material issue to:

`location | problem | evidence | proposed action | change risk`

Use three risk classes:

- **Safe editorial:** grammar, punctuation, consistency, local clarity,
  redundant prose, broken references, or wording that can be repaired without
  changing meaning.
- **Supported substantive:** structure, claim scope, comparison wording, or
  interpretation whose correction is directly justified by the manuscript's
  evidence.
- **Evidence/author required:** a change that would require a new experiment,
  citation, policy decision, scientific judgment, or stronger claim.

Apply safe editorial and supported substantive changes when the user has asked
for revision. Report, but do not fabricate around, evidence/author-required
items.

### 3. Revise in scientific dependency order

Revise the load-bearing argument before polishing sentences:

1. Align the title, abstract, introduction, contribution statement, results,
   discussion, and conclusion around the same supported contribution.
2. Correct claim scope and connect each important claim to its evidence.
3. Put methods, results, interpretation, related work, and limitations in their
   proper sections.
4. Repair section handoffs so that the introduction poses the problem, the
   method operationalizes it, the evaluation tests it, the discussion interprets
   it, and the conclusion closes the promise made by the title.
5. Repair figures, tables, captions, citations, labels, acronyms, and
   terminology.
6. Remove redundant or defensive passages and improve sentence-level clarity.
7. Run the generic/AI-prose pass only after scientific content is stable.

Prefer a local edit over replacing a paragraph, and a paragraph edit over
rewriting a section. Keep labels, citation keys, numerical values, and technical
terms stable unless the verified correction requires changing them.

### 4. Route only to relevant focused skills

Do not run the entire skill pack mechanically. Use the smallest set needed:

- `cs-ai-paper-review` for a deep diagnostic when no reliable review exists;
- `paper-external-review-triage` before acting on third-party or LLM criticism;
- `paper-claim-evidence-auditor` before changing load-bearing claims;
- `paper-claims-vs-data` before editing quantitative results;
- `paper-structure-pertinence` for section roles and title-to-conclusion
  coherence;
- `paper-citation-check` after citations are added, removed, or moved;
- `paper-figure-table-auditor` when visual evidence changes;
- `paper-writing-auditor` and `paper-ai-prose-signals` as the final prose passes;
- the relevant experiment, theory, systems, user-study, ethics, artifact, or
  venue skill when the manuscript actually contains that risk.

Verify current venue policies from authoritative sources when compliance claims
depend on them.

### 5. Perform the adversarial second pass

Reread the revised manuscript as two different reviewers:

1. **Busy reviewer:** title, abstract, introduction, main figures/tables, and
   conclusion. Can this reader identify the contribution, evidence, and scope?
2. **Skeptical specialist:** closest-work comparison, claims, methods,
   evaluation, limitations, citations, and reproducibility. What remains open to
   a concrete rejection argument?

Then rerun checks affected by the edits:

- title/abstract/conclusion consistency;
- claim-to-evidence traceability;
- citation and cross-reference integrity;
- acronym and terminology consistency;
- repeated rhetorical templates and sentence-length outliers;
- clean compilation, tests, or artifact generation where applicable.

Do not declare a check passed unless it was actually run.

## Final output

Return a compact but auditable result:

1. **Executive diagnosis** — contribution, strongest evidence, primary truth
   risk, primary review risk, and readiness verdict.
2. **Baseline scorecard** — applicable dimensions with brief reasons.
3. **Change log** — `location | before/problem | after/action | rationale | risk`.
4. **Unresolved items** — each marked `[REQUIRES NEW EVIDENCE]`,
   `[CITATION NEEDED]`, or `[AUTHOR DECISION]`, with the consequence of leaving
   it unresolved.
5. **Post-revision scorecard** — the same dimensions, with deltas and no inflated
   improvement claims.
6. **Adversarial verdict** — the three most credible remaining reviewer attacks,
   the paper's strongest defenses, and the single highest-value next action.
7. **Editorial accountability** — what was deliberately left unchanged and why.

End with a direct senior-author judgment beginning: **“If this were my paper, I
would…”**

## Quality standard

The revision succeeds when every change can be defended from the manuscript,
its verified evidence, or an authoritative source; the paper reads as the
authors' work; and the remaining uncertainty is visible rather than polished
away.
