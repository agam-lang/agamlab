# Numerical Accuracy Rules

- All matrix operations must preserve numerical stability.
- Use compensated summation (Kahan) for reductions over large arrays.
- Document precision guarantees for every public API.
- Test edge cases: NaN, Inf, denormals, near-zero determinants.
