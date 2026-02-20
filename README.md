# Angular-distribution-of-Cosmic-Ray-Muons

# Study of the Angular Distribution of Cosmic Ray Muons

## Overview

This repository contains the complete experimental and computational analysis developed for my Bachelor Thesis in Mechanical Engineering at the University of Brescia.

The objective of this study is to measure and characterize the angular distribution of cosmic ray muons detected at ground level and to compare experimental results with theoretical predictions obtained through Monte Carlo simulation.

The project integrates:

- Experimental particle detector data
- ROOT file processing
- Scientific Python data analysis
- Monte Carlo muon generation
- Detector acceptance simulation
- Statistical comparison between theory and experiment

## Experimental Data Source

The data were collected using a cosmic ray muon detector at the INFN's Legnaro facility. 
Detector events were stored in ROOT format, the standard data format used in high-energy physics. The various ROOT files, which were obtained from a public dataset provided by INFN Legnaro and hosted by CERN, were opened using 'uproot'. Then, only the data regarding the study were extrapolated, that is, the angular coefficient of the incident CR muon, regarding both detector (Super Layer and Drift Tube) and both the directions (horizontal and vertical). The elements of every file were merged into a single file which was cleaned from null values and ordered by timestamp.

## Angular Transformation

Detector measurements were converted into zenith angles within:

0° ≤ θ ≤ 90°

This transformation enabled direct comparison with theoretical muon flux models.

The expected theoretical dependence follows:

I(θ) ∝ cosⁿ(θ)

where n ≈ 2 for atmospheric muons at ground level.

---

## Statistical Analysis

- Histogram construction using `matplotlib`
- Angular binning
- Distribution normalization
- Parameter estimation via curve fitting

The experimental angular distribution was extracted and characterized statistically.

---

## Temporal Analysis

To evaluate detector stability:

- Timestamps converted to datetime format using pandas
- Event frequency analyzed over time
- Heatmaps generated to visualize detector activity

This analysis ensured measurement consistency and detector reliability.

---

## Theoretical Modeling and Monte Carlo Simulation

To validate experimental results, theoretical simulations were performed using:

:contentReference[oaicite:2]{index=2}  
(Efficient COsmic MUon Generator)

EcoMug is a C++-based cosmic muon generator designed for realistic atmospheric muon simulations.

---

### C++ to Python Integration

The original C++ implementation of EcoMug was integrated into the Python workflow using:

- `cppyy` for C++–Python interoperability
- Python-controlled simulation loops
- Detector geometry emulation

This enabled seamless integration between Monte Carlo simulation and experimental analysis.

---

### Monte Carlo Procedure

1. Generation of atmospheric muon samples
2. Simulation of muon cascades
3. Emulation of detector acceptance
4. Extraction of simulated zenith angle distributions
5. Histogram generation for theoretical comparison

---

## Experimental vs Theoretical Comparison

The simulated and measured angular distributions were compared through:

- Histogram normalization
- Shape analysis
- Statistical consistency evaluation

The agreement between simulation and experimental data confirms:

- Correct detector modeling
- Validity of angular transformation
- Consistency with expected atmospheric muon behavior

---

## Repository Structure

```
notebooks/
    Complete Jupyter-based analysis workflow

data/
    Processed dataset used for analysis

results/
    Generated figures and comparison plots

thesis.pdf
    Full Bachelor thesis document

requirements.txt
    Python dependencies required to reproduce the analysis
```

---

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- SciPy
- uproot
- seaborn
- cppyy
- Jupyter Notebook
- C++

---

## Reproducibility

Install dependencies:

```
pip install -r requirements.txt
```

Run notebooks sequentially:

01_root_to_csv_conversion.ipynb  
02_data_cleaning_and_merging.ipynb  
03_angular_transformation.ipynb  
04_angular_distribution_analysis.ipynb  
05_temporal_heatmap_analysis.ipynb  
06_ecomug_simulation.ipynb  
07_experimental_vs_simulation_comparison.ipynb  

---

## Academic Context

This project was developed as part of my undergraduate thesis research.

It demonstrates:

- Experimental data processing in particle physics
- Scientific programming and reproducible research
- Monte Carlo simulation integration
- C++ / Python interoperability
- Statistical analysis and visualization

---

## Author

Bachelor Thesis – Mechanical Engineering  
University of Brescia  

Author: Davide Comotti
