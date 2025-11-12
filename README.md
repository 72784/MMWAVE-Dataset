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
The dataset was collected through a controlled **60 GHz beam-sweep measurement campaign** conducted in the **Wireless Systems Laboratory, California State University, Sacramento**.

- **Hardware:**  
  - Sivers Semiconductors **EVK06002** phased-array transceivers operating at **60 GHz** in **analog beamforming mode**.  
  - The **transmitter (TX)** and **receiver (RX)** were mounted on tripods at a height of **1.6 m** to emulate **user-equipment (UE)–to–access-point (AP)** geometry.  
  - Received power was recorded using a **National Instruments USRP-2900** connected to the RX via a LabVIEW interface.  
  - All measurements represent **relative received power (in dB)**, not absolute power in dBm.

- **Environment:**  
  - Measurements were taken in a **12 m × 8 m indoor laboratory** containing metallic benches, wooden tables, and computers—creating rich **multipath reflections** typical of dense indoor wireless environments.  
  - The **TX** was fixed at **grid index 53**, while the **RX** was sequentially moved across a **7 × 8 spatial grid (56 points)**.  
  - A total of **43 LoS positions** were used in the paper for evaluation.

- **Beam Grid Configuration:**  
  | Parameter | Range | Step | Count |
  |------------|--------|------|-------|
  | **TX azimuth scan** | −45° → +45° | 5° | 19 beams |
  | **RX azimuth scan** | −180° → 180° | 10° | 36 beams |
  | **Total beam pairs per RX** | — | — | 19 × 36 = 684 |
  | **Averaging** | Each beam pair measured 3× and averaged | — | Noise reduction |

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
