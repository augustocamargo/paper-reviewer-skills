---
name: paper-formula-audit
description: >
  Audit the equations/formulas in a paper for correctness: dimensional
  consistency, indices and summation bounds, sign conventions, and — most
  importantly — asymptotic / computational-complexity claims. Use when the user
  asks "are the formulas right", "check the equations", "audit the complexity
  analysis", or "is the Big-O claim correct". Checks math, not prose style.
---

# Formula / equation audit

## Per-equation checks
1. **Dimensions/shapes** line up (matrix products: inner dims match; output
   shape is what the text claims).
2. **Indices and bounds** are correct (summation ranges, off-by-one in
   center/edge grids, e.g. interior points of `linspace(a,b,M+2)[1:-1]`).
3. **Sign conventions** are consistent; note when a sign is irrelevant (e.g.,
   the imaginary term inside a magnitude `R²+I²`).
4. **Consistency with the implementation/reference** — the equation should
   match the code that produced the results.

## Scrutinize asymptotic / complexity claims hardest
This is where strong papers get decapitated by a theory reviewer.
- Identify **which variable actually governs** the trade-off, and hold the
  others fixed explicitly.
- Classic trap: comparing a proposed `O(N·M)` cost to an FFT `O(N·logN)` cost
  and calling the FFT "asymptotically favorable as N grows." If `M` is a fixed
  architectural constant, `O(NM)` is *linear* and **wins** as N→∞; the FFT is
  favorable only in the *practical* regime where `M > log₂N`. State the
  governing inequality and the regime, and tie it to any empirical crossover.
- Use the limit to settle direction: `lim_{N→∞} (N logN)/(NM) = (logN)/M → ∞`.

## Output
- Per-equation verdict: correct / typo / wrong; with the exact issue.
- For complexity/asymptotic prose: the corrected statement naming the governing
  variable and regime. (Equations themselves usually need no change — the error
  is typically the surrounding asymptotic claim.)
- Never "fix" a formula without confirming the intended math; flag, don't guess.
