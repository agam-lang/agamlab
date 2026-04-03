---
name: numerical-validation
description: Use when implementing or modifying numerical algorithms to ensure correctness and precision.
---

# Numerical Validation

Use this skill when working on matrix operations, signal processing, or statistical functions.

## Workflow

1. Identify the algorithm and its known numerical properties.
2. Compare results against reference implementations (MATLAB, NumPy, SciPy).
3. Test with pathological inputs: singular matrices, near-zero values, very large arrays.
4. Document precision bounds in the function docstring.
5. Add regression tests for edge cases discovered during validation.

## Success Criteria

- Results match reference implementations within documented precision bounds
- Edge cases are explicitly handled and tested
- No silent precision loss in reduction operations
