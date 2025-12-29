[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18084428.svg)](https://doi.org/10.5281/zenodo.18084428)

# RAMBHA-LP: Open-Source Processing Toolkit for Chandrayaan-3 Langmuir Probe Data

## Overview
This repository provides an open-source, reproducible data-processing workflow for the **RAMBHA-LP (Radio Anatomy of Moon Bound Hypersensitive Ionosphere and Atmosphere – Langmuir Probe)** instrument onboard **Chandrayaan-3**.

The notebook implements physics-based Langmuir probe analysis to extract:
- Electron temperature (Te)
- Electron density (Ne)

from raw voltage–current (V–I) sweeps, following the methodology reported by ISRO and the RAMBHA-LP science team.

---

## Scientific Background
RAMBHA-LP performed the first in-situ measurements of near-surface lunar plasma in the south polar region of the Moon.  
Published results indicate:
- Mean electron temperature: **3000–8000 K**
- Mean electron density: **380–600 cm⁻³**

This repository independently reproduces these results using open-source Python tools and validated physical models.

---

## Methodology
The processing workflow includes:

1. **Preprocessing**
   - Removal of non-numeric samples
   - Averaging current at identical bias voltages
   - Voltage sweep validation

2. **Potential Estimation**
   - Floating potential (Vf)
   - Plasma potential (Vp) via dI/dV maximization

3. **Electron Temperature (Te)**
   - Linear regression of ln(Ie) in the electron retardation region
   - Quality control using **Normalized Root Mean Square Error (NRMSE)** filtering

4. **Electron Density (Ne)**
   - Computed from electron current at plasma potential using:
     
     \[
     I_{e0} = 0.25 \, n_e \, e \, A \, v_t
     \]
     where
     \[
     v_t = \sqrt{\frac{8 k T_e}{\pi m_e}}
     \]

5. **Temporal Averaging**
   - Two-hour averaged values for comparison with published results

---

## Validation
The extracted parameters show strong agreement with published RAMBHA-LP observations:
- Electron temperature lies within the reported **3000–8000 K** range
- Electron density matches the reported **380–600 cm⁻³** daytime lunar plasma values

This confirms the robustness of the open-source processing chain.

---

## Repository Contents
- `RAMBHA FINAL.ipynb` – Complete processing notebook
- `RambhaLP.pdf` – Reference RAMBHA-LP publication
- `.gitignore` – Excludes raw mission data

> **Note:** Raw mission data is not included due to data policy restrictions.

---

## Requirements
- Python ≥ 3.9
- NumPy
- Pandas
- SciPy
- Matplotlib
- Jupyter Notebook

---

## Citation
If you use this code, please cite:

> Purnima Kumari, *Open-source RAMBHA-LP data processing toolkit and validation*, GitHub repository, 2025.  
> https://github.com/purnimarspr/RAMBHA-LP

---

## Disclaimer
This is an independent, academic reimplementation intended for research and reproducibility.  
It is **not an official ISRO software release**.
