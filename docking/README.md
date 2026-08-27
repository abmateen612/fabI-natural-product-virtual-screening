# Molecular Docking

This directory contains the molecular docking results generated during virtual screening of the filtered natural-product library against FabI from *Acinetobacter baumannii*.

## Docking Software

Molecular docking was performed using **AutoDock Vina**.

The prepared FabI receptor was docked against the compounds that passed the RDKit-based chemical filtering stage.

## Docking Prioritization

A docking-score threshold of:

**≤ −8 kcal/mol**

was used as an initial prioritization criterion.

This resulted in:

**2,703 compounds → 471 prioritized compounds**

These 471 compounds were subsequently subjected to PCA, clustering, ligand-efficiency analysis, and further structural evaluation.

## Files

| File | Description |
|---|---|
| `docking_scores.csv` | Docking scores for the screened compounds used for docking-based prioritization |

## Important Note

Docking scores represent computational predictions and should not be interpreted as experimentally measured binding affinities.
