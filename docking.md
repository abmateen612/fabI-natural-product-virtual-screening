# AutoDock Vina Molecular Docking

## Objective

Following RDKit-based chemical filtering, the remaining **2,703 natural-product compounds** were subjected to molecular docking against the prepared FabI receptor from *Acinetobacter baumannii*.

The objective was to prioritize compounds with favorable predicted binding interactions within the defined FabI binding site.

## Docking Software

Molecular docking was performed using **AutoDock Vina**.

The prepared receptor and ligand structures were converted into the docking-compatible format required by AutoDock Vina.

## Docking Grid

The docking search space was defined during protein preparation using the following parameters:

| Parameter |   Value |
| --------- | ------: |
| Center X  | -37.508 |
| Center Y  |  -7.028 |
| Center Z  |  -3.125 |
| Size X    |    26 Å |
| Size Y    |    26 Å |
| Size Z    |    30 Å |

## Docking Score Filtering

After docking, compounds were ranked according to their predicted binding affinity.

A cutoff of:

**≤ −8 kcal/mol**

was used to prioritize compounds showing favorable predicted binding scores.

This filtering resulted in:

**2,703 docked compounds → 471 prioritized compounds**

The docking scores are provided in the accompanying docking-results CSV file.

## Interpretation

The docking score was used as an initial prioritization criterion rather than as experimental evidence of binding affinity.

The 471 compounds passing the docking-score threshold were subsequently subjected to molecular fingerprint-based chemical-space analysis, PCA, and clustering to identify chemically diverse candidate compounds.
