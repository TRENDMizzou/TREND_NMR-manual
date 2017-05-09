### Plotting script -- display the principal components identified by the main script

* #### GUI and CLI programs

  GUI: `trendplotgui.exe` in Windows and Linux, `trendplotgui.app` in OS X

  CLI: `trendplot.exe` in all platforms

* #### Synopsis

  `trendplot.exe [-r] [-f] [prefix] [-x [xaxisfile]] [-u [Unit]] [-n [the first N components]]
  [-p] [-e] -m [0/1/2/3/4/5]] --plot`

* #### Description

  - `trendplot.exe` plots the output of `trendmain.exe`. It is normally used to plot 
  first principal component (PC1) or n principal components. It can also graph a 
  scree plot of the sizes of the PCs. It uses matplotlib.
  - Note that each time `trendmaingui` or `trendmain` launches it creates 
  a temp directory to save temporary files for `trendplot` and `trendplotgui` and 
deletes the old one (if it exists). This enables `trendplot` and 
`trendplotgui` to use results of the last run of `trendmain` or `trendmaingui`.   

* #### Options

  * `-r`  
    `-r` reads all arguments used by `trendmain.exe`. Therefore when `-r` is used
    all `trendplot.exe` options related to `trendmain.exe` program, such as `-f` 
    and `--ica` options can be omitted.  
  * `-f [input prefix name]`       
    `-f` specifies prefix of input files. This needs to be the same as specified 
    with the `-o` option when using the `trendmain.exe` program. e.g. uM or time (min)
  * `-x [xaxisfile]`   
    The usage is identical to the `-x` option of `trendmain.exe`.  
  * `-u [Unit]`   
    The usage is identical to the `-u` option of `trendmain.exe`.  
  * `-n [integral number N]`   
    `-n` specifies the number of principal components to plot. For example, 
    `-n 3` plots the first 3 principal components.  
  * `--single`  
    `--single` plots the component number `N` specified by `-n` option. For 
    example, `-n 3 --single` plots the third principal component only.  
  * `-p`   
    `-p` plots PC1 values with normalization. This is normally the most 
    important trend of change in an experiment. It is used without argument.  
  * `-e`   
    `-e` plots the scree plot, i.e. the size of each of the principal components   
  * `-m [0/1/2/3/4/5]`

    `-m`  turns on normalization of the `N` principle components plotted using 
    the `-n` option.  There are several modes of normalization to choose among;
    see the table below for the choices. When `-m` option is turned on, the 
    normalized PC values will be saved to `normalizedPC.csv` file.  
   
| Normalization mode | meaning |
| -- | -- |
| 0 | No normalization on PC values |
| 1 | Normalize all PC values to 1.0, with PC1 increasing (typical for a ligand binding isotherm) |
| 2 | Normalize all PC values to 1.0, regardless of the direction |
| 3 | Normalize PC1 to 1.0 and set it to increase. Normalize all other components to PC1 |
| 4 | Normalize PC1 to 1.0 without changing its orientation. Normalize all other components to PC1 |
| 5* | Normalize PC values to the sum of PC1+PC2 |
| 6<sup>$</sup> | Normalize 2 phase binding isotherms into monotonic increasing, reverse turning point |
\* This mode was used for two sequential binding events  
$  This option might be used for binding isotherms of titrations where 
    spectra in the middle of the titration are severely perturbed and the 
    trajectory of change is V-shaped.

  * `--biplot`

    This option shows the "bi-plot" of the first two principal components in 
    matrix V<sup>T</sup>. (A bi-plot is the equivalent of a score plot in the nonmenclature
    of the metabolomics field).

  * `--ica`

    This option is required for plotting ICA results. All _principal components_
    mentioned above will be replaced by _independent components_ when `--ica` is
    turned on.

  * `--plot`  
    `--plot` is optional. When it is on, all figures will be saved as PNG images.  
