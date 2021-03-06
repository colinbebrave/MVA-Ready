
[<img src="https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/banner.png" alt="Visit QuantNet">](http://quantlet.de/index.php?p=info)

## [<img src="https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/qloqo.png" alt="Visit QuantNet">](http://quantlet.de/) **MVAkernelfunctions** [<img src="https://github.com/QuantLet/Styleguide-and-Validation-procedure/blob/master/pictures/QN2.png" width="60" alt="Visit QuantNet 2.0">](http://quantlet.de/d3/ia)

```yaml

Name of QuantLet : MVAkernelfunctions

Published in : Applied Multivariate Statistical Analysis

Description : 'Plots different kernel functions: Uniform, Triangle, Epanechnikov, Quartic
(biweight), Gaussian.'

Keywords : 'gaussian, kde, kernel, kernel smoothing, quartic, smoothing, uniform, gaussian,
Epanechnikov, quartic, plot, graphical representation'

See also : SPMdenepatri, SPMdensity, SPMkdeconstruct, SPMkernel

Author : Andrija Mihoci, Awdesch Melzer

Submitted : Tue, September 09 2014 by Awdesch Melzer

```

![Picture1](MVAkernelfunctions-1.png)


```r

# clear variables and close windows
rm(list = ls(all = TRUE))
graphics.off()

# Different Kernel Functions
u = seq(-3, 3, 0.01) 

K_Uniform      = 0.5 * (abs(u) <= 1)                    # kernel of uniform distribution
K_Triangle     = (1 - abs(u)) * (abs(u) <= 1)           # kernel of triangle distribution
K_Epanechnikov = 0.75 * (1 - u^2) * (abs(u) <= 1)       # epanechnikov kernel
K_Quartic      = 0.9375 * (1 - u^2)^2 * (abs(u) <= 1)   # kernel of quadratic biweighted distribution
K_Gaussian     = 0.3989 * exp(-0.5 * u^2)               # kernel of a gaussian distribution

# Plot Kernels
par(mfrow = c(2, 3))

plot(u, K_Uniform, type = "s", col = "blue3", ylim = c(0, 1), ylab = "", xlab = "", 
    lwd = 2.5)
title("Uniform")

plot(u, K_Triangle, type = "s", col = "blue3", ylim = c(0, 1), ylab = "", xlab = "", 
    lwd = 2.5)
title("Triangle")

plot(u, K_Epanechnikov, type = "s", col = "blue3", ylim = c(0, 1), ylab = "", xlab = "", 
    lwd = 2.5)
title("Epanechnikov")

plot(u, K_Quartic, type = "s", col = "blue3", ylim = c(0, 1), ylab = "", xlab = "", 
    lwd = 2.5)
title("Quartic (biweight)")

plot(u, K_Gaussian, type = "s", col = "blue3", ylim = c(0, 1), ylab = "", xlab = "", 
    lwd = 2.5)
title("Gaussian")


```
