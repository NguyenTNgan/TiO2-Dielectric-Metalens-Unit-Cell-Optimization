# Spectroscopic Ellipsometry Analysis of Thin Films (TiO₂ Dataset)

This repository contains a full workflow for processing and analyzing spectroscopic ellipsometry (SE) data of TiO₂ thin films with different thicknesses (~101 nm, ~177 nm, ~305 nm). The pipeline extracts optical constants, builds dielectric functions, and analyzes thickness-dependent optical behavior.

---

# Dataset Description

The dataset is obtained from Variable Angle Spectroscopic Ellipsometry (VASE) measurements.

Each sample includes:

- Ψ (Psi): amplitude ratio of p- and s-polarized reflected light  
- Δ (Delta): phase difference  
- Model-fitted optical constants (n, k)

### Film thicknesses:

| Sample | Thickness |
|--------|----------|
| Film 1 | ~101 nm |
| Film 2 | ~177 nm |
| Film 3 | ~305 nm |

---

# Theory Background

Ellipsometry measures the complex reflection ratio:

\[
\rho = \tan(\Psi)e^{i\Delta} = \frac{r_p}{r_s}
\]

From this, the complex refractive index is extracted:

\[
\tilde{n} = n + ik
\]

The dielectric function is:

\[
\tilde{\varepsilon} = \varepsilon_1 + i\varepsilon_2 = (n + ik)^2
\]

Where:

- $\varepsilon_1 = n^2 - k^2$ (dispersion)
- $\varepsilon_2 = 2nk$ (optical absorption)

---

# Workflow

## 1. Data Preprocessing

- Clean multi-sheet Excel SE dataset
- Remove empty columns
- Extract wavelength-dependent n and k

## 2. Optical Constants

Construct dataset:

- wavelength (nm)
- n (refractive index)
- k (extinction coefficient)

---

## 3. Dielectric Function Conversion

```python
eps1 = n**2 - k**2
eps2 = 2 * n * k

# Dataset Citation

This project uses publicly available spectroscopic ellipsometry data from the following source:

**Raw data from spectroscopic ellipsometer**

- Author: Chandan Howlader  
- Year: 2020  
- Version: 1  
- Repository: Mendeley Data  
- DOI: https://doi.org/10.17632/zkbpdfhbh6.1  
- License: CC BY 4.0  

### Citation (APA format)

Howlader, C. (2020). *Raw data from spectroscopic ellipsometer* (Version 1) [Data set]. Mendeley Data. https://doi.org/10.17632/zkbpdfhbh6.1

---

### Description

This dataset contains:

- Ψ (Psi) and Δ (Delta) spectra measured using spectroscopic ellipsometry  
- Optical constants derived using B-spline and Psemi-Tri oscillator models  
- Absorption and transmission spectra from UV–Vis spectroscopy  
- Modeled transmission spectra for different film thicknesses  

The data is used here for extracting optical constants (n, k), dielectric functions, and thickness-dependent optical analysis of thin films.

---

### License Note

This dataset is distributed under **Creative Commons Attribution 4.0 (CC BY 4.0)**, allowing reuse with proper attribution.
