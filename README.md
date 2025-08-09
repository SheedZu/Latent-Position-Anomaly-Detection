# Latent-Position-Anomaly-Detection
MSc MLDS thesis project – Latent position modelling for network anomaly detection using synthetic graph simulations and the LANL Cyber-Security Events dataset.

## Overview
This repository contains all code used in the MSc thesis project on Bayesian role-based anomaly detection, applied to:
- Synthetic data generated via Random Dot Product Graph (RDPG) simulation.
- The [Comprehensive, Multi-Source Cyber-Security Events](https://csr.lanl.gov/data/cyber1/) dataset from Los Alamos National Laboratory (LANL).

## Files
- `Final_Sim.ipynb` – RDPG simulation pipeline, MMSBM fitting, clustering, and anomaly scoring on synthetic data.
- `Final_LANL.ipynb` – Full LANL dataset pipeline, from preprocessing to anomaly detection evaluation.
- `requirements.txt` – Python package versions for exact reproducibility.

## Data Access
The LANL dataset (~1.65B events) is **not** included in this repository due to size and licensing constraints.  
You can download it directly from: [https://csr.lanl.gov/data/cyber1/](https://csr.lanl.gov/data/cyber1/)  
After downloading, place the raw files in the `/data` directory before running the notebooks.

## Reproducibility Statement
All analyses can be reproduced by:
1. **Cloning this repository**
   ```bash
   git clone https://github.com/SheedZu/Latent-Position-Anomaly-Detection.git
   cd Latent-Position-Anomaly-Detection
