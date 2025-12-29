---
title: "RAMBHA-LP: An open-source processing and validation toolkit for near-surface lunar plasma data"
tags:
  - lunar plasma
  - Langmuir probe
  - Chandrayaan-3
  - space physics
  - scientific software
authors:
  - name: Purnima Kumari
    affiliation: 1
affiliations:
  - name: Independent Researcher, India
    index: 1
date: 2025-01-XX
bibliography: paper.bib
---

## Summary

RAMBHA-LP is an open-source Python-based processing toolkit for Langmuir probe data obtained by the Radio Anatomy of Moon Bound Hypersensitive Ionosphere and Atmosphere Langmuir Probe (RAMBHA-LP) onboard the Chandrayaan-3 mission. The software implements physically consistent methods to estimate electron temperature and electron density from current–voltage sweeps, incorporating numerical stabilization, quality control using normalized root-mean-square error (NRMSE) filtering, and reproducibility-oriented design.

The toolkit reproduces published trends of near-surface lunar plasma parameters and provides the first openly available, end-to-end processing pipeline for RAMBHA-LP data, enabling transparent validation and reuse by the space physics community.

## Statement of Need

Although RAMBHA-LP measurements have revealed important characteristics of the near-surface lunar plasma environment, no open-source data processing pipeline has been publicly available. This limits independent verification, reuse, and extension of published results. The RAMBHA-LP toolkit addresses this gap by providing a fully documented, open, and reproducible software implementation aligned with published analysis methods.

## Software Description

The toolkit processes raw voltage–current sweep data to estimate floating potential, plasma potential, electron temperature, and electron density. Electron temperature is derived from linear regression in the electron retardation region, with sweep quality assessed using normalized root-mean-square error (NRMSE). Electron density is computed from the electron current at plasma potential using standard orbital motion limited (OML) theory. The implementation includes automated data filtering, temporal averaging, and visualization.

## Validation

The derived electron temperature (3000–8000 K) and electron density (approximately 380–600 cm⁻³) ranges are consistent with values reported in published RAMBHA-LP studies. Temporal trends produced by the toolkit closely match reported diurnal variations, demonstrating the physical correctness and robustness of the implementation.

## Availability

The RAMBHA-LP toolkit is openly available on GitHub and archived on Zenodo with a DOI for long-term reproducibility.

