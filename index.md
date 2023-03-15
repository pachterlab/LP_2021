--- 
title: "Museum of Spatial Transcriptomics"
author: 
  - Lambda Moses
  - Lior Pachter
date: "2023-03-15"
site: bookdown::bookdown_site
documentclass: book
bibliography: "museumst.bib"
#csl: nature-genetics.csl
link-citations: yes
description: "Museum of Spatial Transcriptomics"
github-repo: "pachterlab/LP_2021"
---

# Preface {-} 

This supplement to [the paper Museum of Spatial Transcriptomics](https://www.nature.com/articles/s41592-022-01409-2) and the associated [database of spatial transcriptomics literature](https://docs.google.com/spreadsheets/d/1sJDb9B7AtYmfKv4-m8XR7uc3XXw_k4kGSout8cqZ8bY/edit?usp=sharing) is inspired by museum catalogs that provide insight and detail to further understanding of the exhibits. The results presented are based on code that can be run interactively on [RStudio Cloud](https://rstudio.cloud/project/2492054). We present key analyses of metadata curated for the database, and provide further analyses and results beyond what could be included here in the `more_analyses` directory of this repository. The markdown that generates this text is on GitHub, and is version controlled so that its development can be tracked now and in the future. Please notify us of errors, omissions, or other suggestions via submission of issues on GitHub: https://github.com/pachterlab/LP_2021 To submit new entries to the database, please fill out this [Google Form](https://forms.gle/HjQD9x6AMjR7C62SA). If the text in some figures are too small to read, then right click on the figure to open in a new tab to zoom in.

## Quick stats














As of 2023-03-15, this database contains:

* 1229 current era publications, 780 of which are for data collection and 501 are for data analysis (see Chapter 1 for definition of prequel and current eras)
* 270 prequel era publications
* Current era publications from 441 institutions[^1] in 255 cities in 35 countries
* 399 current era data analysis software packages whose source code is available online

## Running the code

This document is built with the `bookdown` package from a collection of R Markdown files. How some of figures look depends on parameters that can be changed, such as size of bins when binning number of publications in time to show a trend. The source code is on [RStudio Cloud](https://rstudio.cloud/project/2492054). The dependencies are pre-installed in the RStudio Cloud project. By default, when the database is queried by code, the most up to date version is used, which can be newer than the rendered static version on github.io. To build the document in RStudio Cloud, run this in the R console:


```r
bookdown::render_book("index.Rmd", output_format = "bookdown::bs4_book")
```

If you are cloning this repo into a fresh RStudio Cloud project or a fresh machine, install the packages required to build the book as follows:

First install `remotes` with `install.packages("remotes")`. Then use `remotes:install_deps(dependencies = TRUE)` to install all required packages from CRAN, Bioconductor, and GitHub. So in short,


```r
install.packages("remotes")
remotes::install_deps(dependencies = TRUE)
```

Because many packages are installed, the installation can be sped up with the argument `Ncpus` in `install_deps()` to specify the number of CPU cores to use to install packages in parallel, such as `Ncpus = 2L` for 2 cores. The free plan of RStudio Cloud only has 1 core, but this argument can be used when multiple cores are available.

By default, the most up to date version of the database is downloaded for analyses in this book. However, as the `museumst` R package written for these analyses contains a cached version of the database, historical versions of the database can be viewed by installing older versions of `museumst` and setting `update = FALSE` when calling `museumst::read_metadata()` when running code from this book on RStudio Cloud or your computer. Older versions of `museumst` can be installed with


```r
remotes::install_github("pachterlab/museumst", ref = "v0.0.0.9016")
```

where `ref` refers to a release. Release history of `museumst` can be seen [here](https://github.com/pachterlab/museumst/releases). Documentation of `museumst` can be seen [here](https://pachterlab.github.io/museumst/).

[^1]: Caveat: definition of "institution" is more complicated. While it usually means a university or company, whether named institutions, schools, and hospitals affiliated with a university count as institutions distinct from that university is somewhat inconsistent within this database. Usually those are considered separate institutions if they reside in a different city from the rest of the university or are sometimes listed independently from the university. However, what counts as a city is also somewhat complicated as different countries have different administrative structures.
