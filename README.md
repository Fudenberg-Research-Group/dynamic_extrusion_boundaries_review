# Chromatin loop extrusion with dynamic boundaries

### description
This GitHub repository contains tools for simulating chromatin loop extrusion using a dynamic model of CTCF to better understand how binding of CTCF contributes to chromatin organization and regulation.


### requirement
- Python
- Polychrom: A toolkit for polymer simulations. (https://github.com/open2c/polychrom)
- Openmm: A library for molecular simulations. (https://github.com/openmm/openmm)


### usage
#### running simulaitons 
1. One-Dimensional Lattice Simulation:
Before running the full molecular dynamics simulations, implement loops on a one-dimensional lattice to determine pairs of monomer indices involved in loop extrusion. This step helps define the harmonic 'bonds' input data for the coarse-grained molecular dynamics simulations. Parameters such as the lifetime, velocity, and density of extruders (Cohesins) can be adjusted in the configuration file located at config/simulation_params.py. You can find the Python script for this simulation in the script/simulations directory.

2. Run the coarse-grained molecular dynamics simulations to model loop extrusion. 

#### processing simulation data
After running the simulations, process the resulting trajectory data to generate virtual ChIP-seq data or contact maps. The scripts for data processing are available in the script/processing directory.
##### example 
To generate contact maps: 
'''
python script/processing/process_data.py
'''

#### analysis
Once the data is processed, perform various analyses to quantify features such as:

- FRiP (Fraction of Reads in Peaks)
- TADs (Topologically Associating Domains)
- Dots
-Vermicelli: Analysis of accumulation of extruders on axial structures.
The analysis scripts are provided as Jupyter notebooks in the analysis directory.
Each notebook includes detailed instructions and examples to guide you through the analysis process.




