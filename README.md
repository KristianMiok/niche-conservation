# Niche Conservation in Historically Translocated and Cryptogenic Freshwater Crayfish

Machine-learning analysis of **ecological niche consistency** between native and non-native populations of freshwater crayfish using network-aware environmental predictors from the **Global Crayfish Database of Geospatial Traits (GeoTraits)**.

This repository accompanies the manuscript:

> **Ecological niche consistency as evidence for the conservation relevance of historically translocated and cryptogenic crayfish populations**

## Overview

This project evaluates whether historically translocated and cryptogenic crayfish populations occupy ecological space similar to their native counterparts. Using hydrologically resolved environmental predictors and interpretable machine-learning models, we compare native and non-native populations across three European crayfish taxa.

The central question is whether environmentally similar non-native populations may represent **ecologically consistent** range extensions rather than functionally disruptive invasions.

## Study species

The analysis focuses on three taxa classified in the GeoTraits dataset as having both **Native** and **Introduced** occurrences:

- *Pontastacus leptodactylus*
- *Austropotamobius fulcisianus*
- *Austropotamobius pallipes*

These taxa represent different biogeographic and historical contexts:

- **Cryptogenic / natural expansion**: *P. leptodactylus*
- **Historical translocation**: *A. fulcisianus*
- **Multiple historical translocations**: *A. pallipes*

## Core analyses implemented

This repository contains the workflow for:

1. **Data filtering and species selection**
2. **Decision-tree classification** of native vs. introduced occurrences
3. **Separate niche models** for native-only and introduced-only ranges
4. **Random forest + SHAP robustness analysis**
5. **Classical niche overlap metrics** (Schoener’s D, Warren’s I)
6. **Cross-validation importance stability**
7. **Pseudo-absence sensitivity analysis**
8. **Cross-paper comparison** with invasive species from the companion study

## Project structure

```text
niche-conservation/
├── config/
│   └── species_config.yaml
├── data/
│   ├── raw/                     # GeoTraits exports + S2 glossary (not tracked in git)
│   ├── interim/                 # Intermediate outputs
│   └── processed/               # Species-level prepared datasets
├── results/
│   ├── figures/                 # Main and supplementary figures
│   ├── tables/                  # Main and supplementary result tables
│   ├── pseudoabsence_sensitivity/
│   └── sample_size_sensitivity/
├── src/
│   ├── __init__.py
│   ├── data_loader.py
│   ├── species_selector.py
│   ├── data_preparation.py
│   ├── eda.py
│   ├── decision_tree.py
│   ├── cross_species_comparison.py
│   ├── separate_niche_models.py
│   ├── variable_glossary.py
│   ├── random_forest_shap.py
│   ├── niche_overlap_metrics.py
│   ├── cv_importance_stability.py
│   ├── pseudoabsence_sensitivity.py
│   └── cross_paper_comparison.py
├── requirements.txt
├── .gitignore
└── README.md
