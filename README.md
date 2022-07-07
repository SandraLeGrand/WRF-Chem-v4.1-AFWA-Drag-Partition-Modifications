# WRF-Chem-v4.1-AFWA-Drag-Partition-Modifications

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6792554.svg)](https://doi.org/10.5281/zenodo.6792554) - Latest version (1.1.0)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.6713284.svg)](https://doi.org/10.5281/zenodo.6713284) - All versions

## Created 
Summer 2022

## Purpose
This repository contains modified Weather Research and Forecasting with Chemistry (WRF-Chem) Version 4.1 model code with Version 1.0 of the albedo-based drag partition parameterization originally developed by Chappell and Webb (2016) incorporated into the AFWA dust emission module.

## Modified Code Authors
* Theodore W. Letcher (ERDC)
* Sandra L. LeGrand (ERDC)
* Michelle L. Michaels (ERDC)

## Instructions
Download and compile the modified WRF-Chem code from the [Drag_Partition_Modified_Code](https://github.com/SandraLeGrand/WRF-Chem-v4.1-AFWA-Drag-Partition-Modifications/tree/main/Drag_Partition_Modified_Code) directory following the same build procedures required for setting up the baseline WRF-Chem code (see https://ruc.noaa.gov/wrf/wrf-chem/).

WRF-Chem v4.1 baseline source code and run instructions are available for download at https://github.com/wrf-model/WRF/releases/tag/v4.1.

To implement these changes into an existing copy of WRF-Chem v4.1, copy the .F files listed below from this repository to the corresponding WRF-Chem subdirectory (/Registry or /chem) and compile the WRF-Chem code. Note that because these steps include a change to the model registry, users will need to do a full clean of WRF-Chem (*./clean -a*) if these changes are being added to previously compiled code.

Files that differ from the WRF-Chem v4.1 baseline code and purpose:<br/>
* **WRF-v4.1/Registry/registry.chem** - file to add namelist variables<br/>
* **WRF-v4.1/chem/chem_driver.F** - passes *u*<sub>ns*</sub> data to the AFWA dust emission module<br/>
* **WRF-v4.1/chem/emissions_driver.F** - passes *u*<sub>ns*</sub> data to the AFWA dust emission module<br/>
* **WRF-v4.1/chem/module_gocart_dust_afwa.F** - AFWA dust emission module with drag partition code modifications

Though we used WRF-Chem v4.1 in this implementation example, the process should be relatively consistent for later WRF-Chem versions (currently on v4.4 at the time of publication). We recommend users planning to use the WRF-Chem/GOCART dust transport capability work with WRF-Chem v4.1 or later due to a critical bug fix in the GOCART deposition module.

Please refer to the technical report by Michaels et al. (2022; ERDC/CRREL TR-22-2) for detailed code descriptions, guidance on preparing the required input data, and model runtime instructions.

This repository also includes a copy of the WRF Pre-processing System (WPS) Version 4.2, obtained from https://github.com/wrf-model/WPS/releases/tag/v4.2. We used this version of WPS to generate terrain and atmospheric forcing condition inputs for simulations during our code implementation and testing process. 

## How to Cite

### Code
Letcher, T. W., LeGrand, S. L., and Michaels, M. L.: WRF-Chem-v4.1-AFWA-Drag-Partition-Modifications: Initial full model code release (v1.1.0), Zenodo [code], https://doi.org/10.5281/zenodo.6792554, 2022.

### Concept & Methodology
LeGrand, S. L., Letcher, T. W., Okin, G. S., Webb, N. P., Gallagher, A. R., Dhital, S., Hodgdon, T. S., Ziegler, N. P., and Michaels, M. L.: Application of a Satellite-Retrieved Sheltering Parameterization (v1.0) for Dust Event Simulation with WRF-Chem v4.1, Geosci. Model Dev. Discuss. [preprint], https://doi.org/10.5194/gmd-2022-157, in review, 2022.

## References

Chappell, A. and Webb, N. P.: Using albedo to reform wind erosion modelling, mapping and monitoring, Aeolian Res., 23, 63–78, https://doi.org/10.1016/j.aeolia.2016.09.006, 2016.

Michaels, M. L., Letcher, T. W., LeGrand, S. L., Webb, N. P., and Putnam, J. B.: Implementation of an albedo-based drag partition into the WRF-Chem v4.1 AFWA dust emission module, ERDC/CRREL TR-22-2, U.S. Army Engineer Research and Development Center, Hanover, New Hampshire, USA, https://doi.org/10.21079/11681/42782, 2022.
