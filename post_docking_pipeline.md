# Post-Docking Analysis Pipeline

## Overview

Following molecular docking, compounds achieving a docking score of **≤ −8 kcal/mol** were subjected to a series of computational post-docking analyses.

A total of **471 compounds** were carried forward from the docking stage.

The complete post-docking workflow included:

1. Molecular fingerprint generation
2. Principal Component Analysis (PCA)
3. PCA visualization
4. Cluster-number evaluation
5. Chemical clustering
6. Cluster-based candidate selection
7. Protein-ligand complex generation
8. Ligand Efficiency (LE) analysis

All of these analyses were implemented in a single Jupyter Notebook included in this repository.

## 1. Molecular Fingerprint Generation

Molecular fingerprints were generated for the 471 docked compounds to represent their structural features computationally.

These molecular representations were used for subsequent chemical-space analysis and clustering.

## 2. Principal Component Analysis

PCA was performed to reduce the dimensionality of the molecular feature space and visualize the structural distribution of the docked compounds.

The PCA visualization was used to examine the chemical-space distribution of the 471 compounds.

## 3. Cluster Number Selection

To determine an appropriate number of clusters, both the **Elbow Method** and **Silhouette Analysis** were evaluated.

The combined assessment supported the selection of:

**6 clusters**

for the subsequent chemical-diversity analysis.

## 4. Chemical Clustering

The 471 compounds were grouped into six clusters based on their molecular similarity/features.

Rather than selecting compounds solely according to docking score, candidates were selected across the clusters to maintain chemical diversity within the prioritized compound set.

This resulted in:

**471 compounds → 24 selected compounds**

## 5. Protein-Ligand Complex Generation

Protein-ligand complexes were generated for the selected 24 compounds.

These complexes were subsequently used for further structural evaluation and ligand-efficiency analysis.

## 6. Ligand Efficiency Analysis

Ligand Efficiency (LE) was calculated for the 24 selected compounds.

Ligand efficiency provides a way to evaluate predicted binding performance relative to molecular size and therefore provides an additional prioritization criterion beyond docking score alone.

Following ligand-efficiency analysis:

**24 compounds → 21 compounds**

The 21 compounds were retained for subsequent protein-ligand interaction analysis.

## Summary

| Stage | Compounds |
|---|---:|
| Docking-score filtered | 471 |
| Cluster-selected candidates | 24 |
| After ligand-efficiency analysis | 21 |

## Implementation

The complete post-docking workflow is provided as a Jupyter Notebook:

`pca_clustering_le_analysis.ipynb`

The notebook contains the computational analysis, visualizations, clustering evaluation, complex generation, and ligand-efficiency calculations used in this stage.
