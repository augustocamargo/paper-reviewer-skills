---
name: paper-venue-fit-strategy
description: >
  Assess CS/AI venue fit and submission strategy: whether the paper is better
  suited for ML, NLP, CV, systems, HCI, security, data management, software
  engineering, workshop, journal, or interdisciplinary venues. Use when the user
  asks "where should I submit", "is this venue a good fit", "what bar should I
  target", or "how do I adapt for this venue".
---

# Venue fit & strategy

## Venue-fit dimensions
- Audience problem: who must care?
- Contribution type: theory, method, benchmark, system, dataset, empirical
  study, application, negative result, position, artifact.
- Evidence bar: novelty, rigor, scale, ablation depth, real users, deployment,
  proofs, artifact, reproducibility, ethics.
- Review culture: surprise vs validation, short-paper tolerance, benchmark/SOTA
  expectations, artifact emphasis, desk-reject triggers.
- Scope risk: too applied for theory venues; too engineering for ML venues; too
  model-centric for systems venues; too narrow for general journals.

## Strategy checks
1. Identify the best-fit primary venue and two fallback venues.
2. Map the paper's strongest evidence to each venue's review criteria.
3. Flag likely desk-reject or early-reject issues: formatting, page limits,
   anonymity, missing ethics, noncompliant artifacts, out-of-scope framing.
4. Recommend framing changes by venue: title, abstract, contribution bullets,
   experiments to foreground, related-work taxonomy.
5. Decide whether the paper needs more science, more engineering evidence, or
   only better positioning.

## Output
- Venue ranking: `venue/type | fit | main risk | needed adaptation`.
- Submission-readiness verdict for the target venue.
- Framing changes for the chosen venue.
- "Do not submit here unless..." warnings for poor-fit venues.
