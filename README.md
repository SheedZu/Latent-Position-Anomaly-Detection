# Latent-Position-Anomaly-Detection
MSc MLDS thesis project – Latent position modelling for network anomaly detection using synthetic graph simulations and the Los Alamos National Laboratory (LANL) Cyber-Security Events dataset.

## Overview
This repository contains the code developed for my MSc thesis on **Bayesian role-based anomaly detection**.  
The approach is applied to:
- **Synthetic graphs** generated via Random Dot Product Graph (RDPG) simulation.
- The [Comprehensive, Multi-Source Cyber-Security Events](https://csr.lanl.gov/data/cyber1/) dataset from LANL.

## Repository Structure
- `Final_Sim.ipynb` – RDPG simulation pipeline, MMSBM fitting, clustering, and anomaly scoring on synthetic data.
- `Final_LANL.ipynb` – LANL dataset pipeline, from preprocessing to anomaly detection evaluation.
- `requirements.txt` – Python dependencies for exact reproducibility.

## Data Access
The LANL dataset (~1.65B events) is **not** included in this repository due to size and licensing restrictions.  
You can obtain it directly from: [https://csr.lanl.gov/data/cyber1/](https://csr.lanl.gov/data/cyber1/)  

The notebooks expect the relevant raw LANL files (e.g., `redteam.txt`, `auth.txt`, etc.) to be available locally.  
They can be placed anywhere accessible — update the file paths in the notebooks accordingly.

## Reproducibility
To reproduce the results:
```bash
# Clone the repository
git clone https://github.com/SheedZu/Latent-Position-Anomaly-Detection.git
cd Latent-Position-Anomaly-Detection

# Install dependencies
pip install -r requirements.txt
