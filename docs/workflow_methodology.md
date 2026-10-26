# Workflow and Methodology

Current workflow of the FabI virtual screening project. Only the NPASS natural
product library is used. This replaces the earlier multi-library version.

**Status:** research code for an article in preparation. No final results are
reported here.

## Pipeline

| Step | Method | Compounds left |
|---|---|---|
| 0 | NPASS library ([release / date]) | ~96,000 |
| 1 | RDKit filtering: Lipinski (0 violations), PAINS, QED, ADMET, rotatable bonds < 10, eNTRy rules | 369 |
| 2 | AutoDock Vina docking, score <= -8 kcal/mol | 128 |
| 3 | Morgan fingerprint PCA + KMeans (k = 4), top 4 per cluster | 16 |
| 4 | Ligand efficiency ranking | 9 |
| 5 | 2D interaction analysis | 4 |
| 6 | 100 ns molecular dynamics (GROMACS) | 4 |

## Receptor

PDB 6AHE (A. baumannii FabI, 2.29 A), prepared in UCSF Chimera. The NAD cofactor
is kept in the receptor. The protocol was validated by redocking the native
ligand AFN-1252: -10.2 kcal/mol, RMSD 0.365 A.

## Filtering

Compounds were filtered in RDKit with Lipinski's rule of five (0 violations),
PAINS, QED, ADMET-related filters, rotatable bonds < 10, and the eNTRy rules
for Gram-negative accumulation. 369 compounds remained.

## Docking

AutoDock Vina on an HPC cluster (SLURM). Ligands were prepared with RDKit
(ETKDGv3, MMFF) and converted to PDBQT with Open Babel (Gasteiger charges).

| Setting | Value |
|---|---|
| Grid centre | -37.508, -7.028, -3.125 |
| Grid size | 26 x 26 x 30 A |
| Exhaustiveness | 32 |
| Score cut-off | <= -8 kcal/mol |

## Selection

- **Diversity:** Morgan fingerprints (radius 2, 1024 bits), PCA, KMeans with
  k = 4 (elbow and silhouette). Top 4 compounds per cluster by docking score.
- **Efficiency:** ranked by ligand efficiency, top 9 kept.
- **Interactions:** 2D diagrams in Discovery Studio Visualizer; 4 compounds
  chosen for MD.

## Molecular dynamics

GROMACS, CHARMM36 force field, CGenFF parameters for ligands and the cofactor
(NADH). 100 ns production, 300 K, 1 bar, PME. Analysis: RMSD, RMSF, radius of
gyration, hydrogen bonds and contacts.

## Limitations

Docking scores rank compounds but are not measured affinities. ADMET filters use
predictions. All compounds are computational hits, not tested in the laboratory.

## References

- Rao et al. (2020). Chem Biol Drug Des 96, 704-713.
- Zeng, X. et al. (2018). Nucleic Acids Res 46, D1217-D1222.
- Eberhardt, J. et al. (2021). J Chem Inf Model 61, 3891-3898.
- Abraham, M. J. et al. (2015). SoftwareX 1-2, 19-25.
- Huang, J. et al. (2017). Nat Methods 14, 71-73.
