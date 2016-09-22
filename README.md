# Resources

- [A curated list of awesome R packages and tools](https://github.com/qinwf/awesome-R)
- [The official (CRAN) R introduction](http://cran.r-project.org/doc/manuals/R-intro.html)
- http://adolfoalvarez.cl/the-hitchhikers-guide-to-the-hadleyverse/
- https://leanpub.com/hitchhikers_ggplot2
- [RtutoR package](https://mran.revolutionanalytics.com/package/RtutoR/)
- http://moderndata.plot.ly/
- http://datascienceplus.com/best-packages-for-data-manipulation-in-r/
- https://www.datacamp.com/community/blog/intro-to-statistics-with-r-series
- [Advanced R by Hadley Wickham](http://adv-r.had.co.nz/), [HN thread](https://news.ycombinator.com/item?id=9394556)
- [R packages by Hadley Wickham](r-pkgs.had.co.nz)
- http://www.cookbook-r.com
- http://www.rstudio.com/resources/cheatsheets/
- [R Weekly](https://rweekly.org/)
- [RDocumentation](http://www.rdocumentation.org/)
- [StackOverflow R questions](http://stackoverflow.com/questions/tagged/r)




## Packages

- [CRAN (official)](https://cloud.r-project.org/), [CRAN task views](https://cran.r-project.org/web/views/)
- GitHub and other places


### General in scope and important

- tidyverse (a collection of packages)
- devtools
- dplyr
- tidyr, (sort of replaces `reshape2`)
- [XLConnect](https://cran.rstudio.com/web/packages/XLConnect), [xlsx](https://cran.rstudio.com/web/packages/xlsx), readxl
- stringr
- lubridate ([r-exercises.com](http://r-exercises.com/tag/lubridate/)), related: [anytime](http://dirk.eddelbuettel.com/blog/2016/09/15/#anytime_0.0.2)



### Plots, images and visualisations

- ggplot2, [announcement of ggplot2 v. 2.0](https://blog.rstudio.org/2015/12/21/ggplot2-2-0-0/), [ggplot2 extensions](http://www.ggplot2-exts.org/)
- RColorBrewer
- plotly
- shiny
- [magick - advanced image-processing in R](https://cloud.r-project.org/web/packages/magick/vignettes/intro.html)


### Report generation

- knitr
- R Markdown
- xtable
- [Bookdown - authoring books with R Markdown](https://bookdown.org/)
- prettydoc (example: [1](http://statr.me/2016/08/creating-pretty-documents-with-the-prettydoc-package/))
- [Parameterized Reports (R Markdown from Rstudio)](http://rmarkdown.rstudio.com/developer_parameterized_reports.html)


### Some chem and phys packages

- [diffractometry](http://cran.r-project.org/web/packages/diffractometry/index.html)
- [solaR](http://cran.r-project.org/web/packages/solaR/index.html)
- [hyperSpec](https://r-forge.r-project.org/projects/hyperspec/)
- [AquaEnv](http://cran.r-project.org/web/packages/AquaEnv/index.html)
- [CHNOSZ - Chemical Thermodynamics and Activity Diagrams](http://www.chnosz.net/)
- [kinfit](http://cran.r-project.org/web/packages/kinfit/)
- [mkin](http://cran.r-project.org/web/packages/mkin/index.html)
- [quantchem](http://cran.r-project.org/web/packages/quantchem/index.html)
- [rpubchem](http://cran.r-project.org/web/packages/rpubchem/index.html)
- [seacarb](http://cran.r-project.org/web/packages/seacarb/index.html)
- [TIMP](http://timp.r-forge.r-project.org/)

[Journal of Statistical software, special issue on spectroscopy and chemometrics](https://www.jstatsoft.org/v18).

[Example of plotting XRD data with lattice](http://casoilresource.lawr.ucdavis.edu/drupal/node/516).


### On the art of judging quality of an R package

- [Good R packages (Joseph Rickert)](http://blog.revolutionanalytics.com/2016/05/good-r-packages.html)


### Submitting your own packages

- ["Submitting your first package to CRAN, my experience" (R.M. Hogervorst)](http://rmhogervorst.nl/cleancode/blog/2016/07/09/submtting-to-cran-first-experience.html)
- [submitting packages to CRAN](http://f.briatte.org/r/submitting-packages-to-cran)
- [Building and Maintaining R Packages with devtools and roxygen2, 2014](https://thepoliticalmethodologist.com/2014/08/14/building-and-maintaining-r-packages-with-devtools-and-roxygen2/)



## R courses, books or sites for beginners

- [The official (CRAN) R introduction](http://cran.r-project.org/doc/manuals/R-intro.html)
- [Guide to R Data Import/Export](https://cran.r-project.org/doc/manuals/R-data.html)
- [Start here to learn R! (collection of exercises)](http://r-exercises.com/2016/07/22/start-here-to-learn-r/)
- [Getting used to R, RStudio, and R Markdown (Chester Ismay)](https://ismayc.github.io/rbasics-book/), with [source on Github]()
- [A modern dive into data with R (Chester Ismay)](https://ismayc.github.io/moderndiver-book/), with [source on Github](https://github.com/ismayc/moderndiver-source)
- [R for Data Science, Grolemund and Wickham.](http://r4ds.had.co.nz/)
- [Data analysis with R, Udacity](https://www.udacity.com/course/data-analysis-with-r--ud651)
- [R stats, Chris Albon. (Lots of examples).](http://chrisalbon.com/#R_Stats)
- [Learning statistics on youtube](http://flavioazevedo.com/stats-and-r-blog/2016/9/13/learning-r-on-youtube)
- [R programming foundations for Life Scientists, SciLifeLab Uppsala](https://www.scilifelab.se/events/rht16/)
- [R courses (Jumping Rivers LLC, UK)](http://www.jumpingrivers.com/)
- http://r4stats.com/
- [Intro to R, Univ. of British Columbia, 2014.](https://jennybc.github.io/2014-05-12-ubc/)
- [R course at EBC, 2010 by Paolo Innocenti](http://ebc.uu.se/digitalAssets/10/10907_Intro-R-stat_2010.pdf)





## Databases or datasets (with free access)

- `nycflights13` and `ggplot2movies` (comes with `dplyr` and `ggplot2`, respectively)
- [The Materials Project](https://materialsproject.org/)
- [17 places to find datasets for data science projects](https://www.dataquest.io/blog/free-datasets-for-projects/)
- [StackLite dataset of Stack Overflow questions and tags](http://varianceexplained.org/r/stack-lite/) (with examples in R)
- [UN Comtrade Database](http://comtrade.un.org/), [R API for UN Comtrade](http://comtrade.un.org/data/Doc/api/ex/r)
- SciHub downloads (?)
- Wikipedia (very large)
- datadryad and such



## Reproducibility, replication, and scientific computing

- [How computers broke science and what we can do to fix it, The Conversation, 2015.](http://theconversation.com/how-computers-broke-science-and-what-we-can-do-to-fix-it-49938)
- [A Simple Explanation for the Replication Crisis in Science, Roger Peng, 2016.](http://simplystatistics.org/2016/08/24/replication-crisis/)
- [Standards for scientific graphic presentation](http://www.juretriglav.si/standards-for-graphic-presentation/), [HackerNews comments](https://news.ycombinator.com/item?id=8636672)
- [Good Enough Practices for Scientific Computing, Wilson et al. 2016](http://swcarpentry.github.io/good-enough-practices-in-scientific-computing/)
- [A statistical definition for reproducibility and replicability. http://dx.doi.org/10.1101/066803](http://biorxiv.org/content/early/2016/07/29/066803)
- [Why scientists must share their research code. Nature, 2016.](http://www.nature.com/news/why-scientists-must-share-their-research-code-1.20504)



## Blog posts with R code and viz examples, etc.

- [ggplot2 viz, reshape2, dplyr example (simple)](http://datascienceplus.com/the-importance-of-data-visualization/)
- [Reading RSS and Atom feeds from R (Andrew Collier)](http://www.exegetic.biz/blog/2016/08/feeder-reading-rss-atom-feeds-r/)
- [The ggthemr package -- Theme and colour your ggplot figures](http://www.shanelynn.ie/themes-and-colours-for-r-ggplots-with-ggthemr/)
- https://renkun.me/blog/2014/08/08/difference-between-magrittr-and-pipeR.html
- http://zevross.com/blog/2015/01/13/a-new-data-processing-workflow-for-r-dplyr-magrittr-tidyr-ggplot2/
- [dplyr tutorial (video)](https://www.youtube.com/watch?v=VnjujO8z4OI)
- ["Why I use ggplot2", David Robinson, 2016.](http://varianceexplained.org/r/why-I-use-ggplot2/)
- [Kernel density animation with gganimate](http://varianceexplained.org/files/bandwidth.html)
- [Animations and GIFs using ggplot2](http://rforpublichealth.blogspot.se/2014/12/animations-and-gifs-using-ggplot2.html)
- [R with parallel computing from user perspectives](http://www.parallelr.com/r-with-parallel-computing/)
- [Beeswarm Plot in R, to Show Distributions](https://flowingdata.com/2016/09/08/beeswarm-plot-in-r-to-show-distributions/)
- [Tidying computational biology models with biobroom: a case study in tidy analysis](http://varianceexplained.org/r/tidy-genomics-biobroom/)
- [forcats, a new package for working with factors](https://blog.rstudio.org/2016/08/31/forcats-0-1-0/)
- [On the elements of graphing data](http://civilstat.com/2016/01/the-elements-of-graphing-data-william-s-cleveland/)
- [Animated IRL pirate attacks in R](https://rud.is/b/2013/09/19/animated-irl-pirate-attacks-in-r/)
- [R Programming – Pitfalls to avoid (Part 1)](http://datascienceplus.com/r-programming-pitfalls-to-avoid-part-1/)
- [GoodReads: Webscraping and Text Analysis with R (Part 1)](http://datascienceplus.com/goodreads-webscraping-and-text-analysis-with-r-part-1/)
- [Animated plots using R (base graphics)](http://davetang.org/muse/2015/02/12/animated-plots-using-r/)
- [ggplot2 basics in action](http://www.joyofdata.de/blog/ggplot2-in-action/)
- [Improving R animated GIFs with tweenr](http://lenkiefer.com/2016/05/29/improving-R-animated-gifs-with-tweenr)
- [Producing animated graphs from R without having to learn any other software (slideshow presentation)](http://www.animatedgraphs.co.uk/LondonR.html)
- [Producing an animated comet plot in R (StackOverflow)](http://stackoverflow.com/questions/21018026/producing-an-animated-comet-plot-in-r)
- [Countries sport representation at Rio 2016 (swissinfo.ch)](http://www.swissinfo.ch/eng/rio-2016-_swiss-olympians---the-solo-specialists-/42349156) (an example of [interactive, Illustrator-quality graphics with R](http://blog.revolutionanalytics.com/2016/08/interactive-illustrator-quality-graphics-with-r.html), with published source code)
- [Animated greath circles on rotating 3D Earth](https://blog.snap.uaf.edu/2016/05/16/animated-great-circles-on-rotating-3d-earth-example-r-code/)
- http://r-exercises.com/2016/05/20/accessing-dataframe-objects-exercises/
- [How to install R on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-r-on-ubuntu-16-04-aeb4315b-f6f4-4c15-8a48-b12866bea23f)
- [How to reshape data in tidyr vs reshape2](http://www.milanor.net/blog/reshape-data-r-tidyr-vs-reshape2/)
- [Applying functions to lists exercises](https://www.r-bloggers.com/applying-functions-to-lists-exercises/)
- [ggtree for outbreak data](http://guangchuangyu.github.io/2016/09/ggtree-for-outbreak-data/)
- [Running a model on separate groups of data](https://drsimonj.svbtle.com/running-a-model-on-separate-groups)
- [Hunspell 2.0: High-Performance Stemmer, Tokenizer, and Spell Checker for R](http://ropensci.org/blog/technotes/2016/09/12/hunspell-release-20) ([vignette](https://cloud.r-project.org/web/packages/hunspell/vignettes/intro.html))
- [An awesome RStudio addin for selecting colours, and another for adding marginal density plots to ggplot2](http://deanattali.com/blog/colourpicker-ggmarginal-gadgets/)



## Examples of why Excel et al. is bad (and open-source software is good for everyone)

- [Washington Post: An alarming number of scientific papers contain Excel errors](https://www.washingtonpost.com/news/wonk/wp/2016/08/26/an-alarming-number-of-scientific-papers-contain-excel-errors/), [discussion on HackerNews](https://news.ycombinator.com/item?id=12370605), [discussion on Reddit](https://www.reddit.com/r/programming/comments/4zrp2w/an_alarming_number_of_scientific_papers_contain/)
- [The hidden benefits of open-source software, Rob J. Hyndman, 2015](http://robjhyndman.com/hyndsight/oss-benefits/)



## R conferences (including content from conferences)

- useR! 2016 tutorials, [part 1](http://blog.revolutionanalytics.com/2016/06/the-user-2016-tutorials.html) and [part 2](http://blog.revolutionanalytics.com/2016/07/user-2016-tutorials-part-2-.html)
- [EARL 2016](http://www.mango-solutions.com/wp/2016/08/10-reasons-why-you-cant-miss-this-years-earl-conference-in-london/)
- [Videos](https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016?sort=viewed&direction=asc#tab_sortBy_viewed)
- [Michael Levy - Teaching R to 200 people in a week](https://channel9.msdn.com/Events/useR-international-R-User-conference/useR2016/Teaching-R-to-200-people-in-a-week)




## User groups, associations, societies, etc.

- [Stockholm R useR group (SRUG)](https://www.meetup.com/StockholmR/)


## Related tools and software (including version control)

- [Practical version control for scientists](http://htmlpreview.github.io/?https://github.com/BernhardKonrad/2014-02-22-SFU/blob/gh-pages/BK-slides/git-intro.slides.html)
- [Happy Git and Github for the useR](http://happygitwithr.com/)
- [Using Git with Rstudio, Jenny Bryan](https://jennybc.github.io/2014-05-12-ubc/ubc-r/session03_git.html)
- [Commit Often, Perfect Later, Publish Once: Git Best Practices](https://sethrobertson.github.io/GitBestPractices/)
- [Why you need version control](http://ellisp.github.io/blog/2016/09/16/version-control)
- [Git and GitHub, Wickham](http://r-pkgs.had.co.nz/git.html)
- [Learn enough command line to be dangerous (tutorial by Michael Hartl)](https://www.learnenough.com/command-line-tutorial), [HN comments](https://news.ycombinator.com/item?id=10245033)
- [The art of command line](https://github.com/jlevy/the-art-of-command-line), [HN comments](https://news.ycombinator.com/item?id=9720813)




## Course schedule and organisers

| Date | Time | Room |
| :--- | :--: | :--- |
| 2016-09-19 | 14:00 - 17:00 | ITC 1145, Polacksbacken |
| 2016-09-20 | 14:00 - 17:00 | ITC 2345, Polacksbacken |
| 2016-09-21 | 14:00 - 17:00 | 80115, Ångström |
| 2016-09-22 | 14:00 - 17:00 | ITC 2345, Polacksbacken |


This course was organised and presented by:

- Delphine Lebrun, delphine.lebrun@angstrom.uu.se
- Taha Ahmed, taha@chepec.se
- Matt Lacey, matt@lacey.se
