# Latent-Position-Anomaly-Detection

This project explores **probabilistic anomaly detection in enterprise authentication graphs** using latent position models.  
We focus on the Los Alamos National Laboratory (LANL) authentication dataset, comparing methods such as spectral embedding, Gaussian Mixture Models (GMM), and entropy-based scoring.

---

## Overview
This repository contains the code developed for my MSc thesis on **Bayesian role-based anomaly detection**.  
The approach is applied to:
- **Synthetic graphs** generated via Random Dot Product Graph (RDPG) simulation.  
- The [Comprehensive, Multi-Source Cyber-Security Events](https://csr.lanl.gov/data/cyber1/) dataset from LANL.  

---

## Pipeline Overview

This repository implements a two-track pipeline:

1. **Real Data (LANL Authentication Logs)**
   - Input: `auth.txt[.gz]`, `redteam.txt[.gz]` from the LANL dataset.  
   - Preprocessing: `Final_LANL.ipynb` creates `./lanl_output/` containing:
     - `auth_early_redonly.csv.gz`
     - `auth_peak_redonly.csv.gz`
     - `auth_late_redonly.csv.gz`
   - Analysis: graph creation, SVD embedding, clustering, and anomaly detection are performed on these subsets.  

2. **Synthetic Data (RDPG Simulation)**
   - Input: simulated graphs with injected anomalies.  
   - Processing: `Final_Sim.ipynb` generates RDPG graphs with injected anomalies, performs SVD embedding, clustering, and anomaly detection.  
   - Output: comparative evaluation of detection methods under controlled conditions.  

---

## Repository Structure
- `Final_Sim.ipynb` – RDPG simulation pipeline with anomaly scoring.  
- `Final_LANL.ipynb` – LANL dataset pipeline: preprocessing → subset generation → anomaly scoring.  
- `requirements.txt` – Python dependencies for exact reproducibility.  
- `LICENSE` – License information.  

---

## Data Access

The LANL dataset (~1.65B events) is **not** included in this repository due to size and licensing restrictions.  
You can obtain it directly from the [LANL dataset site](https://csr.lanl.gov/data/cyber1/).

### Required Files
At minimum, you will need the following raw files from the LANL release:
- `auth.txt` (or `auth.txt.gz`)  
- `redteam.txt` (or `redteam.txt.gz`)  

### Preprocessing
The notebook `Final_LANL.ipynb` expects these raw files to be available locally.  
On first run, it will:

1. Create a subdirectory (`./lanl_output/`) inside the repo.  
2. Generate **three cleaned data subsets** from the raw authentication log:
   - `auth_early_redonly.csv.gz`
   - `auth_peak_redonly.csv.gz`
   - `auth_late_redonly.csv.gz`
3. Save these subsets into the subdirectory.  

All subsequent analysis notebooks load their data directly from these subsets, so you will only need to run the preprocessing step once.

> Note: You may place the raw files anywhere on your machine, but you will need to update the file paths inside the notebook accordingly.  

---

## Reproducibility
To reproduce the results:

```bash
# Clone the repository
git clone https://github.com/SheedZu/Latent-Position-Anomaly-Detection.git
cd Latent-Position-Anomaly-Detection

# Install dependencies
pip install -r requirements.txt

# Run preprocessing (first time only)
jupyter notebook Final_LANL.ipynb

# Run simulation experiments
jupyter notebook Final_Sim.ipynb
