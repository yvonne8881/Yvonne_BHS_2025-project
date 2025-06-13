# Stroke-related Brain Connectivity from fNIRS Data


## 🧠 Project Overview

This project investigates brain connectivity patterns in **stroke patients** and **healthy adults** using **functional near-infrared spectroscopy (fNIRS)**. We analyze evoked responses and functional connectivity patterns during a motor task involving repeated handgrips.

## 📚 Background

Stroke impairs motor function by altering brain connectivity. Understanding these changes can guide personalized rehabilitation.  
We build upon connectivity-based frameworks (Grefkes & Fink, 2014) using fNIRS recordings during a rest + handgrip task.

> Grefkes, C., & Fink, G. R. (2014). *Connectivity-based approaches in stroke and recovery of function*. The Lancet Neurology, 13(2), 206–216. https://doi.org/10.1016/S1474-4422(13)70264-3

## 🎯 Project Goals

- Preprocess and convert raw fNIRS data into BIDS format  
- Visualize hemodynamic responses and compute ERP features (mean, peak, AUC)  
- Analyze correlation-based functional connectivity (FC)  
- Compare stroke (SP) and healthy (SH) groups using statistical and network-level analyses  

> Network Deviation Score (NDS) was planned but **not yet implemented** in this project.

## 📦 Dataset

| Item              | Details                                |
|-------------------|----------------------------------------|
| Participants      | 17 total (10 stroke patients, 7 healthy adults) |
| Collection Period | Aug 2024 – May 2025                    |
| Trials            | 218                                    |
| Montage           | 8 sources + 8 detectors → 22 channels  |
| Task Design       | 2-min rest + 3 × handgrip blocks (per side) |

> Dataset is for internal use only (not publicly released).

## 🧪 Methods

### Preprocessing

- Convert raw `.snirf` to BIDS-compliant `.fif` format  
- Band-pass filtering (0.01–0.2 Hz, 4th-order Butterworth)  
- Apply Beer–Lambert Law to estimate Δ[HbO] and Δ[HbR]

### ERP Analysis

- Time-windows defined:  
  - Task: 0–10s  
  - Onset: 5–25s  
  - Rest: 0–30s  
- Extract features: Mean, Peak, AUC  
- Joint plot & topographic visualizations

### Functional Connectivity

- Pearson correlation of channel-wise time series  
- FC categorized into:
  - Left M1
  - Right M1
  - Interhemispheric (Left–Right M1)
  - Other connections
- Between-group comparisons (SP vs SH)
- Graph metrics and violin plots

## 👩‍💻 Tools I learned during this project

- Python (MNE-Python, NumPy, Pandas, Matplotlib)  
- BIDS conversion tools
- Functional Connectivity

## 🔮 Future Directions

- Add motion correction  
- Add more participants and behavioral data  
- Incorporate EEG or MRI multimodal data  
- Develop machine learning models for prognosis

