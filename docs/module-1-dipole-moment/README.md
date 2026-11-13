# Module 1 — DipoleMoment

**Polarization of Functional Topological Atoms (FTA)**

> Part of the [DipolarCalc](../../README.md) suite.

---

## Overview

**DipoleMoment** calculates the polarization characteristics of an individual **Functional Topological Atom (FTA)** — a localized bound state of topologically conjugated atomic groups around a central atom. The module computes:

- the dipole moment of an individual chemical bond,
- the total dipole moment of a triatomic conjugated group,
- the total bond dipole moment of an FTA,
- the **polarized state** of an FTA.

All computations are analytical and are performed in real time through a graphical interface, without requiring quantum-chemical tools.

---

## Scientific Background

The analysis of intermolecular interactions of various organic molecules requires taking into account their **intramolecular polarization**, caused by electron delocalization in specific functional groups. Electron delocalization, in turn, affects the electron density distribution in molecules, which is reflected in the electronic effects: **inductive effect** (electronegativity), **field effect** (electrostatic interaction), **conjugation** (resonance), and **orbital repulsion** (spatial effect).

Intramolecular polarization can be considered as division of the molecular structure of a biomolecule under the influence of external and internal forces into several different local equilibrium states exhibiting opposite physicochemical properties.

The theoretical foundation of DipolarCalc is based on the concept of **Functional Topological Atoms (FTA)** — localized bound states of topologically conjugated atomic groups around a central atom, characterized by minimal or maximal electronegativity and a defined internal energy that determines the molecule's physicochemical properties and spatial stability.

Polarization within FTA structures is described by a set of conjugated parameters:

- atomic electronegativity,
- dipole moment of chemical bonds,
- polarized state,
- polarizability.

DipolarCalc implements analytical expressions for these quantities, allowing for **real-time high-precision evaluation** of molecular polarization.

---

## Algorithms for calculating parameters

### 1. Calculation of the dipole moment of an individual chemical bond

$$
\mu = |\Delta\chi_{ab}| \cdot d,
$$

where $\mu$ is the dipole moment of the bond (measured in debyes, D), $\Delta\chi_{ab}$ is the difference in electronegativity of two atoms forming the chemical bond (measured in statcoulombs, ESU), and $d$ is the length of the chemical bond (measured in angstroms, Å).

### 2. Calculation of the total dipole moment of a group of three conjugated atoms

The calculation accounts for the angle between bonds:

$$
\mu_{\text{tot}} = \sqrt{\mu_1^2 + \mu_2^2 - 2\mu_1\mu_2 \cos \alpha},
$$

where $\mu_1, \mu_2$ are the dipole moments of the two bonds and $\alpha$ is the angle between the chemical bonds.

### 3. The total bond dipole moment of an FTA

It is defined as the geometric mean of the bond dipole moments of all groups of three conjugated atoms in the FTA structure:

$$
\mu_{\mathrm{FTA}} = \left(\prod_{i = 1}^{n} \mu_{i}\right)^{\frac{1}{n}},
$$

where $n$ is the number of groups in the FTA and $\mu_i$ is the dipole moment of each group.

### 4. Polarized state

The polarized state $P$ is equal to the total dipole moment $\mu$ of a unit of the substance volume $V$ (the volume of a sphere with a radius equal to the chemical bond length of the central atom in the FTA), which arises during its polarization. The quantitative characteristic of dielectric polarization (measured in C/m²) is:

$$
P = \frac{\mu}{V}.
$$

**Units for converting the dimensions of parameters:**

$$
1 \text{ \AA} = 10^{-10} \text{ m}; \quad 1 \text{ D} = 3.33564095 \times 10^{-30} \text{ C}\cdot\text{m}.
$$

---

## System Architecture

| Module | Description |
|--------|-------------|
| **User Interface** | Provides intuitive input forms and result visualization. |
| **Mathematical Core** | Implements analytical formulas for dipole and polarization calculations. |
| **Error Handling** | Checks data correctness and prevents invalid calculations. |
| **Localization** | Supports English and Russian language interfaces. |

The program is implemented in **C#** and performs calculations in real time.

---

## Graphical User Interface

The interface includes:

- a table of FTAs with their parameters ($P$, valence $V$, radius $r$, charge $q$);
- input fields with automatic validation (red color for invalid values);
- controls to add and delete FTAs.

---

## Advantages

- Analytical accuracy and reproducibility of results.
- Full automation of data processing.
- User-friendly interface suitable for research and education.
- Multilingual support (EN / RU).

---

## License

© 2026 I.K. Il'in, Yu.A. Uss. All rights reserved.

The source code is provided exclusively for academic and research purposes. Reproduction, modification, distribution, or commercial use of the software — in whole or in part — is prohibited without explicit written permission from the authors.