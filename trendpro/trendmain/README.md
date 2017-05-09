### TREND NMR - Binding Isotherms and  Time Courses Readily from NMR  
- TREND NMR is an improvement of the earlier [Trendmain](../../manual/GUI/trendmaingui.md) 
that is optimized for NMR.
- In the left side bar, there are three modes to choose from: **`spectra`**, 
**`fid`**, and **`peaklist`**. They function similarly with minor 
differences.  
- For details of each option, see the [GUI mannual](../../manual/GUI/trendmaingui.md) 
and [CLI mannual]((../../manual/CLI/trendmain.md)).  
<img src="../png/trendmain/trendnmr_1.png" alt="trendnmr_spectra" width="600">  
- The **`spectra`**  menu is used for analysis of NMR spectra. It is similar 
to the **`nmr`** menu of [Trendmain](../../manual/GUI/trendmaingui.md). 
- Comparing to [Trendmain](../../manual/GUI/trendmaingui.md), `TREND NMR` 
automatically selects the format of the NMR spectra. A series of 2D NMR 
spectra in NMRPipe `ft2`, Sparky `ucsf`, and `jcamp-dx` formats can be read 
by the `file` File Chooser widget. Fourier-transformed Bruker Topspin 
(`brukerspectra`) or Agilent VnmrJ (`agilentspectra`) directories can 
be read by `dir` Directory Chooser widget.  
- `ROI` option allows zooming in on the region of interest (ROI). 
When `ROI` option is turned on, a preview of the first spectrum in the 
series will pop up. The contour level can be adjusted by dragging the 
`Contour level` widget in the bottom of the preview. 
<img src="../png/trendmain/ROI_1.png" alt="trendnmr_ROI_1" width="600">  
<img src="../png/trendmain/ROI_2.png" alt="trendnmr_ROI_1" width="400">  
- The ROI can be selected by dragging a rectangular of the spectrum using 
mouse. After this window is closed, a preview of selected ROI will pop up 
and be saved as a `PNG` picture with suffix of `-ROI.png` to the directory 
of input spectra.  
- The **`fid`** menu is very similar to the **`spectra`** menu but 
removes options that FID do need, such as `threshold` and `binning`. Instead, 
`solventfilter` is added. FID files such as NMRPipe `fid`, Simens `RDA`, 
`JCAMP-DX` are supported by the `file` browser. Bruker Topspin `brukerfid` 
and Agilent VnmrJ `agilentfid` directories can be read by the `dir` browser.  
VnmrJ   
<img src="../png/trendmain/trendnmr_2.png" alt="trendnmr_fid" width="600"> 
- The **`peaklist`** menu currently only supports Sparky peak list format 
`sparky`. It supports scaling on both row (`--scaling`) and column 
(`--columnscaling`).   
<img src="../png/trendmain/trendnmr_3.png" alt="trendnmr_peaklist" width="600"> 


