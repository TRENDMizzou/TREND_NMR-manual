### Fitting of Principal Components or Independent Components using TRENDanalysis   
#### Parameters
- The **`fitting`** is used to fit principal 
components (PC) or independent components (IC) calculatd by [Trendmain](../../manual/GUI/trendmaingui.md) 
or [TREND NMR](../trendmain/README.md).
To these PCs and ICs, TRENDanalysis fits an equation selected 
in the **`fittingmode`** menu. This can include an equation that you
provide yourself. TRENDanalysis will save 
an html report to directory containing the input data.  
The report will have the suffix of `_fitting_result.html`  
<img src="../png/trendanalysis/trendanalysis_1.png" alt="trendanalysis" width="600">
- When the **`readparm`** option is turned on by choosing `Yes`, 
`TRENDanalysis` fits a PC or IC calculated by 
`Trendmain` or `TREND NMR`. The component is recorded by X and Y
coordinates and any units provided for the X-axis. If `readparm` is
turned off by choosing `No`, the PC or IC will be read instead from
**`vtmatrix`**, **`xaxis`**, and **`xunit`**.
- **`pcn`** specifies which PC or IC to fit. It must 
be a positive integer. By default it is set to 1.  
- **`parameters`** specifies the parameters to fit. The 
parameters are separated by commas (`,`). Parameters and their values 
to initialize fitting can be given as equations, e.g.  
e.g. `KD=0.3`. When a parameter is given 
without an inital value, such as `Pt`, the initial value will be set as 1.  
**Note** all parameters must exist in the fitting function specified
under **`fittingmode`**  or **`function`**.  
- **`fittingmode`** allows the user to choose to fit a standard equation
  of TRENDanalysis. 
See  href=#LigandBinding>Fitting models</a> for details.  
- **`help_tab`**  
By default **`help_tab`** is set to `Run data fitting` which directs 
TRENDanalysis to fit a curve. 
Choosing an option other than `Run data fitting` will print out 
definitions of parameters listed under the **`fittingmode`** once 
the `Start` button is pressed. This will launch a help file in html
format.  
- **`constant`** specifies which values to fix in the fitting function. 
It can be left blank. Setting constants is similar to setting
**`parameters`**.   
- **`function`** allows user to define their own custom functions. See <a
  href=#UserDefine>User defined functdion</a> for details. Note that 
equation starts with `y=` is not allowed.  
- **`vtmatrix`**  
When **`readparm`** is turned off, **`vtmatrix`** is used to as the
source of PCA
  results calculated by TRENDmain or TREND NMR. 
- **`xaxis`**  
When **`readparm`** is turned off, **`xaxis`** is used to read the
X-axis file  
- **`xunit`**  
When **`readparm`** is turned off, **`xunit`** sets the unit of X-axis  
- **`normalmode`** sets the normalization mode of PC or IC to be
  fit. See [Trendplot manual](../../manual/CLI/trendplot.md) for details of
normalization mode.  


#### Fitting models:
- [1:1 protein-ligand binding (y_end, KD, Pt)](fitting/LigandBinding.md)
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
<img src="../png/trendanalysis/ligandbinding.png" alt="ligandbinding" width="600">  
- [Single exponential decay (A0, K, C)](fitting/exp_decay.md)
`Single exponential decay`:  {% math %} y = C + Ae^{-k \cdot x}
{% endmath %}, where <i>A0</i> is the initial amplitude,  {% math %} C {% endmath %}
is offset, <i>k</i> is the rate constant. Rate can be calculated as inverse
of t: {% math %} R=\frac{1}{t} {% endmath %}   
Similar to <a href=#LigandBinding>1:1 Protein Ligand Binding</a>, {%
math %} C, A, t {% endmath %} must be defined in either
**`pararmeters`** or **`constants`**. 
However, TRENDanalysis can initialize parameters for exponential fitting
(both exponential growth and decay) automatically and hence their
initial values do not need to be set, such as:  
<img src="../png/trendanalysis/exponential.png" alt="exponential" width="600">  
  - <a name="TwoPhase">Two phase exponential(A1, t1, A2, t2, C)</a>  
The function of `Two phase exponential` is {% math %} y =
A_1e^{-\frac{x}{t_1}} + A_2e^{-\frac{x}{t_2}} + C {% endmath %} ,
where {% math %} A_1, A_2 {% endmath %} stand for amplitudes of two
phases, {% math %} t_1, t_2 {% endmath %} are time constans of two
phases, {% math %} C {% endmath %} is offset. Choose the initial
values carefully according to the shape of your curve.   
  - <a name="Linear">Linear regression</a>  
Linear regression does not need **`parameters`** or **`constants`**,
therefore these two options will be ignored when linear regression model 
is chosen. 
  - <a name="UserDefined">User defined function</a>  
Besides implemented models descrbied above, TRENDanalysis also supports
user defined function. The equation can be input in **`function`**
text field, while **`parameters`** and **`constants`** are set in the
same way as descrbied before. **Note** initial values are very important
for any non-linear curve fitting. An example of user defined example is
given as:  
<img src="../png/trendanalysis/userdefine.png" alt="user defined" width="600">  
It is an example fitting data to exponential equation with rate constant
(R) instead of time constant (t), the equation is: {% math %} y=Ae^{Rx}
 + C {% endmath %}. Note in the **`function`** textfield 
a function instead of an equation is required. Therefore only
`A*exp(R*x) + C` is allowed, while `y=A*exp(R*x) + C` is wrong.  







 




