Assignment 9.3
================
Taniya Adhikari
05/16/2021

Calculate the probability of a model ensemble that uses simple majority
voting making an incorrect prediction in the following scenarios.

The ensemble makes an error just in case k = (n+1)/2 or more models
simultaneously. Since we are calculting probability of model ensemble
making incorrect predictions, we are not looking for probability of
success, instead we are interested in probability of failure. Thus
*q* = *ϵ*
  
The formula for exact k making an error is:  
$P(K=k) = \\binom{n}{k}\\epsilon^k(1-\\epsilon)^{(n-k)}$  
The formula for probability of error is:  
$P(K\\geq k) = \\sum\_{k}^n\\binom{n}{k}\\epsilon^k(1-\\epsilon)^{(n-k)} = 1 -P(K\\leq(k-1))$  
1. The ensemble contains 11 independent models, all of which have an
error rate of 0.2.

``` r
1 - pbinom(5, size=11, prob=0.2)
```

\[1\] 0.01165421

1.  The ensemble contains 11 independent models, all of which have an
    error rate of 0.49.

``` r
1 - pbinom(5, size=11, prob=0.49)
```

\[1\] 0.4729477

1.  The ensemble contains 21 independent models, all of which have an
    error rate of 0.49.

``` r
1 - pbinom(10, size=21, prob=0.49)
```

\[1\] 0.4630479
