# 🛰️ Refined Bayesian Optimization (R-BO) Beam Alignment Dataset  
**Wireless Systems Laboratory, California State University, Sacramento**

This repository provides the dataset used in the paper:

**“Refined Bayesian Optimization for Efficient Beam Alignment in Intelligent Indoor Wireless Environments”**  
*Parth Shiroya, Amod Ashtekar, Swarnagowri Shashidhar, and Mohammed E. Eltayeb*  
Department of Electrical and Electronics Engineering, California State University, Sacramento  

---

## 📘 Overview
This dataset supports the empirical evaluation of the **Refined Bayesian Optimization (R-BO)** framework for efficient millimeter-wave (mmWave) beam alignment.

> **Correction:**  
> The dataset contains measured **received *relative* power values (in dB)**, not absolute power in dBm.  

Each RX sheet represents the relative power map obtained from exhaustive beam search at a specific receiver location.

---

## 🧭 Experimental Setup
- **Frequency:** 60 GHz (mmWave band)  
- **Hardware:** Sivers Semiconductors EVK06002 phased-array transceivers  
- **Environment:** Indoor laboratory (~12 m × 8 m) at CSU Sacramento  
- **Beam grid:**  
  - TX: 19 beams over [−45°, +45°] in 5° steps  
  - RX: 36 beams over [−180°, 180°) in 10° steps  
  - Total beam pairs: 19 × 36 = 684 per RX position  
- **Averaging:** Each beam pair measured three times and averaged to suppress noise  

---

## 🧾 Measurement Metadata

| Parameter | Description |
|------------|-------------|
| **Total number of grids** | 56 |
| **Transmitter location** | Grid Point 53 |
| **Line-of-Sight (LoS) grids** | RX01–RX04_Blocked, RX06–RX35, RX37–RX41, RX45–RX47 |
| **Non-Line-of-Sight (NLoS) grids** | RX05, RX36, RX42, RX43, RX44, RX48, RX49, RX50, RX51, RX52, RX54, RX55, RX56 |
| **Total grid points** | 56 (43 LoS + 13 NLoS) |

---

## 🗂️ Dataset Structure
- 📂 Dataset Structure

    ```
    Dataset.xlsx
    ├── Sheet Info      → Metadata and configuration details
    ├── RX01            → Relative power map (dB)
    ├── RX02
    ├── ...
    └── RX56
    ```


- **Sheet Info:**  
  Contains metadata fields such as total grids, transmitter grid point, LoS/NLoS classifications.  

- **RX## Sheets:**  
  Each sheet (36 × 19) stores the relative received-power values (in dB) over all AoA–AoD combinations.

| Dimension | Range | Step | Description |
|------------|--------|------|-------------|
| **AoD** | −45° → +45° | 5° | Transmit beam index |
| **AoA** | −180° → 180° | 10° | Receive beam index |
| **Values** | — | — | Relative received power (dB) |

---

## 📍 RX Locations Used in the Paper
The paper’s experimental evaluation used **only Line-of-Sight (LoS) RX grids**, listed below:  

**RX01–RX04_Blocked, RX06–RX35, RX37–RX41, RX45–RX47**

*(Total = 43 LoS receiver locations)*  

---

## 📄 Citation and Usage Policy
Any use of this dataset, in whole or in part, **must cite the associated paper**:

> **Parth Shiroya, Amod Ashtekar, Swarnagowri Shashidhar, and Mohammed E. Eltayeb**,  
> *“Refined Bayesian Optimization for Efficient Beam Alignment in Intelligent Indoor Wireless Environments,”*  
> arXiv preprint, 2025. [arXiv: \<placeholder\>]  

*(This section will be updated once the paper is published on arXiv.)*

---

© 2025 Wireless Systems Laboratory, California State University Sacramento.  
All rights reserved.
