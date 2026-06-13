---
name: paper-ai-prose-signals
description: >
  Detect generic / AI-generated-sounding academic prose and make it read like a
  domain expert wrote it — without changing the science. Flags uniform sentence
  rhythm, overused connectives, hollow wrap-ups, marketing tone, and adjectives
  where numbers belong. Use when the user says "does this read AI-generated",
  "make it sound less generic / less like ChatGPT", "a detector flagged my
  paper", or "tighten the writing". Prose only; never alters results.
---

# AI / generic-prose signals

## What to flag (quote the excerpt, say why)
- **Uniform rhythm / predictable structure** — every sentence one clean clause;
  repeated openings (". The", ". This").
- **Overused connectives**: Furthermore, Moreover, Notably, Consequently, "It
  is worth noting", "It should be noted".
- **Hollow wrap-ups**: "Together, these observations suggest…", "These results
  highlight…" — sentences that add no information.
- **Adjectives where numbers exist**: "high", "most", "competitive",
  "significant" when the value is available — replace with the number.
- **Marketing / grant-proposal tone**; generic mission-statement openers;
  unsupported "may generalize to broader classes".

## Measurable diagnostics (don't eyeball — count)
- **Sentence-length histogram.** Hard rule: any sentence ≥46 words must break;
  36–45 words break at a natural `:` / `;` / `—`. Fix the long tail and clusters,
  not a global average.
- **Connector tics.** Count occurrences of each ("therefore", "furthermore",
  "moreover", "notably") and cut them down (e.g., 25 → 11), not to zero.
- **Repeated openers.** Flag runs of **≥3 consecutive sentences** with the same
  opening word/structure.
- **Vague demonstratives.** Flag "This/These + verb" with no noun ("This shows…",
  "These suggest…") — name the subject.
- **Slice from `\begin{abstract}`, not `\section{Introduction}`.** The abstract
  is the most-read paragraph and easily escapes length/style passes that start at
  the intro. Treat equation displays as sentence boundaries and include
  `\item` text. Re-run all diagnostics after any later rewrite wave.

## How to fix
- Replace adjectives with the actual measured numbers.
- Cut the hollow wrap-up sentence or replace it with one concrete fact.
- Vary sentence length/openings; break the one-clause monotony.
- Lead paragraphs with the result/mechanism, not a restatement of the mission.
- **Quantify a style criticism before acting on it.** Before cutting "the
  Discussion is repetitive, trim 20–30%", measure term frequencies and section
  proportions; the criticism is often refuted by the data. Same trace-before-fix
  discipline as for numbers.
- **Assertion order is posture.** Prefer positive-first ("The contribution is Y.
  It is not X.") over negation-first ("not X but Y") — the latter reads defensive
  and is itself an LLM-tic-shaped template. Anchor content, not surface phrasing.

## Honest caveats (tell the user)
- AI-detector scores (e.g., GPTZero) are **unreliable on formal technical
  writing** — uniform, hedged academic prose scores high even when fully human.
  Treat the score as a style signal, not proof.
- Separate this from **policy**: most venues now require disclosing AI-*generated
  content* (system, sections, level of use), while AI-*assisted editing* is
  usually recommended-but-not-required. Check the target venue's author policy
  for exact wording/placement; point the user there if relevant.

## Output
- Table: `location | excerpt | why it reads artificial | suggested direction`.
- Prose-only edits; do not touch numbers, tables, equations, or citations.
