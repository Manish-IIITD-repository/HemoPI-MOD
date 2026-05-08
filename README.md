# HemoPImod: Predicting Hemolytic Potency of Chemically Modified Peptides

Welcome to the official documentation for **HemoPImod**, a systematic computational tool developed to predict the hemolytic potency of chemically and structurally modified peptides. While several tools exist for natural peptides, HemoPImod is the first of its kind specifically designed to handle modified sequences by utilizing structural features and chemical descriptors.

**Web Server:** [http://webs.iiitd.edu.in/raghava/hemopimod/](http://webs.iiitd.edu.in/raghava/hemopimod/)

---

## Citation

Kumar, V., Kumar, R., Agrawal, P., Patiyal, S., & Raghava, G. P. S. (2020). 
**A Method for Predicting Hemolytic Potency of Chemically Modified Peptides From Its Structure.** *Frontiers in Pharmacology*, 11:54. 
[https://doi.org/10.3389/fphar.2020.00054](https://doi.org/10.3389/fphar.2020.00054) 
(https://doi.org/10.5281/zenodo.20079972)

---

## About the Platform

Peptide-based therapeutics are often modified to improve solubility, increase half-life, and decrease hemolysis.HemoPImod facilitates this drug-era advancement by providing a machine-learning framework to evaluate the toxicity of these modified molecules based on their 3D structures.


### Mechanism of Action
* **Membrane Binding**: Peptides rich in positively charged amino acids bind to the negatively charged lipid bilayer of erythrocytes.
* **Disintegration**: This binding leads to membrane disintegration, allowing water and solutes to enter the cell.
* **Cell Lysis**: The resulting osmotic gradient causes cell swelling and bursting (hemolysis).

---

## Dataset & Model Performance

[cite_start]The models were trained and evaluated on a curated dataset of **583 modified hemolytic peptides** and an equal number of non-hemolytic peptides extracted from the Hemolytik database[cite: 562, 596].

| Feature Type | Best Classifier | Accuracy (Main) | AUC (Main) |
| :--- | :--- | :--- | :--- |
| **Fingerprints** | Random Forest | 78.33% | 0.86  |
| **Diatom Composition** | ExtraTree | 74.36% |0.87  |
| **2D Descriptors** | Random Forest | 75.88% | 0.83  |
| **Atom Composition** | Random Forest | 70.49% | 0.81  |
| **3D Descriptors** | ExtraTree | 65.74% | 0.70  |

---

## Technical Overview

[cite_start]HemoPImod utilizes a wide range of peptide features to bridge the gap between structure and biological activity.

* **Structure Generation**: tertiary structures are predicted using the **PEPstrMOD** script.
* **Descriptor Calculation**: Atomic (atom/diatom composition) and chemical (2D, 3D, and fingerprints) descriptors are computed via **Open Babel** and **PaDEL** software.
* **Feature Selection**: Unnecessary descriptors are removed using **WEKA** (CfsSubsetEval with BestFirst search) to reduce noise.
* **Machine Learning**: Implementation of Ridge, Random Forest (RF), K-Nearest Neighbor (KNN), and ExtraTree classifiers via the **Scikit-learn** library.

---

## Web Server Usage

The HemoPImod interface is designed for simplicity, requiring only the tertiary structure of the modified peptide as input.

1. **Input**: Provide the peptide structure in **PDB format**.
2. **Structure Tool**: If the PDB structure is unavailable, users can generate it using the integrated **PEPstrMOD** link.
3. **Threshold**: Select an appropriate threshold value for prediction.
4. **Output**: Results are provided in text and graphical forms, including a probability score for hemolytic potential.

---

## Contact & Authors

**Prof. Gajendra P.S. Raghava**
Department of Computational Biology, Indraprastha Institute of Information Technology (IIIT-Delhi), India. 
**Email**: raghava@iiitd.ac.in 

---

## License

This project is an open-access resource distributed under the terms of the **Creative Commons Attribution License (CC BY)**.
