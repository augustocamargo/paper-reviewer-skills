---
name: paper-writing-auditor
description: >
  Audit scientific writing quality in CS/AI papers without judging the science:
  grammar, spelling, punctuation, readability, ambiguity, repetition, paragraph
  flow, transitions, title consistency, acronym consistency, IEEE/ACM tone, and
  overclaim wording. Use when the user asks for a writing edit, language audit,
  clarity pass, copyedit, readability review, or "act like a scientific editor".
  Do not review novelty, experiments, statistics, methodology, significance, or
  contribution.
---

# Scientific writing auditor

## Scope
This is a writing and copyediting pass only. It improves how the paper says
things, not what the paper proves.

## Do not review
- Novelty.
- Experiments.
- Statistics.
- Methodology.
- Significance.
- Contribution.
- Whether the scientific claim is true.

If a sentence seems scientifically unsupported, flag the wording as overclaiming
and route the evidence question to `paper-claim-evidence-auditor`,
`paper-experiment-design`, or `paper-claims-vs-data`.

## Writing checks
1. **Grammar, spelling, punctuation.** Fix errors and awkward constructions.
2. **Readability.** Shorten long sentences, remove needless nominalizations, and
   prefer direct technical prose.
3. **Ambiguity.** Flag unclear antecedents, vague "this/these", overloaded
   terms, unclear comparisons, and ambiguous scope.
4. **Repetition.** Remove repeated claims, repeated paragraph openings, and
   redundant summary sentences.
5. **Flow and paragraph structure.** Each paragraph should have one job, a clear
   topic sentence, and a logical order from context to claim to evidence.
6. **Transitions.** Replace mechanical connectors with transitions that explain
   the relationship between ideas.
7. **Title and terminology consistency.** Ensure title terms, keywords, method
   names, datasets, metrics, and acronyms are used consistently.
8. **Acronyms.** Define on first use, avoid redefining, and do not introduce
   acronyms that are used only once.
9. **IEEE/ACM tone.** Prefer precise, restrained, evidence-faithful academic
   prose over marketing language.
10. **Overclaim wording.** Replace universal or causal language with scoped
   wording when the sentence itself overreaches.

## Output
- Writing issue table: `location | issue | why it hurts readability | edit`.
- Optional polished rewrite of selected passages.
- Consistency notes for terms, acronyms, title wording, and tone.
- Route any science/evidence concern to the correct non-writing skill.
