---
name: paper-limitations-threats
description: >
  Strengthen limitations and threats-to-validity sections for CS/AI papers. Use
  when the user asks "are my limitations good", "what threats to validity should
  I mention", "will reviewers trust the caveats", or "how do I disclose
  weaknesses without hurting acceptance". Keeps caveats honest and strategic.
---

# Limitations & threats-to-validity audit

## Principle
Good limitations reduce reviewer attack surface. They admit scope without
undercutting the core contribution.

## Threat categories
- **Construct validity:** metric measures the intended concept?
- **Internal validity:** causal claim isolated from confounds?
- **External validity:** generalizes across data, domains, hardware, models,
  languages, workloads, users?
- **Statistical conclusion validity:** enough power/seeds/samples; correct test?
- **Implementation validity:** code, dependency, hardware, precision, or runtime
  choices could change results?
- **Ethical/social validity:** deployment assumptions, population harms, misuse?

## Checks
1. Every major claim should have a matching scope boundary.
2. Limitations should name concrete regimes, not vague humility phrases.
3. Do not bury fatal weaknesses; reframe as operating envelope or future work
   only when the evidence supports it.
4. Mention mitigations already performed: ablations, multiple datasets, checksums,
   seeds, independent implementations, subgroup analysis, or artifact release.
5. Avoid apologetic prose. Use engineering language: "The method assumes...",
   "The evaluation covers...", "The results do not establish...".

## Output
- Threat table: `claim | plausible threat | current coverage | fix`.
- Missing limitations ranked by reviewer likelihood.
- Replacement wording for weak/generic caveats.
- List of caveats that would harm acceptance because they imply an untested
  fatal flaw; suggest narrower, evidence-faithful wording.
