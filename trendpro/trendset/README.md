## TRENDset - Batch Fitting of Binding Affinities (or Time Courses) 
### Description  
- TRENDset works on a batch of titrations to
  determine the binding isotherm and <i>K<sub>D</sub></i> of each
titration. The set of results are then sorted by <i>K<sub>D</sub></i>   
- Similar to TREND NMR, TRENDset has two menus, **`spectra`** and
  **`fid**, which function similarly.  
- `TRENDset` is launched using `trendset.app` or `trendset.exe`. After
  the batch run finishes, an HTML report with suffix of 
`-batch_run_result.html` will be opened in a browser window automatically.  
#### Arguments - Read from an **`index`** file  
- **`index`**  
Unlike `Trendmain` or `TREND NMR`, `TRENDset` can read most options from `index` file, which is read by **`index`** File Chooser Widget.      
<img src="../png/trendset/trendset_1.png" alt="trendset_1" width="600">   
The `index` file should be a CSV format spreadsheet. Each column in the
spreadsheet contains a parameter for the calculation. The title 
appears in the first row of the speadsheet.  Three arguments are 
**required** to be be given 
in a `index` file. Other arguments are optional.  
	- Required Arguments:
		- **`FILE_LOC`**: File location  
**`FILE_LOC`** specifies the location of each file or directory to be
used for PCA 
calculations. It can be given as the absolute path from the root directory, 
such as 
`/Users/username/data/titration1/1.ucsf`. **`FILE_LOC`** can also be a 
relative path to the `index` file. For example, if an index file `index.csv` 
is saved as `/Users/username/data/index.csv`, then the previous `1.ucsf`
can be given as a relative path from a current directory by listing it
as: `titration1/1.ucsf`.  
For Bruker Topspin directories, **`FILE_LOC`** should specify the `<expno>` 
level of the directory tree because `<expono>/` contains a 
processed spectrum as the `1r` or `2rr` file in its `/pdata/1`
subdirectory. 
Since the raw data is present in the `fid` or `ser` file in the same `<expno>`
directory, the **`fid`** menu can read this raw data by listing the `<expno>/` 
directory in the same way. See `brukerspectra` and
`brukerfid` in  [Trendmain manual](../../manual/CLI/trendmain.md) for
details.   
TRENDset also reads data from Agilent or Varian VnmrJ directories containing 
an `fid` file or `datdir/phasefile`. See 'agilentfid` and `agilentspectra` in  [Trendmain manual](../../manual/CLI/trendmain.md) for details.  
		- **`EXP_NAME`**: Experiment name   
TRENDset works on a batch of NMR spectra of titrations or time-dependent 
measurements. 
**`EXP_NAME`** names each titration (or time series) for your
convenience. 
		- **`XAXIS`**: X axis  
In the **`XAXIS`** column, the X axis (e.g. concentration of the ligand) 
is defined for each file. It will be used as the x-axis 
values for data fitting. It is the same as
the `xaxis` options of 
[Trendmain](../../manual/GUI/trendmaingui.md) and [TREND
NMR](../trendmain/README.md).  
An example of an index file directing the fittin of two titrations is:     
<img src="../png/trendset/trendset_index_1.png" alt="index" width="400">   
	- Optional Arguments for available in TRENDset:  
These arguments are optional and most of them can be set in the GUI of 
TRENDset as  "global" arguments. However these arguments can also be 
defined in the 
`index` file to overwrite the "global" arguments. Each *experiment*
(EXP_NAME) may have its own optional arguments.  
The below arguments are used to do PCA calculation and their details can
be found in the [Trendmain GUI manual](../../manual/GUI/trendmaingui.md) and [Trendmain CLI manual](../../manual/CLI/trendmain.md).   
		- **`FILETYPE`**: `type` option in `trendmain` or `trendnmr` 
for choosing file 
format.  Although TRENDset can determine the file type automatically.
the user can also specify **`FILETYPE`** argument. 
You can use this argument to analyze FID data in the **`spectra`** menu of TRENDset.  
		- **`SCALING`**: This indicates the caling method to apply to
		  rows of the data matrix. `Autoscaling` is usually preferred.
However, in titrations with intermediate exchange broadening, Pareto
scaling is preferred because it corrects sigmoidal distortion of binding
isotherms. See futhur description of scaling in the documentation of
([Trendmain GUI manual](../../manual/GUI/trendmaingui.md) and [Trendmain CLI manual](../../manual/CLI/trendmain.md).   
		- **`COLUMNSCALING`**:  Applies the chosen scaling method to the columns of the data matrix.   
		- **`XUNIT`**:  specifies the units of the X-axis 
(given by `XAXIS` column in the `index` file).   
		- **`THRESHOLD`** and **`THRESHOLDNUMBER`**:  These are used as
		  described for `trendmain` and `trendnmr`, in order to 
filter noise from NMR spectra.  
		- **`BINTIMES`**: 
		  Specify the number of points to be merged
		  together into a single point for the purpose of compressing
the spectra for a faster calculation. See the documentation of
[trendmain](../../manual/CLI/trendmain.md) and [TRENDNMR](../trendmain/README.md).  
		- **`SOLVENTFILTER`**: As described for handling 
		  FID signals in the documentation of
[trendmain](../../manual/CLI/trendmain.md) and [TREND NMR](../trendmain/README.md), 
`solventfilter` specifies a funciton to use to subtract the solvent 
filter signal from the FID.   
		- **`XLIM`** and **`YLIM`**: indices for selecting the region of
		  interest (ROI). These are coordinates in the NMR spectra given
as a point index number, in the same fashion as done in Bruker Topspin.
See more details in the next section.  
	- Optional Arguments for data fitting:  
		- **`FITTING_FUNC`**: Provides the location files configuring 
the fitting function. Its format is described below.   
		- **`NORMALMODE`**: selects the type of normalization, as in [trendplot](../../manual/CLI/trendplot.md).  


#### Arguments - Read from TRENDset GUI  
There are two menus of TRENDset, **`spectra`** and  **`fid`** (shown
below). These are designed to analyze NMR data in the frequency or 
time domain, respectively. 
As described above and 
in [Trendmain](../../manual/GUI/trendmaingui.md), preprocessing can be 
tailored using `scaling`, `xunit`, `threshold`, 
`thresholdnumber`, `xlim`, and `ylim`. If these arguments are not defined 
in the **`index`** file, they are read by the GUI of TRENDset.   
<img src="../png/trendset/trendset_fid.png" alt="trendset_fid" width="600">   
- `file` text box reads the configuration file for curve fitting.  It can be 
generated by running [TRENDanalysis](../trendanalysis/fitting.md), which
generates a  `fitting.config` file in the results folder. Or it
can be created by a text editor in the following format (**case-sensitive**):  

```bash
Parameters: KD=0.05, y_end=1.0
Constants: Pt=0.05
Function: y_end * 1.0 / (2.0 * Pt) * (KD + x + Pt - sqrt((KD + x + Pt) ** 2
- 4.0 * x * Pt))
```  

This is an example of configuration file used to fit 1:1 protein-ligand binding isotherm.   
The line starting with **Function** is the function for the binding isotherm 
in this example. 
(Note that it is a function, not an equation): 
{% math %} \frac{(K_D+x+Pt-\sqrt{(K_D+x+Pt)^2-4xPt)}}{2Pt} \times y_{\_end} {% endmath %}. 
The parameters are defined in the manual for [TRENDanalysis](../trendanalysis/fitting.md#protein-ligand).    
The line starts with **Parameters** defines the parameters to fit, while
the values specified here with initial estimates. In this
example, KD, y_end are parameters to fit, while their initial values are
set as 0.05 and 1.0, respectivley. If initial values are not given, then
it will be set as 1.0.   
The line starting with **Constants** defines the constant values that are
fixed in the fitting. Here Pt is fixed to 0.05. The Pt can also be
defined in the **Parameters** line as a parameter instead of a
constant.  
The units of KD and PT must be identical to the units of x-axis, which is
defined by the `xaxis` argument.  For example, if the `xaxis` option is
set to *mM* then the units of KD and PT are also *mM*.  
Another example is a configuration file of Exponential function:  
```bash
Exponential time
Parameters: A, C, T 
Constants: None
Function: C + A * exp(-x / T)
```
The line of **Exponential time** is a flag that turns on initialization
of parameters defined in the **Parameters** line. Usually the auto parameter 
initialization works fine. Hence, there is no need to list initial
values in the **Parameters** line. TREND also supports auto parameter
initialization for exponential function rate constant: `C + A * exp( -k * x)`. 
To turn it on
just add a line of **Exponential rate**.  The `Constants: None` line specifies
the absence of constants in the fitting.   
- `sort` argument defines which parameter to be sorted in the
  batch of results. By default `KD` will be sorted. **Note** If `sort`
is not set, or the parameters set by `sort` is not found in one or 
more fitting results, TRENDset will generate a table without sorting
selected parameters.   
- `order` defines the order of sorting. By default sorted values will be
  outputed in the ascending order.  
- `cutoff` defines which results are color-coded as a "hit". Values
  larger than `cutoff` in a descending order, or smaller than `cutoff` in an
ascending order will be considered  as "hits" and colored in green in the
generated table.   
- `title` is the title of output report. TRENDset will create a result
  folder named `title` (with spaces removed if there are any).
PCA results, preview of selected ROIs, and fitting results of each
experiment will be saved to the subdirectories named as
`TITLE/EXP_NAME/`.  
- `XLIM` defines the indices of x-axis points used in the PCA analysis, 
e.g.`1-max` means using all points in x-axis. `450-500` means
using points from 450 to 500. The definition of "points" is identical to
that used by `index` in Bruker Topspin.  
- `YLIM` defines indices of y-axis points used for PCA analysis, provided
the input data has two dimensions.  
- `ROI` allows manual selection of ROI. When it is checked, it will turn 
off the `XLIM` and `YLIM` option. A preview of the ROI will pop up the 
first spectrum, allowing selection of the ROI manually by dragging a 
rectangle across the spectrum. See [TREND NMR](../trendmain/README.md) for 
more details.  
