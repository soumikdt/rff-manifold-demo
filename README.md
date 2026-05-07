# RFF Manifold Demo

Code release for the paper:

**"Random Fourier Features on Manifolds: Uniform Kernel Distance Preservation and Topological Guarantees"**

## Contents

| File | Description |
|------|-------------|
| `RFF_map_demo.ipynb` | Generates Figure 1: RFF distance-ratio error quantiles vs. target dimension *t* on the slow helix and the unit sphere *S*^{N−1} |

## What the notebook does

The notebook demonstrates the main empirical claim of the paper: for a 1-dimensional manifold (the slow helix in *R*^N with N = 100) and for a high-dimensional sphere, the RFF embedding achieves small relative error in pairwise kernel distances using far fewer features than the ambient dimension suggests.

It:
1. Samples 1 000 points on the slow helix and on *S*^{99} using quasi-random (Sobol) sampling.
2. For each target dimension *t* ∈ {20, 30, …, 90}, draws 200 independent RFF projections and records the maximum pairwise distance-ratio error `max_{i<j} | ||z_i - z_j|| / ||x_i - x_j|| − 1 |`.
3. Plots the 95th, 99th, and 100th percentiles of that error across seeds.

## Requirements

```
numpy
scipy
pandas
matplotlib
openpyxl
```

Install with:

```bash
pip install numpy scipy pandas matplotlib openpyxl
```

## Running

```bash
jupyter notebook RFF_map_demo.ipynb
```

Run all cells in order. The notebook first generates `experiment_data/rff_quantiles_vs_t.xlsx` (the raw results table) and then reads it back to produce `experiment_data/rff_quantiles_vs_t.png`.

## Citation

If you use this code, please cite:

```bibtex
@article{rff_manifold_2025,
  title   = {Random Fourier Features on Manifolds: Uniform Kernel Distance Preservation
             and Topological Guarantees},
  author  = {},
  year    = {2025},
  note    = {Preprint}
}
```

(Citation details will be updated on publication.)
