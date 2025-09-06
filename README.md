# Solar-Proton-Event-Analyzis
## Overview
This project processes and analyzes historical solar energetic particle (SEP) measurements from NOAA's GOES11 and GOES13 satellites. It focuses on differential proton flux data from the P2-P7 channels, corresponding to energies of approximately 6.6 MeV to 155 MeV. The code performs calculations such as average and maximum flux spectra, integral spectra, peak detection, NOAA S-scale categorization, and correlation with solar disk measurements. The analysis is based on data files (SEP_H_GOES11.txt and 
SEP_H_GOES13.txt), which contain unidirectional proton flux measurements
 in units of particles/MeV/cm²/sec/str. This project helps in 
identifying SEP events, visualizing spectra, and assessing their 
intensity and correlation with solar activity.

## Purpose
To process SEP data for event selection, spectrum analysis, and 
correlation studies. This includes calculating key metrics for proton 
energies (e.g., 10 MeV, 30 MeV, and 80 MeV) and categorizing events 
using the NOAA S-scale (which classifies proton storms based on flux 
thresholds).

## Data Sources
Primary Data: 
SEP_H_GOES11.txt: Historical proton flux data from GOES11.
SEP_H_GOES13.txt: Historical proton flux data from GOES13.
These files include columns for time (epoch) and flux values for channels P2-P7 (mapped to energies: 6.6 MeV, 12.6 MeV, 20.6 MeV, 46.6 MeV, 104 MeV, and 155 MeV).
Additional Data: 
A sample solar disk dataset is included in the code for correlation analysis.

## Key Features:
Load and preprocess data from GOES11 and GOES13.
Compute average and maximum differential spectra.
Derive integral spectra and fluxes above specific energy thresholds.
Detect peak flux times for each energy channel.
Categorize events (e.g., S1 for minor storms).
Correlate GOES data with sample solar disk measurements to explore relationships with solar phenomena.


## Code Explanation:
The solution is implemented in a Jupyter notebook [Solar-Proton-Event-Analysis.ipynb]( ). Here's a high-level breakdown of the code:

1. Data Loading and Setup:
Imports necessary libraries: pandas, numpy, matplotlib, scipy, and datetime.
Loads the GOES11 and GOES13 data files into DataFrames.
Defines energy channels and processes the data for a specified date range.
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.interpolate import InterpolatedUnivariateSpline
from datetime import datetime

# Set plot styles
plt.rcParams['axes.labelsize'] = 16
plt.rcParams['axes.titlesize'] = 16

# Define the date range for processing 
start_date = '2010-05-01'  # use a range that exists in both datasets
end_date = '2011-02-27'
```

2. Average and Maximum Differential Spectra:
Calculates the mean and maximum flux for each energy channel.
Plots the spectra for both satellites using logarithmic scales for better visualization.
```

```

3. Average and Maximum Differential Spectra:
Calculates the mean and maximum flux for each energy channel.
Plots the spectra for both satellites using logarithmic scales for better visualization.

5. Integral Spectra Calculation:
Uses spline interpolation to compute integral spectra from the differential spectra.
Plots the average and maximum integral spectra.

7. Flux Above Specific Energies:
Computes integral fluxes for protons above 10 MeV, 30 MeV, and 80 MeV.
Prints the results for both satellites.

9. Peak Appearance Times:
Identifies the time and value of the peak flux for each channel.
Outputs the peak details for GOES11 and GOES13.

11. NOAA S-Scale Categorization:
Classifies events based on the maximum flux above 10 MeV using NOAA thresholds (e.g., >10000 for S5, >1000 for S4, etc.).
Prints the category for each satellite.

13. Correlation with Solar Disk Measurements:
Merges the GOES13 data with a sample solar disk dataset.
Computes Pearson and Spearman correlations to assess relationships between solar disk flux and GOES proton flux.
Plots the correlated data for visual inspection.
