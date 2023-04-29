# Multipole Decomposition for Scattering (MDS)
![multipole_schematic](/assets/img/fig_schematic.png)

## Overview
The open-source Matlab package MDS is the numerical implementation of multipole decomposition for arbitrary scattering objects, based on a combination of full-wave simulation and numerical projection. Our algorithm is capable of computing higher-order multipole coefficients beyond dipole and quadrupole with decent efficiency. 

Two types of approaches for numerical projection are introduced, each suitable for different situations. The first type is surface integration based on the distribution of scattered field outside the scatterer, which is mainly used for the multipole analysis of single structures. The second type is volume integration based on the induced current density inside the scatterer, which is applicable to the building blocks in periodic structures such as metasurfaces and photonic crystals. 

## Usage
### Surface integration method

### Volume integration method
build the mesh. run the COMSOL simulation. run main_numerical.m. run plot

## Citing
If you find MDS useful for your research, we would appreciate you citing the following paper:

## Acknowledgements

