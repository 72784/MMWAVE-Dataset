# 🛰️ Refined Bayesian Optimization (R-BO) Beam Alignment Dataset
**California State University, Sacramento – Wireless Systems Laboratory**

This repository provides the dataset used in the paper:

> **Refined Bayesian Optimization for Efficient Beam Alignment in Intelligent Indoor Wireless Environments**  
> *Parth Shiroya, Amod Ashtekar, Swarnagowri Shashidhar, and Mohammed E. Eltayeb*  
> Department of Electrical and Electronics Engineering, California State University, Sacramento  

---

## 📘 Overview
This dataset supports the empirical evaluation of the **Refined Bayesian Optimization (R-BO)** framework for efficient millimeter-wave (mmWave) beam alignment.

It contains **measured received-power values (in dB)** over two-dimensional **Angle-of-Departure (AoD)** and **Angle-of-Arrival (AoA)** beam grids for multiple receiver (RX) positions in an indoor laboratory environment.

Each file corresponds to one RX location and represents the **relative power map** obtained from exhaustive beam search.

---

## 🧭 Experimental Setup
- **Frequency:** 60 GHz (mmWave band)  
- **Hardware:** Sivers Semiconductors EVK06002 phased-array transceivers  
- **Environment:** Indoor laboratory (~12 m × 8 m) at CSU Sacramento  
- **Beam grid:**  
  - TX: 19 beams over [−45°, +45°] in 5° steps  
  - RX: 36 beams over [−180°, 180°) in 10° steps  
- **Total beam pairs:** 19 × 36 = 684 per RX position  
- **Receiver positions:** 43 usable locations  
- **Averaging:** Each beam pair measured 3 times and averaged to suppress noise  

---

## 🗂️ Dataset Structure
dataset/
├── RX01.csv
├── RX02.csv
├── ...
├── RX43.csv
└── metadata.json


Each `RX##.csv` file contains a **36 × 19 matrix** of relative received-power values (in dB):

| Dimension | Range | Step | Description |
|------------|--------|------|-------------|
| AoD | −45° → +45° | 5° | Transmit beam index |
| AoA | −180° → 180° | 10° | Receive beam index |
| Values | — | — | Relative received power (dB) |

Example `metadata.json`:
```json
{
  "frequency_GHz": 60,
  "tx_beams": 19,
  "rx_beams": 36,
  "rx_positions": 43,
  "angular_resolution": {"AoA_deg": 10, "AoD_deg": 5},
  "measurement_repeats": 3,
  "unit": "dB"
}
