---
layout: post
tags: [model-choice, Labrids]
categories: evolution
---





 





Research
--------

-   Bootstrapping procedures should have the option to refit the
    painting. Currently use the fixed painting but refit parameters.
-   wrote the function peaks\_update() which update the painting as well
    as the OU peak parameters.

![20 replicates, bootstraps the painting step as
well](http://openwetware.org/images/thumb/e/e1/Bootstrap_painting.png/600px-Bootstrap_painting.png)

![image](/skins/common/images/magnify-clip.png)

20 replicates, bootstraps the painting step as well

Computing / Package
-------------------

-   LR\_bootstrap and model\_bootstrap should be the same function call
    with an optional second model for the LR bootstrapping. Similarly
    the LR\_bootstrap\_all and model\_bootstrap\_all() should be the
    same function call. Will simplify documentation, error handling,
    redundancy etc.
    -   Will need to combine the return object types: model\_boots
        object or an LR\_boots object though. Will need an indicator for
        their type, and combine a plot function that can handle both.

-   The fit\_k\_peaks can't actually take an ouchtree, though it will
    try, due to the strange behavior of the ape package in tree pruning
    discussed earlier. Will eventually need a better work around than
    writing out and reading back in the nexus file. Should post this
    issue to r-sig-phylo.

-   The refit painting bootstrap needs the original ape-format (phylo
    class) tree, due to the above problem. It's been added as an
    argument to the bootstrapping calls.

### Troubleshooting

-   The partitions function may assign all points to only three regimes
    even though it is given four regimes to fit to. This has been
    causing a rather subtle bug in bootstrapping the ou4 model in the
    labrid dataset. Trying to address by modifying the function
    infer\_painting(), a function child of fit\_k\_peaks() function, to
    calculate k as the maximum value in the factor list, rather than the
    length of the factor list. Still leads to other errors...

-   also tried modifying so that factor matching is explicit, lines 54,
    55 of infer\_niches.R Still get NAs in regime inference when its
    failed to use all the peaks.

-   Ways to force utilizing all peaks??

#### Speed concerns

-   Refitting is much slower. Will need to explore parallelizing each of
    the bootstrapping fits. Should also perform profiling and start
    moving slowest parts into C code. Will also need to avoid any
    redundant bootstrapping.

-   *Shouldn't refit the true model in each row.* Should be able to
    reuse the simulated data and the fit of the true model, and just
    refit each comparison model to that simulated dataset. Doesn't seem
    fit naturally in the framework of the bootstrap package, however.

**Profiling Results**

-   Profiling with Rprof(), summaryRprof()
-   fit\_k\_peaks() is 90% of computational time
    -   it's member function, fit\_k\_partitions() is 65% total time
    -   it's member function, infer\_painting() is 10% of total time
    -   optim function, called by fit\_k\_partitions() (also called by
        hansen) is 71% of total time

Misc / Notes
------------

-   Following phylogenetics discussion group Friday, Samantha passed on
    new suggestions to Brian, now on the [planned
    updates](http://code.google.com/p/brownie/issues/list "http://code.google.com/p/brownie/issues/list")
    for Brownie.

Talks
-----

-   Need to prepare Evolution Discussion Group talk for next week.

-   Survey for CSGF

-   Computing tool

-   Teaching with technology -- GTC

-   Effective Assessment -- GTC

-   ievobio?

Meetings, etc
-------------

-   Grad Teaching Community -- tonight
-   Open Science Meeting -- Weds

\

