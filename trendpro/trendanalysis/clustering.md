### Clustering of PCA results using TRENDanalysis   
#### Parameters
<img src="../png/trendanalysis/trendanalysis_2.png" alt="trendanalysis" width="600">
- The **`clustering`** menu of TRENDanalysis is used to visualize and
  cluster PCA results calculated by by [Trendmain](../../manual/GUI/trendmaingui.md)   
- When **`readparm`** option is turned on (choose `Yes`), `TRENDanalysis` 
reads PC values from `Trendmain` or `TREND NMR`. 
If **`readparm`** is turned off (choose `No`), the data will be read by
**`pcmatrix`** option.  
- **`biplot_option`** sets visualization mode of PCA biplots. Choices
  are `2D`, `3D`, `Both 2D and 3D`, and `None`.  
- **`cluster_method`** provides options of clustering methods, the
  default method is `K-means`. Parameters needed are listed in
parenthesis.  See details in [Clustering methods](#method)     
- **`parameter`** sets parameter for clustering. See
  **`cluster_method`** for details.  
- **`help_tab`**  
By default **`help_tab`** is set as `Run data clustering` and TRENDanalysis
will run data fitting as described. Options other than default `Run data
clustering` gives definitions of parameters shown in **`cluster_method`** and
will launch help file in html format.  
- **`pcn`**  
This option is a list of components selected for biplot, e.g 1-3 or
2,3,5. Only 3 or more numbers are allowed. Error will happen if 2 or less
numbers are selected. If 4 or more numbers are selected only the first 3
number of components will be used to plot 2D or 3D biplots. However
clustering results are calculated by all selected components.  
The syntax it uses is equivalent to specifying pages in a print dialog. 
For example,  `1, 3-5, 7` means selectinig components 1, 3, 4, 5, 7.  
- **`scale`**  
This option controls scaling of output biplots. If `uniform` is chosen
then in 2D or 3D biplots the axes will use the same scale, otherwise
each axis will be scaled automatically.  
- **`label`**  
when **`label`** is off labeling of data points in biplots will be
turned off.  
- **`labelfile`**  
This option reads a label file containg labels of each file. When no 
file is chosen for **`labelfile`**, TRENDanalysis will use file
names to label data points in biplots. The format of labeling file is
identical to `file.index` (See [manual of
trendmain](../../manual/CLI/trendmain.md)) for the format of
`fileindex`. **Note** the sequence in a label file must be identical to
its corresponding [fileindex] file.  
- **`pcmatrix`** 
When **`readparm`** is turned off, **`pcmatrix`** is used to read PCA
results calculated by TRENDmain or TREND NMR, the file name of which
ends in `-pc.txt`. 
- **`export`**  
When **`export`** is turned on clustering results will be saved as
`prefix-cluster_2d.txt` or `prefix-cluster_3d.txt`   
- **plot**  
When this option is checked, 2D and/or 3D biplots will be saved as PNG
images.    

#### <p hidden>method</p>
<h4>Clustering methods:</h4>  
##### <p hidden>kmeans</p>
<li> K-means (number of clusters)</li>  
The K-means algorithm needs to specify the number of clusters in
**`parameter`** option. By default it is set as 3. See
[K-means](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) for
details. 
##### <p hidden>agglomerative</p>  
<li>Aggolerative (number of clusters)</li>  
Similar to K-means, Agglomerative clustering also needs to specify the
number of clusters.  See [Agglomerative
Clustering](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.AgglomerativeClustering.html#sklearn.cluster.AgglomerativeClustering)
for details.  
##### <p hidden>affinity</p>  
<li>Affinity Propagation (preference)</li>  
This option perms Affinity Propagation Clustering of data. It doesn't
require prior-knowledge of number of clusters. Instead, `preference` is
used to choose exemplars. Choose `None` in **`parameter`** option to set
`preference` to the median of input similarities. See
[affinity_propagation](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.affinity_propagation.html#sklearn.cluster.affinity_propagation) for details.   
##### <p hidden>dbscan</p>  
<li> DBSCAN (min_sample)</li>  
This option performs DBSCAN(Density-Based Spatial Clustering of Applications) clustering. The `min_sample` parameter defines the number of samples to be considered as a core point. 
See
[DBSCAN](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html)
for details.  
##### <p hidden>meanshift</p>  
<li>Mean Shift (bandwidth)</li>  
This option applys mean shift clustering. The **`parameter`**  can be
set as `None`. See [Mean
Shift](http://scikit-learn.org/stable/modules/generated/sklearn.cluster.MeanShift.html)
for details.  


