# DipolarCalc

**Software suite for assessing polarization and interaction energy of biomolecular structures**

DipolarCalc is a modular scientific software package for analytical calculation of the physicochemical parameters of biomolecular structures based on the concept of **Functional Topological Atoms (FTA)**. It is developed for **computational biology**, **biophysical chemistry**, and **molecular modeling**, and gives researchers real-time access to high-precision molecular polarization without requiring quantum-chemical tools.

## Modules

| # | Module | Scope | Documentation |
|---|--------|-------|---------------|
| 1 | **DipoleMoment** | Polarization of a single FTA: bond dipole moment, triatomic-group dipole moment, FTA total dipole moment, polarized state | [→ Module 1](docs/module-1-dipole-moment/README.md) |
| 2 | **PairwiseInteraction** | Pair interaction of FTAs: polarizability, average polarizability, potential energy of intermolecular interaction | [→ Module 2](docs/module-2-pairwise-interaction/README.md) |

Both modules share the same FTA data model and can be used together or independently.

## Background

The analysis of intermolecular interactions of organic molecules requires taking into account their **intramolecular polarization**, caused by electron delocalization in specific functional groups. Electron delocalization affects the electron density distribution in molecules, which is reflected in four classical electronic effects:

- **inductive** (electronegativity),
- **field** (electrostatic interaction),
- **conjugation** (resonance),
- **orbital repulsion** (spatial effect).

Intramolecular polarization can be regarded as the division of a biomolecule's structure — under the influence of external and internal forces — into several local equilibrium states that exhibit opposite physicochemical properties. DipolarCalc describes each such state as an **FTA**.

## System requirements

- **OS:** Windows 10 or newer
- **Framework:** .NET Framework 4.8
- **Architecture:** Intel/AMD x64
- **RAM:** 2 GB minimum

## License

© 2026 I.K. Il'in, Yu.A. Uss. All rights reserved.

The source code and binaries are provided exclusively for **academic and research purposes**. Reproduction, modification, distribution, or commercial use — in whole or in part — is **prohibited without explicit written permission** from the authors.