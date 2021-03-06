---
layout: post

categories: evolution
---





 





Evolution 2010 Day 2
--------------------

-   **Clay Cressler** : Can you trust evolutionary parameters estimated
    by complex phylogenetic comparative methods? A simulation study with
    OUCH

-   **Jeet Sukumaran** (Mark Holder lab) Performance and robustness of
    phylogeographic analytical studies

Tests common macroscopic models of inferring population structure (i.e.
via coalescent) an individual based simulation model.

-   **Graham Slater**, Luke Harmon, Liam Revell, Marc Suchard, Mike
    Alfaro. Estimating rates of phenotypic evolution and speciation from
    incomplete trees.

Fascinating talk on estimating rates when the tree is not resolved to
the species level. Approximate Bayesian Computing based approach which
simulates the tree to the species level as a pure birth process with
trait evolution by Brownian motion, estimating parameter posteriors by
ABC. Seemed to me this calculation could be done analytically, since the
Brownian rate inference depends only on the distribution of branch
lengths, which is simply exponential under the pure-birth (or constant
birth-death) model. For instance:

![ \\begin{align} L(\\beta | u ) &= \\frac{1}{\\beta\^N} \\exp \\left(
\\frac{- Q(\\vec u)}{2 \\beta} \\right)\\\\ Q(\\vec u) &= \\sum\_i
\\frac{(u\_i - u\_{i'})\^2 }{v\_{ii'} } \\end{align}
](http://openwetware.org/images/math/2/9/4/294d88d35ebd9a564f9f93f531fdfa03.png)

Well, if the branch length *v*~*i**i*'~ is exponentially distributed
with parameter λ

![ \\begin{align} L(\\beta | u) &= \\int \\exp\\left(- \\sum\_i
\\frac{(u\_i - u\_{i'})\^2 }{v }/2\\beta \\right) \\lambda e\^{-\\lambda
v} / \\beta\^N dv \\\\ L(\\beta | u) &= \\int \\exp\\left(-
\\frac{\\sum\_i (u\_i - u\_{i'})\^2 }{2\\beta v} - \\lambda v \\right)
\\lambda / \\beta\^N dv \\\\\\end{align}
](http://openwetware.org/images/math/e/2/e/e2ec1a2a59f94c87a70a64983656c668.png)

If we simply estimated the branch length as the mean always, we'd have
![ \\beta = \\sum\_i \\frac{(u\_i - u\_{i'})\^2 }{2 N \\lambda T }
](http://openwetware.org/images/math/0/e/6/0e699e1dc4680e00fc6e8b5fb962a35e.png)

\

-   **Andrew Hipp** Chromosome and genome size evolution in sedges

-   **John Huelsenbeck** The growth of Bayesian phylogenetics

\

\

