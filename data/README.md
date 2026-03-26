# Navier-Stokes Data Dictionary

All data files contain JSON-formatted computational results from the 3D NS Jacobian eigenvalue analysis.

---

## Data Files

| File | Description | Key Fields |
|------|-------------|------------|
| **complex_eigenvalues.json** | Ginibre universality analysis — complex nearest-neighbor spacings on the full non-symmetric Jacobian | `re` (Reynolds number), `grid_n`, `ks_complex` (KS distance for complex NN spacings), `beta_complex` (repulsion exponent), `im_range` (imaginary eigenvalue extent), `method` (symmetrised vs complex), `dim` |
| **falsification.json** | Laminar vs turbulent vs pure Stokes base state comparison — the critical falsification test | `re`, `base_state` (turbulent/laminar/stokes), `ks`, `beta`, `interpretation` (near-GUE/Poisson), `grid_n`, `dim` |
| **ns_spectrum.json** | Single NS Jacobian spectrum at Re = 100 — raw eigenvalue data | `re`, `grid_n`, `eigenvalues` (sorted list), `ks`, `beta`, `positive_count`, `total_count`, `eig_range` |
| **reynolds_sweep.json** | Full Reynolds number sweep at N = 12 (dim 5,184) — symmetrised Jacobian statistics across Re = 10-2,000 | `re`, `ks`, `beta`, `eig_range`, `positive_count`, `total_count`, `grid_n`, `dim` |

---

## Subdirectory

| Path | Contents |
|------|----------|
| `navier-stokes/` | Duplicate copies of all four JSON files above |

---

## Key Numbers Across Files

| Quantity | Value | Source File |
|----------|-------|-------------|
| Best KS (symmetrised) | 0.146 | reynolds_sweep.json |
| Best KS (Ginibre) | 0.092 | complex_eigenvalues.json |
| β range (symmetrised) | 1.71-2.05 | reynolds_sweep.json |
| β range (Ginibre) | 2.34-4.00 | complex_eigenvalues.json |
| Laminar KS | 0.98 | falsification.json |
| Laminar β | 0.00 | falsification.json |
| Spectral floor ratio | 0.6% | complex_eigenvalues.json |
| Scaling law ratio | 0.040 | complex_eigenvalues.json |
