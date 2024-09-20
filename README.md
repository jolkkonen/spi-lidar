# Simulation of ultra-fast structured illumination in single-photon sensitive single-pixel lidar
This repository contains files for the manuscript *Simulation of ultra-fast structured illumination in single-photon sensitive single-pixel lidar* by Jaakko Olkkonen, Josef Taher, Teemu Hakala, Antero Kukko, Harri Kaartinen, and Juha Hyyppä.

## Abstract
This study presents a novel single-pixel imaging lidar system utilizing VCSEL arrays and single-photon detection for high-speed structured illumination and accurate reflectance estimation. The research developed a detailed measurement model and inverse rendering workflow. These were evaluated using ray tracing simulations that generated full-waveform intensity data. The proposed method achieved millimeter-level precision in range measurements and accurate reflectance estimates by leveraging local angle of incidence information. Notably, the method does not require separate surface normal estimation from dense point clouds. Future research may explore additional applications of the local angle of incidence information and further validate the model in real-world scenarios. 

# File descriptions

- **ray_tracing.ipynb**: 
  This notebook simulates light intensity measurements by performing ray tracing for Gaussian beams interacting with Lambertian targets. It models multiple illumination sources and generates the resulting full-waveform intensity data.
- **inverse_rendering.ipynb**: 
  This notebook performs the inverse rendering of simulated light intensity measurements. It begins by defining illumination patterns and adding noise to the data to mimic single-photon sensing. The notebook then uses maximum likelihood estimation to extract individual signals from these noisy measurements. Finally, it reconstructs the properties of each point, including range, angle of incidence, and reflectance, by solving a sequence of nonlinear least squares problems.
- **ray_tracing_data**: 
  This directory contains data generated by the `ray_tracing.ipynb` simulation. The data is stored in a single file using the `pickle` format, which contains a list of dictionaries. Each dictionary holds the simulation results for different illumination sources.
  
  **Note:** Ensure that the data file is present before running the `inverse_rendering.ipynb` notebook.
  
# Dependencies

This project requires the following Python libraries:

- `matplotlib`
- `numpy`
- `pickle`
- `scipy`
- `pandas`
