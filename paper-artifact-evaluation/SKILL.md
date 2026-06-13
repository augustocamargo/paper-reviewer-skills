---
name: paper-artifact-evaluation
description: >
  Prepare or audit research artifacts for CS/AI venues: code, data, models,
  Docker/Conda, README, scripts, checksums, licenses, reproducibility badges,
  and artifact-evaluation expectations. Use when the user asks "is my artifact
  ready", "prepare artifact appendix", "reproduce my paper", or "AE checklist".
---

# Artifact evaluation & reproducibility package

## Artifact contents
Require, as applicable:
- Versioned code repository and archived DOI release.
- Environment spec: Dockerfile, Conda/uv/pip lockfile, compiler/CUDA versions,
  OS, driver, hardware, and random seeds.
- Data download/preparation scripts, checksums, and license notes.
- Model checkpoints or instructions to regenerate them.
- One-command smoke test and one-command full reproduction path.
- Mapping from paper tables/figures to scripts and output files.
- Runtime/compute estimates and expected numerical tolerances.

## Audit
1. Run or inspect the smoke-test path before claiming reproducibility.
2. Check that scripts do not require private absolute paths, hidden credentials,
   undocumented data, GUI sessions, or manual notebook clicks.
3. Separate fast validation from expensive full reproduction.
4. Preserve exact versions used for the paper; a "latest" dependency is a risk.
5. Include license compatibility for code, data, pretrained models, and third
   party assets.
6. Confirm anonymization requirements for double-blind review.

## Output
- Artifact readiness: pass / weak pass / fail, with reason.
- Checklist: `item | present | verified | fix`.
- Minimal `README`/artifact-appendix outline.
- Reproduction command map: `paper result | command | expected output | time`.
