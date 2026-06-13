---
name: paper-theory-proof-audit
description: >
  Audit theoretical CS/AI content: theorem statements, assumptions, proofs,
  lemmas, counterexamples, convergence claims, bounds, reductions, and notation.
  Use when a paper includes proofs, guarantees, regret/sample-complexity bounds,
  convergence arguments, privacy/security proofs, or formal claims.
---

# Theory & proof audit

## Checks
1. **Statement precision.** The theorem names all assumptions, domains,
   randomness, constants, asymptotic variables, and probability qualifiers.
2. **Assumption visibility.** No hidden smoothness, boundedness, independence,
   realizability, convexity, distribution, oracle, or finite-precision assumption.
3. **Proof dependency graph.** Lemmas prove exactly what later steps need; no
   circular dependency or stronger unstated result.
4. **Quantifiers.** Check for swapped "for all" / "there exists", expectation vs
   high-probability, asymptotic vs finite-sample, average-case vs worst-case.
5. **Boundary cases.** Test n=1, empty graph, zero variance, singular matrix,
   degenerate labels, duplicate points, adversarial input, or equality cases.
6. **Tightness and meaning.** State whether the bound explains the empirical
   result or merely exists. Avoid dressing a loose guarantee as practical.
7. **Notation consistency.** One symbol, one meaning; no overloaded N/n/T/K/d
   across sections without reset.

## Output
- Theorem table: `claim | assumptions explicit? | proof gap | severity`.
- Counterexample/boundary-case attempts and whether they break the claim.
- Corrected formal wording for overbroad claims.
- Proof-risk verdict: sound / likely sound with edits / gap / false or unproven.
