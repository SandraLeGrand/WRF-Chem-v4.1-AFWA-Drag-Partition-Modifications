# WRF-Chem-v4.1-AFWA-Drag-Partition-Modifications

[![DOI](https://zenodo.org/badge/506778395.svg)](https://zenodo.org/badge/latestdoi/506778395)

## Created 
Summer 2022

## Purpose
This repository contains the four modified WRF-Chem v4.1 files required to incorporate version 1.0 of the albedo-based drag partition parameterization originally developed by Chappell and Webb (2016) into the AFWA dust emission module.

## Modified Code Authors
* Theodore W. Letcher (ERDC)
* Sandra L. LeGrand (ERDC)

## Instructions
Though we used WRF-Chem v4.1 in this implementation example, the process should be relatively consistent for later WRF-Chem versions (currently on v4.4 at the time of publication). We recommend users planning to use the WRF-Chem/GOCART dust transport capability work with WRF-Chem v4.1 or later due to a critical bug fix in the GOCART deposition module.

WRF-Chem v4.1 baseline source code and run instructions are available for download at https://github.com/wrf-model/WRF/releases/tag/v4.1.

To implement these changes, copy the .F files listed below from this repository to the corresponding WRF-Chem subdirectory (/Registery or /chem) and compile the WRF-Chem code. Note that because these steps include a change to the model registry, you will need to do a full clean of WRF-Chem in order for the new code to compile correctly if adding these changes to previously compiled code.

Code included in this repository and purpose:<br/>
* **WRF-v4.1/Registry/registry.chem** - file to add namelist variables<br/>
* **WRF-v4.1/chem/chem_driver.F** - passes *u*<sub>ns*</sub> data to the AFWA dust emission module<br/>
* **WRF-v4.1/chem/emissions_driver.F** - passes *u*<sub>ns*</sub> data to the AFWA dust emission module<br/>
* **WRF-v4.1/chem/module_gocart_dust_afwa.F** - AFWA dust emission module with drag partition code modifications

Please refer to the technical report by Michaels et al. (2022; ERDC/CRREL TR-22-2) for detailed code descriptions, guidance on how to prepare the required input data, and model runtime instructions. 

## References

Chappell, A. and Webb, N. P.: Using albedo to reform wind erosion modelling, mapping and monitoring, Aeolian Res., 23, 63–78, https://doi.org/10.1016/j.aeolia.2016.09.006, 2016.

Michaels, M. L., Letcher, T. W., LeGrand, S. L., Webb, N. P., and Putnam, J. B.: Implementation of an albedo-based drag partition into the WRF-Chem v4.1 AFWA dust emission module, ERDC/CRREL TR-22-2, U.S. Army Engineer Research and Development Center, Hanover, New Hampshire, USA, https://doi.org/10.21079/11681/42782, 2022.
