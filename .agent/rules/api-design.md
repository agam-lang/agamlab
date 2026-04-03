# API Design Rules

- AGAMLAB APIs should feel familiar to MATLAB and NumPy users.
- Function names should be concise and domain-standard (e.g., `fft`, `svd`, `linspace`).
- All public functions must include docstrings with examples.
- Prefer value semantics for small matrices, reference semantics for large data.
