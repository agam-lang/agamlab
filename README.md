# 🔬 AGAMLAB — Interactive Scientific & Numerical Computing Platform

> Part of the [agam-lang](https://github.com/agam-lang) organization.  
> A MATLAB/Julia-class interactive scientific computing and numerical visualization environment built natively on top of the **Agam** compiler, runtime, and hardware acceleration pipeline.

---

## 🏛️ Architecture & Crate Ecosystem

AGAMLAB is composed of 8 specialized modular crates providing high-performance linear algebra, signal processing, statistical distributions, terminal and SVG plotting, an interactive REPL, and a native notebook engine:

```
                               ┌──────────────────────────┐
                               │       agamlab_repl       │ (Interactive JIT REPL)
                               │     agamlab_notebook     │ (Native Notebook Engine)
                               └────────────┬─────────────┘
                                            │
               ┌────────────────────────────┼────────────────────────────┐
               ▼                            ▼                            ▼
      ┌─────────────────┐          ┌─────────────────┐          ┌─────────────────┐
      │ agamlab_matrix  │          │ agamlab_signal  │          │  agamlab_stats  │
      │ (SIMD/BLAS GEMM)│          │ (FFT/FIR/IIR)   │          │ (MCMC/PDF/CDF)  │
      └────────┬────────┘          └────────┬────────┘          └────────┬────────┘
               │                            │                            │
               └────────────────────────────┼────────────────────────────┘
                                            ▼
                               ┌──────────────────────────┐
                               │       agamlab_plot       │ (SVG & Terminal Visualizer)
                               │        agamlab_io        │ (HDF5/CSV/Arrow Data I/O)
                               │       agamlab_core       │ (Shared Numerical Context)
                               └──────────────────────────┘
```

---

## 📦 Crate Inventory

| Crate | Directory | Purpose & Key Features |
| :--- | :--- | :--- |
| **`agamlab_core`** | [`crates/agamlab_core/`](crates/agamlab_core/) | Shared numerical context, precision traits, and session state management. |
| **`agamlab_matrix`** | [`crates/agamlab_matrix/`](crates/agamlab_matrix/) | Dense and sparse 2D/3D matrix operations, LU/QR/SVD decomposition, and SIMD GEMM. |
| **`agamlab_signal`** | [`crates/agamlab_signal/`](crates/agamlab_signal/) | Fast Fourier Transforms (FFT/IFFT), FIR/IIR multi-rate filters, and spectral analysis. |
| **`agamlab_stats`** | [`crates/agamlab_stats/`](crates/agamlab_stats/) | Probability distributions, Bayesian MCMC sampling, regression, and hypothesis testing. |
| **`agamlab_plot`** | [`crates/agamlab_plot/`](crates/agamlab_plot/) | 2D/3D line plots, scatter plots, heatmaps, histograms, and SVG export. |
| **`agamlab_repl`** | [`crates/agamlab_repl/`](crates/agamlab_repl/) | Interactive terminal REPL with live syntax highlighting and autocompletion. |
| **`agamlab_notebook`**| [`crates/agamlab_notebook/`](crates/agamlab_notebook/)| Interactive JSON notebook execution kernel with cell state caching. |
| **`agamlab_io`** | [`crates/agamlab_io/`](crates/agamlab_io/) | High-throughput data ingestion for CSV, Arrow, Parquet, and binary matrix formats. |

---

## ⚡ Quick Start

### 1. Build and Test the Complete Workspace
```bash
# Check all AGAMLAB crates
cargo check

# Run the comprehensive test suite
cargo test --all
```

### 2. Launch the Interactive Scientific REPL
```bash
cargo run -p agamlab_repl
```

---

## 📜 License

Dual-licensed under [MIT](LICENSE-MIT) and [Apache 2.0](LICENSE-APACHE).
