# AI-Assisted Natural Product Virtual Screening Against FabI from *Acinetobacter baumannii*

## Project Overview

This project presents an end-to-end computational drug discovery workflow for the identification and prioritization of natural-product compounds targeting FabI (enoyl-acyl carrier protein reductase) from *Acinetobacter baumannii*.

FabI was selected as the target because it is an essential enzyme involved in bacterial fatty-acid biosynthesis and represents a potential antibacterial drug target. *A. baumannii* is also an important antimicrobial-resistance (AMR) pathogen.

The workflow integrates cheminformatics, molecular docking, dimensionality reduction, chemical-space analysis, clustering, ligand-efficiency analysis, and protein-ligand interaction analysis to progressively prioritize potential FabI inhibitors.

The final computationally prioritized compounds are currently being prepared for molecular dynamics simulation.

---

# Workflow

```text
Natural Product Databases
        │
        ├── NPASS
        ├── COCONUT
        ├── LOTUS
        └── FooDB
        │
        ▼
3,404 Compound Records
        │
        ▼
RDKit Chemical Filtering
        │
        ├── Structure validation
        ├── Lipinski filtering
        ├── PAINS filtering
        └── Rotatable bond filtering
        │
        ▼
2,703 Compounds
        │
        ▼
AutoDock Vina Molecular Docking
        │
        ▼
Docking Score ≤ -8 kcal/mol
        │
        ▼
471 Compounds
        │
        ▼
Molecular Fingerprints
        │
        ▼
PCA + Chemical-Space Analysis
        │
        ▼
Elbow Method + Silhouette Analysis
        │
        ▼
6 Clusters
        │
        ▼
Cluster-Based Candidate Selection
        │
        ▼
24 Compounds
        │
        ▼
Ligand Efficiency Analysis
        │
        ▼
21 Compounds
        │
        ▼
Protein-Ligand Interaction Analysis
        │
        ▼
9 Final Computational Candidates
        │
        ▼
Molecular Dynamics Simulation
        │
        ▼
Next Stage
