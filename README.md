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

