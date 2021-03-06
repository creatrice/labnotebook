---
layout: post
tags: [warning-signals]
categories: [ecology]
---





 





Reading
-------

Trying to make this show reading of the day, the script below shows only
current reading:

Friendfeed discussion on solving this:

Warning Signals
---------------

-   Implementing likelihood-based methods for early warning signals.
    Trying three models:

![ \\begin{align} dX =& (\\theta\_1 + \\theta\_2 X) dt + \\theta\_3
dW\_t \\\\ dX =&(\\alpha\_0+\\beta t) (\\theta + X) dt + \\sigma dW\_t
\\\\ dX =& \\alpha(t) (\\theta + X) dt + \\sigma dW\_t \\end{align}
](http://openwetware.org/images/math/3/f/8/3f8dd657158475757eb6bd177e3c3ad1.png)

\

-   Model 3 is intended to be a changepoint analysis, where α(*t*) is
    piecewise constant.
-   I solved analytically the transition probability density in Model 2
    on User:Carl Boettiger/Notebook/Stochastic Population
    Dynamics/2010/05/06, see this and the following entry.
-   Code implementations are in [Structured
    Populations](http://github.com/cboettig/structured-populations "http://github.com/cboettig/structured-populations")
    repository

#### To Do

1.  Simulation routine for custom equations (2, 3)
2.  Neyman-Pearson Likelihood ratio test method between models
3.  Simulation from actual population dynamics -- update warning signals
    method to return individual runs

\

\

\

