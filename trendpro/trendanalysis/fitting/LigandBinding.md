#### Fitting models:
  - <a name="LigandBinding">1:1 protein-ligand binding (y_end, KD, Pt)</a>   
This model provides an equation for 1:1 protein-ligand binding: 
{% math %} y = \frac{(K_D+x+Pt-\sqrt{(K_D+x+Pt)^2-4xPt)}}{2Pt} \times y_{\_end} {% endmath %},
where <i>y</i> is the fraction of bound or free protein (indicated by PC 
or IC), <i>x</i> stands for total ligand concentration <i>[Lt]</i> which is 
given by **`xaxis`** options in `Trendmain`, `TREND NMR` or
`TRENDanalysis`, 
{% math %} K_D {% endmath %} stands for dissociation constant, which is the
parameter to be fit here and should be set in the **`parameters`**
textfield, {% math %}Pt{% endmath %} stands for total protein 
concentration, {% math %} y_{\_end} {% endmath %} stands for y value 
when ligand concentration 
is infinite. If binding isotherm is represented by normalized PC1 the
initial value of {% math %} y_{\_end} {% endmath %} can be set as 1.0. 
They can be either parameters to fit (set in **`parameters`**) or fixed as constant values (set in
**`constant`** texfield) 
**Note**, the unit of {% math %} Pt {% endmath %} must be identical to
unit of x values (**`xunit`**), the fitted binding affinity {% math %} 
K_D {% endmath %} also have the same unit.  
An example of 1:1 protein-ligand binding is shown below. 
<img src="../../png/trendanalysis/ligandbinding.png" alt="ligandbinding" width="600">  
