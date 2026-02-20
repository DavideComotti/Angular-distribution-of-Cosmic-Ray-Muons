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

## Angular Transformation and Statistical Analysis

Detector measurements were converted into zenith angles within: 0° ≤ θ ≤ 90°. 
This transformation allowed the creation of histograms using the library 'matplotlib' which show the number of detected muons for each inclination with respect to the perpendicular to the detector

## Temporal Analysis

Starting from the merged files, heatmaps were created to analyze the detector activity throughout the days considered for this study. To create the heatmaps, timestamps were converted to datetime format using pandas.This analysis ensured measurement consistency and detector reliability.

## Theoretical Modeling and Monte Carlo Simulation

To compare experimental results with theoretical predictions, Monte Carlo simulations were performed using EcoMug (Efficient COsmic MUon Generator), an open-source cosmic muon generator.

The EcoMug source code was obtained from its official GitHub repository and integrated into the Python analysis pipeline using cppyy for C++ interoperability. From the GitHub repository of EcoMug was used TestSuite too which was integrated too. TestSuite allowed to simulate the presence of a detector (where the user can decide both the size and the orientation of the detector as well as the source type between flat-sky and hemisphere) and a CR muon's cascade. The muons that hit the detector are saved in a .txt file. These files were then used to create histograms of the angular distribution of muons.

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
- uproot
- cppyy
- Jupyter Notebook
- C++

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
