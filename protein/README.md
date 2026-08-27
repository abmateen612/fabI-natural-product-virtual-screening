# Protein Structure and Preparation

This directory contains the FabI protein structure used in the virtual screening workflow against *Acinetobacter baumannii*.

## Target

- **Target:** FabI (enoyl-acyl carrier protein reductase)
- **Organism:** *Acinetobacter baumannii*
- **PDB ID:** 6AHE

## Files

| File | Description |
|---|---|
| `6AHE.pdb` | Original protein structure obtained from the Protein Data Bank |
| `receptor.pdbqt` | Prepared receptor used for AutoDock Vina molecular docking |

## Protein Preparation

The native ligand (0WE) was removed using UCSF Chimera.

Further receptor preparation was performed using AutoDock Vina Tools/MGLTools, including removal of water molecules and unnecessary chains, addition of polar hydrogens, and charge assignment.

The prepared receptor was converted to PDBQT format for molecular docking.

## Docking Grid

The docking grid was defined using:

| Parameter | Value |
|---|---:|
| Center X | -37.508 |
| Center Y | -7.028 |
| Center Z | -3.125 |
| Size X | 26 Å |
| Size Y | 26 Å |
| Size Z | 30 Å |
