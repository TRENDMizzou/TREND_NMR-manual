### COordiNated ChemIcal Shifts bEhavior (CONCISE) analysis using TRENDanalysis  
#### Important  
This tab can only be launched **after** the peak lists have been analyzed via 
[**peaklist**](https://trendmizzou.gitbooks.io/trend_nmr-manual/content/trendpro/trendmain/#peaklist)   tab of 
[TREND NMR](https://trendmizzou.gitbooks.io/trend_nmr-manual/content/trendpro/trendmain/#peaklist)  
#### Parameters
<img src="../png/trendanalysis/concise_1.png" alt="trendanalysis" width="600">
- **`start`** and **`end`** choose the start and end states for CONCISE analysis. 
The peak lists were read in the [`peaklist`](https://trendmizzou.gitbooks.io/trend_nmr-manual/content/trendpro/trendmain/#peaklist) 
tab of tab of [`TREND NMR`](https://trendmizzou.gitbooks.io/trend_nmr-manual/content/trendpro/trendmain/#peaklist)  
#### <p hidden>options</p>
- **`peaks_retained_for_CONCISE`** provides three choices of NMR peaks to retain for CONCISE. 
The default option is: **Extreme**: `Discard peaks that do not begin or end at extremes 
of conditions specified`. The second option is: **Order**: `Delete peaks not shifted in order of input files` 
The third option is **Full set**: `Use all peaks for inital assessment`  See also [Interactive Plot](#checkbox)  
#### <p hidden>linearity</p>  
- **`linearity`** The threshold for the degree of linearity. It is defined as 
SD<sub>PC1</sub>/SD<sub>PC2</sub>.  
[(Cembran et al., 2014)](https://www.ncbi.nlm.nih.gov/pubmed/24604024). 
It can also be adjusted by the Slider of [Interactive Plot](#linearity2)  
#### <p hidden>threshold</p>  
- **`smallest_peak_shifts_to_retain`** This removes peaks with small shifts along PC1
that are smaller than the threshold (default: 0.03 ppm).   
It can also be adjusted by the Slider of [Interactive Plot](#threshold2)  
#### <p hidden>labelfile</p>  
- **`labelfile`** refers to the file containg a list of labels for the
  points. 
The format of this file is identical to 
`file.index` (See the [manual of trendmain](../../manual/CLI/trendmain.md) for 
the format of `fileindex`.) **Note** the sequence in a label file must be 
identical to its corresponding [fileindex] file. When no file is chosen
for **`labelfile`**, TRENDanalysis will use the file names to label the CONCISE.   
#### <p hidden>interactive</p>  
#### Interactive Plot  
<img src="../png/trendanalysis/concise_2.png" alt="CONCISE" width="600">  
An interactive plot is shown after the **Start** button is clicked:  
(A) The average PC score of NMR peak shifts is the average PC1 for the ensemble 
of NMR peak shifts, expressed as the number of standard deviations (SDs) of PC1.
#### <p hidden>checkbox</p>  
(B) Checkboxes for three choices of NMR peaks to retain for CONCISE are shown. 
The **Extreme Enforced** option was sued in the example shown. **Extreme Enforced** 
selects the subset of residues following the pattern that the peak of the open 
(unliganded) state lies at one extreme position and the peak of the most 
closed complex lies at the other extreme 
[(Cembran et al., 2014)](https://www.ncbi.nlm.nih.gov/pubmed/24604024)  . By default 
extremes are the first and last files in the input files. Other files can be 
chosen as starting and ending states (i.e., extremes) in TRENDanalysis. 
The **Order Enforced** option selects only the subset of residues with
NMR peaks that shift in the order specified by the order of the file names 
of peak lists. Full Set uses all peaks in the assessment.
See also [**`peaks_retained_for_CONCISE`**](#options)  
#### <p hidden>linearity2</p>  
(C) The conformational populations are represented by replotting the average 
PC score as a Gaussian distribution with the SD shown. The threshold for 
linearity parameter (defined as SD<sub>PC1/</sub>/SD<sub>PC2</sub>) 
is also set in the field called [**`linearity`**](#linearity)  
#### <p hidden>threshold2</p>  
(D) The interactive slider bars are used to set the thresholds for linearity and size 
required of the peak shifts. These are displayed with defaults of linearity set 
at 3.0 SD<sub>PC1/</sub>/SD<sub>PC2</sub> and peak shifts at 0.03 ppm. 
The threshold for linearity is also defined in the field of [**`threshold`**](#threshold)  
#### References  
1. [Cembran, A., Kim, J., Gao, J., & Veglia, G. (2014). NMR mapping of protein conforma- tional landscapes using coordinated behavior of chemical shifts upon ligand binding. Physical Chemistry Chemical Physics, 16(14), 6508](https://www.ncbi.nlm.nih.gov/pubmed/24604024').   
2. [Xu, J, Van Doren, S. (2018). Chapter Seven - Affinities and Comparisons of Enzyme States by Principal Component Analysis of NMR Spectra, Automated using TREND Software Methods in Enzymology
607, 2018, 217-240](https://www.ncbi.nlm.nih.gov/pubmed/30149859)   
You can also read the chapter with the [link](https://books.google.com/books?id=mvhqDwAAQBAJ&lpg=PR7&ots=jYrRtoo2kH&dq=Affinities%20and%20Comparisons%20of%20Enzyme%20States%20by%20Principal%20Component%20Analysis%20of%20NMR%20Spectra%2C%20Automated%20using%20TREND%20Software&pg=PA226#v=onepage&q&f=false)   
<iframe frameborder="0" scrolling="no" style="border:0px" src="https://books.google.com/books?id=mvhqDwAAQBAJ&lpg=PR7&ots=jYrRtoo2kH&dq=Affinities%20and%20Comparisons%20of%20Enzyme%20States%20by%20Principal%20Component%20Analysis%20of%20NMR%20Spectra%2C%20Automated%20using%20TREND%20Software&pg=PA226&output=embed" width=500 height=500></iframe>  



