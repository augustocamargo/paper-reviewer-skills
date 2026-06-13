---
name: paper-abstract-title-contribution
description: >
  Rewrite or audit a CS/AI paper's title, abstract, and contribution bullets for
  reviewer triage. Use when the user asks "fix my abstract", "is the title good",
  "make the contribution clearer", "first page review", or "make this more
  compelling". Preserves scientific claims and numbers.
---

# Title, abstract & contribution surface

## Triage principle
The title, abstract, and contribution bullets must let a tired reviewer answer:
what is new, why it matters, what evidence supports it, and what the limits are.

## Checks
1. **Title.** Accurate, specific, searchable, and not over-promising. Every
   load-bearing title word must be supported in the paper.
2. **First abstract sentence.** Starts with the problem/tension, not a generic
   field mission statement.
3. **Contribution sentence.** Names the actual contribution unit, not a vague
   "framework" or "novel approach" unless that is substantiated.
4. **Evidence sentence.** Includes the key dataset/task/baseline/metric and the
   strongest verified result. Use numbers already checked elsewhere.
5. **Scope sentence.** States the operating envelope or limitation without
   sounding apologetic.
6. **Bullets.** Each bullet should be a claim plus evidence, not a task list.

## Rewrite constraints
- Do not invent numbers, baselines, citations, or scope.
- Keep venue abstract limits and no-math/no-reference rules when applicable.
- Prefer concrete nouns and verbs over "propose", "leverage", "robust",
  "comprehensive", and "significant".

## Output
- Surface diagnosis: title, first sentence, contribution, evidence, scope.
- Revised title options: conservative / sharper / broad-audience.
- Revised abstract or contribution bullets, preserving verified facts.
- Risk notes: claims that need confirmation before submission.
