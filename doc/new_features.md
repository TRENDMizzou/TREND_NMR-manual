## Coming Soon (~2019-5-15): 

### TREND NMR (a new package including TREND NMR, TRENDanalysis, TRENDset) 
#### TRENDNMR  
##### An improvement of `trendmaingui` that is optimized for NMR  
- Auto file format detection  
- Supports zooming in on the Region of Interest (ROI)  
- Flag spectral intensity decrease, warn possible aggregation  
- Powerful and flexibile peak lists support:  
	- 2D or mutlidimension NMR peak lists  
	- Besides chemical shifts, other peak properties, such peak height,  can also be scaled and calculated.   
	- Capability to combine or interleave different fields of the same peak
	- Multiple missing value handling methods.    
	- The peak list can be referenced to the first spectrum.   
	- Supports BMRB accession code and NMR-START format.  
	- Implement CONCISE strategy for comparing enzymes using their NMR peak lists.  

#### TRENDanalysis
- Supports various data fitting models, including fitting of
 <i>K<sub>D</sub></i> to binding isotherm  
- Supports various clustering methods of `trendmain` or `TREND NMR` results  
- Supports fitting with user-defined equations  
- PCA biplot and multiple clustering methods  
- CONCISE strategy support  

#### TRENDset
- Works on a batch of titrations to determine the bindign isotherm of Kd
  of each titration, with ranking by <i>K<sub>D</sub></i>  
- Can be used to work on a batch of any data series and ranking the
  results on selected parameters    

### TREND classic
#### `trendmaingui` and `trendmain` 
- Supports zooming in on the Region of Interest (ROI)      
- Supports Simens RDA format
- Supports Matlab MAT-File format, Python Numpy NPY format
- More converged noise detection algorithm
- Support multiple users on Linux platform

#### `trendreconstructgui` and `trendreconstruct`  
- Supports ICA reconstruction  

### Released (2016-11-22)

#### `trendmaingui` and `trendmain`  
- Supports Bruker Topspin FID/spectra, Agilent(Varian) FID/Spectra
- Supports various [JCAMP-DX](https://badc.nerc.ac.uk/help/formats/jcamp_dx/) formats 
- Enables clipping of input video by setting `starttime` and `endtime`

#### `trendreconstructgui` and `trendreconstruct`  
- Supports reconstruction of NMRPipe FT2 format
- Supports reconstruction of Topspin FID/Spectra, Agilent FID

