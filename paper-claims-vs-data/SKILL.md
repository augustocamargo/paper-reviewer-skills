---
name: paper-claims-vs-data
description: >
  Cross-check every quantitative claim in a paper/draft against its source —
  the tables, figures, and the raw results (CSV/logs) — and flag drift between
  prose, tables, and data. Use when the user says "check the claims vs the
  numbers", "do the numbers in the text match the tables/data", "is the prose
  consistent with the results", or after regenerating results. Also recommends a
  single-source-of-truth setup so numbers can't drift again.
---

# Claims × Data cross-check

Goal: every figure-in-text traces to source data, and prose = tables = figures.

## Principles
- **Trace to source, not to memory or to the prose.** Recompute each value
  independently from the raw data (CSV/results/logs); don't trust the paragraph.
- **Verify before "fixing."** If a number looks wrong, confirm against the raw
  data first — the prose may be right and your intuition (or a reviewer's) wrong.
  Never change a value without a source check; an unverified fix can introduce
  an error.

## Procedure
1. Inventory every quantitative claim in the prose (speedups, accuracies,
   p-values, ranges, percentages, counts).
2. For each, locate the matching value in (a) the table/figure and (b) the raw
   data. Recompute from raw where feasible (same metric, same window, same
   rounding).
3. Confirm the **same metric uses the same source everywhere** (e.g., latency
   from the dedicated sweep, not a different measurement window).
4. **Unify precision.** The same metric must appear at one precision across
   prose and tables (e.g., F1 = 0.948 in prose vs 0.9477 in a table is drift).
   Enforce in the generators, never by hand.
5. **Audit hand-written artifacts separately.** Captions, abstract, and
   manually built tables (e.g., an analysis-plan "Reported in" column, stale
   "Chip-Level" labels, an abstract `$\times$` regression) are **not reached by
   the number-macro pipeline** and are where drift hides. Cross-check each
   against the data / decisions log explicitly.
6. Report mismatches as a table: `claim | location | prose says | data says | source`.
7. Classify each: wrong / stale (drift) / imprecise / OK.

## Recommend a single source of truth
To prevent recurrence: generate inline numbers as LaTeX macros
(`\newcommand`) from the analysis pipeline, `\input` them in the preamble, and
use the macros in BOTH prose and tables. Then a data change updates every
figure-in-text on rebuild. Offer to build the generator (`make macros`).

## Output
- The mismatch table (`was → is`, with source).
- Confirmation of which claims are verified-correct.
- Any fix proposed must reuse values already in the data — never invent numbers.
