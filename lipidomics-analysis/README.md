# Lipidomics Data Analysis and Statistical Modeling

This project presents a computational analysis pipeline for lipidomics data,
focusing on group-wise statistical comparison, dimensionality reduction,
and interpretable machine learning.

The analysis was conducted as part of a biomedical engineering course project
and is based on real experimental lipidomics measurements.

## Objectives

- Identify lipid species and subclasses that differ significantly between two biological groups
- Explore global structure and separation using unsupervised methods
- Build interpretable models to highlight key discriminative lipid features

## Methods

The analysis pipeline includes:

- Data preprocessing and normalization (total-sum scaling, log transform, Pareto scaling)
- Dimensionality reduction (PCA, t-SNE)
- Statistical testing (Welch’s t-test, fold-change analysis)
- Visualization (confidence ellipses, heatmaps, volcano plots)
- Interpretable classification (decision tree models)

## Key Analyses

- PCA and t-SNE projections for structural and signaling lipids
- Hierarchical clustering of samples and significant lipid subsets
- Differential lipid analysis with volcano plots and ranked fold changes
- Decision tree models to identify lipid subclasses driving group separation

## Code Structure

- `src/`
  - Scripts for preprocessing, statistical testing, visualization, and modeling
- `figures/`
  - Exported figures illustrating major results (PCA, heatmaps, volcano plots)

## Notes

- Raw data files are not included due to size and data-sharing constraints
- Code is provided for demonstration of analysis logic and methodology

