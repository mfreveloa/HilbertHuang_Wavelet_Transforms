# Hilbert–Huang & Wavelet Analysis for Geotechnical and Atmospheric Data

This repository contains reproducible workflows to analyze soil–atmosphere coupling using **Hilbert–Huang Transform (HHT)** and **Continuous Wavelet Transform (CWT)**. It also includes **wavelet coherence** and **IMF-level correlation** to study multiscale spatiotemporal patterns across three localities: **La Roque-Gageac (France)**, **Le Fauga (France)**, and **Valle de Aburrá (Colombia, SIATA network)**.

---

## What’s inside
- **HHT (Python):** EEMD/EMD decomposition, IMF power/energy, Hilbert spectrum, instantaneous frequency & period statistics.
- **Wavelets (R):** CWT scalograms, significance, **wavelet coherence** between variables.
- **Spatiotemporal analysis:** Compare scale-dependent behavior across the three sites; correlate IMFs and highlight dominant time scales (hours → seasons → years).

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

## Quick start

```bash
# create/activate your environment as you prefer, then:
pip install -r requirements.txt
# launch notebooks
jupyter lab

### R notebook
install.packages(c("IRkernel", "WaveletComp", "biwavelet"))
IRkernel::installspec(user = TRUE)  # enable the R kernel in Jupyter


