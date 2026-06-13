---
name: paper-repro-compliance
description: >
  Check a paper's reproducibility and venue compliance: measurement protocol
  soundness, artifact availability (code/data with a persistent DOI), and the
  generic policy items most venues require (AI-use disclosure, human-subjects/IRB
  statement, style-manual conformance, reproducibility expectations). Use when
  the user asks "is this reproducible", "check venue compliance", "do I need an AI
  disclosure", "where do funding/ethics statements go", or "is the benchmark
  methodology sound". Venue-agnostic — confirm exact wording against the target
  venue's author guide (for IEEE Access specifics, see ieee-access-review).
---

# Reproducibility & compliance check

## Measurement validity
- Is the timing protocol stated and sound: warmup iterations, trials with
  median-of-medians, confidence intervals?
- Was the environment controlled: **freshly booted, background load settled,
  headless over SSH** (interactive GUI sessions perturb sub-millisecond timing);
  **dedicated GPU** with no co-resident jobs on NVIDIA?
- Are noisy/contaminated runs (e.g., GUI-active probes) excluded, and is the
  exclusion stated?
- **Measure directly, beware derived quantities.** A counter read *inside* a
  tight loop can inflate a metric massively (e.g., per-call NVML reads inflated
  energy ~35×); prefer a directly-measured counter over `P̄·t̄`.
- **Statistical floors & single-split fragility.** Watch for test-specific
  p-floors (Wilcoxon signed-rank at n=5 cannot go below p=0.0625, so "n.s." may
  be unreachable-by-design). A single train/test split that looks significant can
  **evaporate under multi-seed** — prefer multi-seed runs and report
  non-inferiority/equivalence where appropriate.

## Artifacts
- Code + data available with a **persistent DOI** (Zenodo/figshare) and a living
  repo (GitHub); cite the **version DOI**, not just the URL.
- Prefer a **regeneration script + selection metadata + checksums** over
  redistributing datasets; link license-restricted datasets to their official
  source rather than re-hosting. State licenses (and dual-license code vs data).
- A manifest mapping each table/figure → command → output strengthens the claim.

## Venue policy (confirm exact wording in the target venue's author guide)
These items are required by most venues; the **specifics differ per venue**, so
look them up rather than assuming:
- **AI-use disclosure**: name the AI system, the specific sections, and the level
  of use. AI-*generated content* generally must be disclosed; AI-*assisted
  editing/grammar* is usually recommended-but-not-required. AI cannot be an
  author; authors remain fully accountable. (Placement — Acknowledgments vs other
  — is venue-specific.)
- **Human/animal subjects**: IRB/ethics approval (or exemption) statement for
  clinical/human data; consent statement.
- **Style manual conformance**: abstract length limit and formatting,
  figure/table caption conventions, units/dashes/percent rules, and where funding
  is declared (first-page footnote vs Acknowledgments) — all per the venue's
  style manual.

## Pre-submission PDF gates (run as commands, on the *rendered* PDF)
- `pdftotext` then `grep '??'` and `grep -i TODO` must return **empty** (no
  undefined refs `??`, no leftover TODOs).
- Abstract within the **venue's word limit**, and (if the venue forbids it)
  **zero `$` math tokens** in the abstract.
- Verify on the **rendered** PDF (`pdftoppm` to images), not the extracted text —
  extraction artifacts (dropped math tokens, glyph noise) are not real defects.

## Output
- Checklist with status per item (present / missing / needs author input).
- Concrete fixes: drafted disclosure/ethics wording where applicable; placement
  per the target venue's author guide.
