# Workflow Methodology

## Overview

This project implements an end-to-end computational virtual-screening workflow for the identification and prioritization of potential FabI inhibitors from natural-product libraries against *Acinetobacter baumannii*.

The workflow combines structure-based virtual screening with cheminformatics and post-docking chemical-space analysis. The objective was not simply to identify compounds with favorable docking scores, but to progressively prioritize candidates using multiple complementary criteria, including chemical filtering, docking score, structural diversity, ligand efficiency, and protein-ligand interaction analysis.

The overall screening strategy was:

**Natural-product library → Chemical filtering → Molecular docking → Docking-score prioritization → PCA → Clustering → Ligand-efficiency analysis → Protein-ligand interaction analysis → Final candidates → Molecular dynamics preparation**

The compound population was progressively reduced from **3,404 initial records to 9 final computational candidates**.

---

# 1. Target Selection

## FabI from *Acinetobacter baumannii*

FabI (enoyl-acyl carrier protein reductase) was selected as the molecular target.

FabI is an essential enzyme involved in bacterial fatty-acid biosynthesis. Because disruption of essential bacterial metabolic processes can affect bacterial survival, FabI represents a biologically relevant target for antibacterial drug discovery.

The target organism selected for this project was *Acinetobacter baumannii*, an important bacterial pathogen associated with antimicrobial resistance.

The three-dimensional protein structure was obtained from the Protein Data Bank.

**PDB ID: 6AHE**

The structure was subsequently prepared for molecular docking.

---

# 2. Protein Structure Preparation

The experimentally determined 6AHE structure was used as the starting receptor structure.

The native ligand present in the crystal structure, **0WE**, was removed using UCSF Chimera.

Further receptor preparation was performed using AutoDock Vina Tools/MGLTools.

The preparation included:

- Removal of water molecules
- Removal of unnecessary protein chains
- Addition of polar hydrogens
- Assignment of Gasteiger charges
- Preparation of the receptor with Kollman charges
- Conversion/preparation of the receptor for AutoDock Vina docking

The resulting prepared receptor was saved as a PDBQT file and used for molecular docking.

## Docking Grid

The docking search space was defined using the following parameters:

| Parameter | Value |
|---|---:|
| Center X | -37.508 |
| Center Y | -7.028 |
| Center Z | -3.125 |
| Size X | 26 Å |
| Size Y | 26 Å |
| Size Z | 30 Å |

The grid was defined around the binding region of the target structure to provide a consistent search space for all docked compounds.

---

# 3. Natural-Product Compound Library

The screening library was constructed from established natural-product and food-compound databases.

The compounds were obtained from:

- **NPASS**
- **COCONUT**
- **LOTUS**
- **FooDB**

Therefore, the starting library was not composed of randomly selected compounds. It represented a collection of compounds originating from natural-product and food-related chemical resources.

The initial dataset contained:

**3,404 molecular records**

This library was used as the starting point for cheminformatics-based quality control and filtering.

---

# 4. RDKit-Based Chemical Filtering

Before molecular docking, the compound library was processed using the RDKit cheminformatics toolkit.

The purpose of this stage was to remove invalid structures and compounds with undesirable structural characteristics while reducing the computational screening space.

## 4.1 Structure Validation

The initial dataset contained:

**3,404 records**

During processing:

- **257 compounds** were classified as invalid or unreadable.
- **3,147 compounds** were successfully processed.

Only successfully processed structures were carried forward.

---

## 4.2 Lipinski Filtering

Lipinski Rule-of-Five-related molecular properties were evaluated to assess basic drug-likeness characteristics.

The filtering strategy allowed up to **one Lipinski violation** rather than requiring every compound to satisfy all rules.

After Lipinski filtering:

**3,147 → 3,144 compounds**

Only three compounds were removed at this stage.

---

## 4.3 PAINS Filtering

The remaining compounds were screened for Pan-Assay Interference Structures (PAINS).

PAINS filtering was included to reduce the presence of structural motifs that can produce misleading activity signals in biological assays.

After PAINS filtering:

**3,144 → 3,005 compounds**

---

## 4.4 Rotatable-Bond Filtering

Molecular flexibility was assessed using the number of rotatable bonds.

Compounds containing more than **10 rotatable bonds** were removed.

This step was used to reduce highly flexible molecules that may present less favorable characteristics for downstream screening and interpretation.

After rotatable-bond filtering:

**3,005 → 2,703 compounds**

---

## RDKit Filtering Summary

| Stage | Compounds Remaining |
|---|---:|
| Initial records | 3,404 |
| Invalid/unreadable | 257 |
| Successfully processed | 3,147 |
| After Lipinski filtering | 3,144 |
| After PAINS filtering | 3,005 |
| After rotatable-bond filtering | 2,703 |

The resulting **2,703 compounds** were carried forward to molecular docking.

---

# 5. Molecular Docking

The filtered compound library was subjected to molecular docking against the prepared FabI receptor.

Docking was performed using **AutoDock Vina**.

Each compound was evaluated within the predefined docking search space around the target binding region.

The docking stage provided predicted binding scores for the screened compounds.

Docking was used as an initial structure-based prioritization step rather than as definitive evidence of experimental binding affinity.

---

# 6. Docking-Based Prioritization

The docking results were ranked according to their predicted binding scores.

A threshold of:

**≤ −8 kcal/mol**

was applied to identify compounds with comparatively favorable predicted binding scores.

This reduced the docking population from:

**2,703 → 471 compounds**

The docking-score results are provided in the corresponding project data file.

The 471 compounds passing this threshold were subsequently analyzed using molecular fingerprints and chemical-space analysis.

---

# 7. Molecular Fingerprint and Chemical-Space Analysis

Docking score alone was not used as the final selection criterion.

The 471 prioritized compounds were further investigated based on their molecular structures.

Molecular fingerprints were generated to represent structural features of the compounds.

Principal Component Analysis (PCA) was then used to reduce the dimensionality of the molecular feature space and visualize the chemical-space distribution of the docked compounds.

This step provided a structural perspective on the diversity of the docking-selected compounds.

The purpose was to identify groups of structurally related compounds and avoid selecting candidates solely because they produced highly favorable docking scores.

---

# 8. Clustering and Cluster-Number Selection

The compounds were subjected to clustering based on their molecular-feature representation.

Two complementary approaches were used to evaluate the appropriate number of clusters:

## Elbow Method

The elbow method was used to examine how within-cluster variation changed as the number of clusters increased.

## Silhouette Analysis

Silhouette analysis was used to evaluate the quality of cluster separation and the relationship between compounds within and between clusters.

Based on the combined assessment of the clustering analyses, **6 clusters** were selected for subsequent candidate prioritization.

---

# 9. Cluster-Based Candidate Selection

Candidate selection was performed while considering the structural groups identified during clustering.

Rather than retaining only the compounds with the most favorable docking scores, compounds were selected across the identified chemical clusters.

This approach was intended to maintain chemical diversity among the shortlisted compounds.

The post-docking selection reduced:

**471 → 24 compounds**

These 24 compounds were carried forward to ligand-efficiency analysis.

---

# 10. Ligand-Efficiency Analysis

Ligand Efficiency (LE) analysis was performed on the 24 shortlisted compounds.

Ligand efficiency provides a way of relating predicted binding performance to molecular size, allowing compounds to be evaluated beyond their absolute docking score.

The analysis considered docking score together with the number of heavy atoms in each ligand.

The calculated ligand-efficiency values were used as an additional prioritization criterion.

Following this stage:

**24 → 21 compounds**

The resulting 21 compounds were retained for detailed protein-ligand interaction analysis.

---

# 11. Protein-Ligand Interaction Analysis

The 21 compounds were further evaluated by examining their predicted interactions with the FabI binding site.

Protein-ligand interaction analysis was performed using **BIOVIA Discovery Studio**.

The analysis was used to investigate the interaction patterns between the ligands and binding-site residues, including relevant:

- Hydrogen-bond interactions
- Hydrophobic interactions
- π-related interactions
- Other non-covalent interactions

This stage provided a structural interpretation of the docking poses and helped distinguish candidates based on their predicted interaction patterns with the target.

Following this analysis:

**21 → 9 final computational candidates**

These nine compounds were selected as the final candidates for the current virtual-screening workflow.

The corresponding Discovery Studio interaction diagrams are provided in the repository.

---

# 12. Final Candidate Selection Strategy

The final candidate selection was therefore based on multiple computational criteria rather than a single docking score.

The progressive prioritization strategy was:

| Stage | Remaining Compounds |
|---|---:|
| Initial natural-product records | 3,404 |
| Successfully processed structures | 3,147 |
| After chemical filtering | 2,703 |
| Docking score ≤ −8 kcal/mol | 471 |
| Cluster-based selection | 24 |
| Ligand-efficiency prioritization | 21 |
| Interaction-based prioritization | 9 |

This multi-stage approach was designed to combine:

1. **Chemical quality**
2. **Predicted binding performance**
3. **Chemical-space diversity**
4. **Ligand efficiency**
5. **Protein-ligand interaction patterns**

The final nine compounds therefore represent candidates that passed several independent computational prioritization stages.

---

# 13. Molecular Dynamics Preparation

The nine final protein-ligand complexes were prepared for the next stage of computational validation: molecular dynamics simulation.

Molecular dynamics will be used to investigate the stability and behavior of the selected protein-ligand complexes over time.

Planned analyses include:

- Protein-ligand RMSD
- Protein RMSF
- Radius of gyration
- Hydrogen-bond persistence
- Protein-ligand interaction stability
- Comparative trajectory analysis
- Binding free-energy estimation, where appropriate

The molecular dynamics stage is intended to provide a dynamic assessment of the shortlisted complexes beyond the static docking and interaction analyses.

---

# 14. Computational Tools

| Tool | Application |
|---|---|
| Protein Data Bank | Protein structure retrieval |
| UCSF Chimera | Native-ligand removal and structure inspection |
| AutoDock Vina Tools / MGLTools | Receptor and ligand preparation |
| AutoDock Vina | Molecular docking |
| RDKit | Molecular processing and chemical filtering |
| Python | Data processing and analysis |
| Jupyter Notebook | Computational workflow |
| PCA | Chemical-space analysis |
| Clustering | Structural diversity analysis |
| BIOVIA Discovery Studio | Protein-ligand interaction analysis |

---

# 15. Limitations

This workflow represents a computational virtual-screening study.

Docking scores, ligand-efficiency values, and predicted protein-ligand interactions are computational measurements and should not be interpreted as experimental confirmation of binding affinity or antibacterial activity.

Similarly, passing chemical filters does not establish biological activity.

The final candidates require additional computational and experimental validation.

Molecular dynamics simulations represent the next computational validation stage.

Ultimately, experimental testing would be required to determine whether the prioritized natural products demonstrate FabI inhibition and antibacterial activity against *A. baumannii*.

---

# 16. Reproducibility

The repository provides the major structures, computational notebooks, docking results, final candidate data, figures, and methodological documentation associated with the workflow.

The objective is to allow the major stages of the virtual-screening process to be understood and reproduced from the documented workflow.

The project intentionally focuses on the key files and results rather than storing thousands of intermediate docking structures and compound files.
