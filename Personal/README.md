# Notes on ML

## Boosting
p.364, HTF

### Algorithm
<img src="https://latex.codecogs.com/svg.image?\textrm{Initialize&space;the&space;observation&space;weights&space;}w_i=1/N,\;i=1,2,...,N.">
<img src="https://latex.codecogs.com/svg.image?\inline&space;\large&space;\\&space;\textrm{2.&space;For&space;}m=1&space;\textrm{&space;to&space;}M:&space;\\(a)&space;\textrm{&space;Fit&space;a&space;classifier&space;}G_m(x)&space;\textrm{&space;to&space;the&space;training&space;data&space;using&space;weights&space;}&space;w_i.&space;\\(b)&space;\textrm{&space;Compute}&space;\\\;\;\;\;\;\;\;\;&space;err_m=\frac{\sum_{i=1}^{N}w_iI(y_i\neq&space;G_m(x_i))}{\sum_{i=1}^Nw_i}&space;\\(c)&space;\textrm{&space;Compute&space;}&space;\alpha_m=log((1-err_m)/err_m)&space;\\(d)&space;\textrm{&space;Set&space;}&space;w_i\leftarrow&space;w_i\cdot&space;exp[\alpha_m&space;\cdot&space;I(y_i&space;\neq&space;G_m(x_i))],&space;\;&space;i=1,2,...,N.&space;\\&space;\textrm{3.&space;Output&space;)}G(x)&space;=&space;sign[\sum_{m=1}^{M}\alpha_mG_m(x)].">


