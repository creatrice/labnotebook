---
layout: post
tags: [model-choice]
categories: evolution
---





 





Research
--------

-   Bootstrap the fitted models (rather than allow the parameters to be
    refit, simply evaluate the likelihood of the model under each
    simulated dataset)
-   Directly evaluate [Neyman-Pearson
    lemma](http://en.wikipedia.org/wiki/Neyman%E2%80%93Pearson_lemma "http://en.wikipedia.org/wiki/Neyman%E2%80%93Pearson_lemma")
    for each pairwise model comparison.
-   Also analyze the bootstrapped likelihoods directly (and without
    refitting) for each model.

#### To Do

-   Add a summary function for the likelihood\_ratio\_bootstrap.R
    library
-   final wrapper function for infer\_niches.R partitioning library
-   More error handling and documentation
-   Example of partitioning Anoles then bootstrapping
-   Bootstrapping likelihoods directly

#### References on thinking about bootstrapping model comparisons

-   [The original Neyman-Pearson
    paper](http://www.jstor.org/stable/91247 "http://www.jstor.org/stable/91247")
-   [Testing Statistical
    Hypotheses](http://www.springerlink.com/content/r12g32/?p=10d7defb56d34e0d99143df5d6000f35&pi=2 "http://www.springerlink.com/content/r12g32/?p=10d7defb56d34e0d99143df5d6000f35&pi=2")
    Text by Lehmann & Romano
-   [Permutation, Parametric and Bootstrap Tests of
    Hypotheses](http://www.springerlink.com/content/978-0-387-20279-2 "http://www.springerlink.com/content/978-0-387-20279-2")
    by Good
-   Thanks to Peter on these; [Bibsonomy
    collection](http://www.bibsonomy.org/user/peter.ralph "http://www.bibsonomy.org/user/peter.ralph")

***ouch2ape.R function needs debugging!*** Works only some of the time.
Seems to error on converting back from an ape2ouch conversion.

Computing
---------

-   Adding documentation and testing the new bootstrapping functions.
-   New functions make up the bootstrapping likelihood ratio suite:

1.  BM\_loglik
2.  my\_update
3.  LR\_bootstrap
4.  LR\_bootstrap\_all
5.  plot.LR\_boots

The function should be easy to call on a list of ouch models.

     plot(LR_bootstrap_all(model_list))

Inline documentation provides more details. Functions in this library
are contained in the likelihood\_ratio\_bootstrap.R file.

General Notes
-------------

#### Break Reading

-   [P
    values](http://www.sciencenews.org/view/feature/id/57091/title/Odds_Are%2C_Its_Wrong "http://www.sciencenews.org/view/feature/id/57091/title/Odds_Are%2C_Its_Wrong")
-   [another commenting
    forum](http://disqus.com/comments/ "http://disqus.com/comments/")
-   [on open
    science](http://ways.org/en/blogs/2010/mar/12/summary_of_the_open_science_session_at_eurodoc_2010 "http://ways.org/en/blogs/2010/mar/12/summary_of_the_open_science_session_at_eurodoc_2010")
-   [Doing vs Discussing
    Science](http://scholarlykitchen.sspnet.org/2010/02/08/science-and-web-2-0-talking-about-science-versus-doing-science/ "http://scholarlykitchen.sspnet.org/2010/02/08/science-and-web-2-0-talking-about-science-versus-doing-science/")
-   [Cameron's research
    cycle](http://docs.google.com/present/edit?id=0ASQvcnWHnwgmZGR3aHFkNmtfMjEyZHo5YjNyZzI&hl=en# "http://docs.google.com/present/edit?id=0ASQvcnWHnwgmZGR3aHFkNmtfMjEyZHo5YjNyZzI&hl=en#")
-   [Nature's position on pre-published blogging
    science](http://scienceblogs.com/geneticfuture/2009/06/nature_news_article_on_confere.php "http://scienceblogs.com/geneticfuture/2009/06/nature_news_article_on_confere.php")

