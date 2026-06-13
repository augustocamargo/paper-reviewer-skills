---
name: paper-figure-table-auditor
description: >
  Audit figures and tables in CS/AI papers for presentation quality: captions,
  legends, units, axis labels, table readability, formatting consistency,
  decimal precision, significant digits, self-contained interpretation, and
  reviewer usability. Use when the user asks whether figures/tables are clear,
  publication-ready, readable, self-contained, or consistent.
---

# Figure & table auditor

## Goal
Make figures and tables easy for a reviewer to understand without hunting
through the prose.

## Checks
1. **Self-contained captions.** Captions state what is plotted, the task/data,
   metric, direction of better, key condition, and takeaway when appropriate.
2. **Legends and labels.** Axis labels, legends, abbreviations, units, and method
   names are complete, readable, and consistent with the text.
3. **Units and scales.** Units appear wherever needed; log/linear scales,
   normalization, percentages, and aggregation windows are explicit.
4. **Table readability.** Headers are clear; groups and row order are logical;
   alignment, spacing, and emphasis help comparison rather than decorate.
5. **Precision and significant digits.** Decimal places are consistent within a
   metric and not more precise than the measurement supports.
6. **Formatting consistency.** Figure/table numbering, caption style, font size,
   notation, colors, symbols, and abbreviations match across the paper.
7. **Accessibility.** Avoid color-only distinctions; ensure line styles, markers,
   contrast, and grayscale print remain understandable.
8. **Statistical display.** Error bars, confidence intervals, sample sizes, seeds,
   and aggregation rules are visible when relevant.
9. **Reviewer scan test.** A reader should understand the main result from the
   figure/table plus caption alone.

## Do not do
- Do not recompute numbers; route that to `paper-claims-vs-data`.
- Do not decide whether experiments are sufficient; route that to
  `paper-experiment-design`.
- Do not judge novelty or venue fit.

## Output
- Figure/table issue table:
  `item | issue | reviewer impact | concrete fix`.
- Precision/units consistency list.
- Caption rewrite suggestions.
- Self-containedness verdict for each major figure/table.
