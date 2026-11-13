# Module 2 — PairwiseInteraction

**Energy of pair interaction of Functional Topological Atoms (FTA)**

> Part of the [DipolarCalc](../../README.md) suite.

---

## Overview

**PairwiseInteraction** calculates the **energy of intermolecular interaction** between pairs of FTAs. It combines the FTA polarization parameters (bond dipole moment, polarized state) computed by [Module 1](../module-1-dipole-moment/README.md) into the pair interaction energy, providing a quantitative measure of the strength of supramolecular complexes formed by non-covalent interactions — ionic and classical/non-classical hydrogen bonds.

---

## Scientific justification

The energy of intermolecular interactions is a quantitative measure for assessing the strength of supramolecular complexes formed as a result of non-covalent interactions between the FTAs of complex molecular ions with the formation of ionic and classical / non-classical hydrogen bonds. The main property of these interactions is their **reversibility**. In this case, molecules can form supramolecular structures with both anisotropic and isotropic properties at the same temperature, depending on the change in their structural and functional symmetry as a result of intermolecular interaction.

The basic foundation for calculating the structural strength of supramolecular complexes — through polarizability and potential energy changes in modeling intermolecular interactions, taking into account the group interaction of atoms — is the calculated parameters of FTA polarization: the dipole moment of the chemical bond and the polarized state.

---

## Algorithms for calculating parameters

### 1. Polarizability $\chi$ in pair interaction of FTA

For the pair **FTA₁ → FTA₂**:

$$
\chi_2 = \frac{4\pi P_2 q_2 (r_1+r_2)^2}{V_1 q_1 e - 4\pi P_2 q_2 (r_1+r_2)^2}.
$$

For the pair **FTA₂ → FTA₁** (analogously):

$$
\chi_1 = \frac{4\pi P_1 q_1 (r_1+r_2)^2}{V_2 q_2 e - 4\pi P_1 q_1 (r_1+r_2)^2}.
$$

Mean polarizability:

$$
\chi_{\text{avg}} = \frac{\chi_1 + \chi_2}{2}.
$$

### 2. Potential energy $U$ of the pair interaction of FTA without electron-shell repulsion

$$
U = \frac{K q_1 q_2 e^2}{2 (r_1+r_2)(1+\chi_{\text{avg}})}.
$$

### 3. Potential energy $U$ of the pair interaction of FTA taking into account electron-shell repulsion

$$
U = \frac{K q_1 q_2 e^2}{2 (r_1+r_2)(1+\chi_{\text{avg}})}
    \left(1 - q_1 q_2 \frac{|r_1-r_2|}{r_1+r_2}\right).
$$

---

## Parameters and their dimensions

| Symbol | Meaning | Units |
|--------|---------|-------|
| $P$ | Polarized state; its sign depends on the ionity (charge) of the FTA | C/m² |
| $r$ | FTA radius | m (recalculation: 1 Å = 10⁻¹⁰ m) |
| $q$ | FTA charge (relative ion charge) | $+1$ or $-1$ |
| $e$ | Elementary charge | $1.602176634 \times 10^{-19}$ C |
| $V$ | Valence of the central atom of the FTA (the $V_I$ parameter in the original notation) | dimensionless |
| $\chi$ | Polarizability | dimensionless |
| $K$ | Coulomb constant | $9 \times 10^{9}$ N·m²/C² |
| $U$ | Potential interaction energy of FTA | J (= N·m) |

> **Note on notation.** The subscript in $V_1, V_2$ refers to FTA₁ and FTA₂, respectively. In the source article this parameter is written $V_I$ ("valence of the central atom").

---

## Graphical User Interface

The interface contains two linked tables:

1. **FTA table** — the same FTA list as in [Module 1](../module-1-dipole-moment/README.md). Each FTA is characterized by name, $P$, $V$, $r$, and $q$.
2. **Pair interaction table** — one row per selected pair, showing $\chi_1$, $\chi_2$, $\chi_{\text{avg}}$, and $U$.

Additional features:

- automatic validation of inputs (red highlight for invalid values);
- duplicate checks for FTA names and for pairs (order-independent);
- cascading deletion: removing an FTA from the first table also removes all pairs that reference it;
- localization (English / Russian).

---

## Advantages

- Analytical accuracy and reproducibility of results.
- Full automation of pair interactions data processing.
- Direct reuse of the polarization parameters from Module 1.
- Multilingual support (EN / RU).

---

## License

© 2026 I.K. Il'in, Yu.A. Uss. All rights reserved.

The source code is provided exclusively for academic and research purposes. Reproduction, modification, distribution, or commercial use of the software — in whole or in part — is prohibited without explicit written permission from the authors.