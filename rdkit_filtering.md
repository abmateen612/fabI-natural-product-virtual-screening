# RDKit-Based Compound Filtering

## Natural Product Library

The initial compound library consisted of **3,404 molecular records** collected from established natural-product and food-compound resources:

* **NPASS**
* **COCONUT**
* **LOTUS**
* **FooDB**

The compounds were therefore **not randomly selected molecules**. They represent a curated computational library of naturally occurring and food-associated compounds assembled for the virtual screening workflow against FabI from *Acinetobacter baumannii*.

## Objective

Before molecular docking, the compound library was subjected to structure-based chemical filtering using **RDKit**.

The purpose of this stage was to remove compounds with undesirable drug-likeness or structural characteristics and reduce the library to a more suitable set for subsequent virtual screening.

## Initial Library

A total of **3,404 molecular records** were processed.

During structure processing:

* **257** records were invalid or unreadable.
* **3,147** compounds were successfully processed.

## Filtering Strategy

Three sequential filters were applied to the successfully processed compounds.

### 1. Lipinski Rule-of-Five

Lipinski-based filtering was applied to assess drug-likeness-related molecular properties.

The workflow allowed **up to one Lipinski violation**.

After this step:

**3,144 compounds remained.**

### 2. PAINS Filtering

The remaining compounds were screened for **Pan-Assay Interference Structures (PAINS)** using RDKit.

PAINS-associated structures were removed to reduce the likelihood of prioritizing compounds with structural features known to cause potential assay interference.

After PAINS filtering:

**3,005 compounds remained.**

### 3. Rotatable Bond Filtering

Molecular flexibility was subsequently assessed using the number of rotatable bonds.

Compounds containing **more than 10 rotatable bonds** were removed.

After this step:

**2,703 compounds remained.**

## Filtering Summary

| Stage                          | Compounds |
| ------------------------------ | --------: |
| Initial compound records       |     3,404 |
| Invalid/unreadable             |       257 |
| Successfully processed         |     3,147 |
| After Lipinski filtering       |     3,144 |
| After PAINS filtering          |     3,005 |
| After rotatable-bond filtering |     2,703 |

## Outcome

The RDKit workflow reduced the successfully processed natural-product library from **3,147 to 2,703 compounds**.

These **2,703 compounds** were subsequently taken forward for molecular docking using AutoDock Vina.

## Implementation

The filtering workflow was implemented in Python using the **RDKit cheminformatics toolkit**.

The corresponding Python implementation is included in this repository to provide transparency and reproducibility of the chemical-filtering stage.
