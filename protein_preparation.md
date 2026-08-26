# FabI Target Selection and Protein Preparation

## Target Selection

FabI (enoyl-acyl carrier protein reductase) from *Acinetobacter baumannii* was selected as the protein target for this virtual screening study.

The three-dimensional protein structure was obtained from the Protein Data Bank (PDB) using **PDB ID: 6AHE**.

## Native Ligand Removal

The 6AHE structure contains a native ligand, **0WE**, within the binding site.

The native ligand was removed using **UCSF Chimera** before preparing the protein for molecular docking. This was done to allow the natural-product compounds to be docked into the target binding site.

## Protein Preparation

Following native-ligand removal, the receptor was prepared using **AutoDock Vina Tools (MGLTools)**.

The preparation included:

* Removal of water molecules
* Removal of unnecessary protein chains
* Addition of polar hydrogens
* Assignment of Gasteiger charges
* Assignment/preparation of Kollman charges
* Preparation of the receptor in docking-compatible format

The resulting prepared receptor was used for subsequent AutoDock Vina molecular docking.

## Docking Grid Box

The docking search space was defined around the binding site using the following grid-box parameters:

| Parameter |   Value |
| --------- | ------: |
| Center X  | -37.508 |
| Center Y  |  -7.028 |
| Center Z  |  -3.125 |
| Size X    |    26 Å |
| Size Y    |    26 Å |
| Size Z    |    30 Å |

These coordinates and dimensions were used to define the region explored by AutoDock Vina during molecular docking.

## Files

* `6AHE.pdb` — original protein structure obtained from the Protein Data Bank
* `receptor.pdb` — prepared receptor structure
* `receptor.pdbqt` — docking-ready receptor, if available

The prepared receptor was subsequently used for virtual screening of the natural-product compound library.
