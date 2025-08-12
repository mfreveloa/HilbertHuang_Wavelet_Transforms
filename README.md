# Hilbert–Huang & Wavelet Analysis for Geotechnical and Atmospheric Data

This repository contains reproducible workflows to analyze soil–atmosphere coupling using **Hilbert–Huang Transform (HHT)** and **Continuous Wavelet Transform (CWT)**. It also includes **wavelet coherence** and **IMF-level correlation** to study multiscale spatiotemporal patterns across three localities: **La Roque-Gageac (France)**, **Le Fauga (France)**, and **Valle de Aburrá (Colombia, SIATA network)**.

---

## What’s inside
- **HHT (Python):** EEMD/EMD decomposition, IMF power/energy, Hilbert spectrum, instantaneous frequency & period statistics.
- **Wavelets (R):** CWT scalograms, significance, **wavelet coherence** between variables (e.g., rainfall vs. soil moisture).
- **Spatiotemporal analysis:** Compare scale-dependent behavior across the three sites; correlate IMFs and highlight dominant time scales (hours → seasons → multi-year).

## Repository structure
- **Python notebooks (HHT)**
  - `HilbertHuang_Transform_LARG.ipynb`
  - `HilbertHuang_Transform_LeFauga.ipynb`
  - `HilbertHuang_Transform_SIATA.ipynb`
- **R notebooks / scripts (Wavelets)**
  - `Wavelet_Transform_LARG.ipynb`
  - `Wavelet_Transform_LeFauga.ipynb`
  - `Wavelet_Transform_SIATA.ipynb`
- **Data**
  - `Data/LARG.dat` (La Roque-Gageac, FR)
  - `Data/LeFauga.dat` (Le Fauga, FR)
  - `Data/SIATA_396.dat`, `..._532.dat`, `..._541.dat`, `..._608.dat`, `..._613.dat` (Valle de Aburrá, CO)
- **IMFs & outputs**
  - `Data/IMFs/...` (EEMD outputs per site/variable)

> The wavelet notebooks use the **R kernel** inside Jupyter.

## Data format (expected)
- **SIATA** files: 3 columns → `[timestamp_unix, precipitation, soil_moisture]`
- **LARG / Le Fauga**: multi-column (time + variables such as solar radiation, rainfall, air/soil temperature, soil moisture at depths)
- Typical timesteps: **30 min** (`dt = 1/48`) or **1 hour** (`dt = 1/24`)

## Quick start

### Python (HHT)
```bash
# create/activate your environment as you prefer, then:
pip install -r requirements.txt
# launch notebooks
jupyter lab

### R notebook
```bash
install.packages(c("IRkernel", "WaveletComp", "biwavelet"))
IRkernel::installspec(user = TRUE)  # enable the R kernel in Jupyter
