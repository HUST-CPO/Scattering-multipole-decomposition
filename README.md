# Multipole Decomposition for Scattering (MDS)
![multipole_schematic](/assets/img/fig_schematic.png)

## Overview
The open-source Matlab package MDS is the numerical implementation of multipole decomposition for arbitrary scattering objects, based on a combination of full-wave simulation and numerical projection. Our algorithm is capable of computing higher-order multipole coefficients beyond dipole and quadrupole with decent efficiency. 

Two types of approaches for numerical projection are introduced, each suitable for different situations. The first type is surface integration based on the distribution of scattered field outside the scatterer, which is mainly used for the multipole analysis of single structures. The second type is volume integration based on the induced current density inside the scatterer, which is applicable to the building blocks in periodic structures such as metasurfaces and photonic crystals. 

## Usage
### Scripts for surface integration method
`generate_sphere_pt.m`: Generate Lebedev quadrature weights and points that are given in both Cartesian and spherical coordinates.

### Scripts for volume integration method
`quad_point52tetra.m`: Get the Gaussian quadrature points and corresponding weights inside the scatterer. 

### Common scripts for both two methods
1. `field_build.m`: Read the scattered field/induced current density at each quadrature point computed by Comsol.
2. `field_from_cart2sph.m`: Convert the field data in the Cartesian coordinate to spherical coordinate.
3. `pm6_NeMo.m`: Calculate electric and magnetic multipole coefficients `aml` and `bml`.
4. `coff.m`: Summation for quadrature. 

### Scripts for Mie theory
1. `mie_scatter.m`: Compute the multipole coefficients using Mie theory for spherical scatterers.
2. `mie_cross_section.m`: Compute the normalized scattering cross-section based on multipole coefficients. 

### Run examples
Examples of the surface/volume integration method are in `./examples`. You can follow the following steps to run the benchmark:
1. Run the Comsol file `silicon_sphere.mph` and store each step of the parameter sweep in `./step`
2. Run the script `main_surface.m`/`main_volume.m`.
3. Run the script `main_mie.m`.
4. Run the script `numerical_and_mie_plot.m` to visualize the results. 

## Citing
If you find MDS useful for your research, we would appreciate you citing the following paper:
1. W. Guo, Z. Cai, Z. Xiong, W. Chen, and Y. Chen, ''Efficient and accurate numerical-projection of electromagnetic multipoles for arbitrary scattering objects,''

## Acknowledgements
The Matlab implementation of Lebedev and Gaussian quadrature is provided by Rob Parrish (Georgia Tech) and John Burkardt (Florida State University), respectively. We appreciate them for the useful numerical tools. 
