--- 
title: "Museum of Spatial Transcriptomics"
author: 
  - Lambda Moses, dlu2@caltech.edu
  - Lior Pachter, lpachter@caltech.edu
date: "2021-04-29"
site: bookdown::bookdown_site
documentclass: book
bibliography: "museumst.bib"
#csl: nature-genetics.csl
link-citations: yes
description: "Museum of Spatial Transcriptomics"
github-repo: "pachterlab/museumst_catalogue"
---

# Preface {-}

This supplement to the paper Museum of Spatial Transcriptomics and the associated [database of spatial transcriptomics literature](https://docs.google.com/spreadsheets/d/1sJDb9B7AtYmfKv4-m8XR7uc3XXw_k4kGSout8cqZ8bY/edit?usp=sharing) is inspired by museum catalogs that provide insight and detail to further understanding of the exhibits. The results presented are based on code that can be run interactively on [RStudio Cloud](https://rstudio.cloud/project/2492054). We present key analyses of metadata curated for the database, and provide further analyses and results beyond what could be included here in the `more_analyses` directory of this repository. The markdown that generates this text is on GitHub, and is version controlled so that its development can be tracked now and in the future. Please notify us of errors, omissions, or other suggestions via submission of issues on GitHub: https://github.com/pachterlab/LP_2021

This document is built with the `bookdown` package from a collection of R Markdown files. How some of figures look depends on parameters that can be changed, such as size of bins when binning number of publications in time to show a trend. The source code is on [RStudio Cloud](https://rstudio.cloud/project/2492054). The dependencies are pre-installed in the RStudio Cloud project. By default, when the database is queried by code, the most up to date version is used, which can be newer than the rendered static version on github.io. To build the document in RStudio Cloud (i.e., both the web page `gitbook` version and a PDF), run this in the R console:


```r
bookdown::render_book("supplement/index.Rmd", output_format = "bookdown::gitbook")
```

If you are cloning this repo into a fresh RStudio Cloud project or a fresh machine, install the packages required to build the book as follows:

First install `remotes` with `install.packages("remotes")`. Then use `remotes:install_deps(dependencies = TRUE)` to install all required packages from CRAN, Bioconductor, and GitHub. So in short,


```r
install.packages("remotes")
remotes::install_deps(dependencies = TRUE)
```

Because many packages are installed, the installation can be sped up with the argument `Ncpus` in `install_deps()` to specify the number of CPU cores to use to install packages in parallel, such as `Ncpus = 2L` for 2 cores. The free plan of RStudio Cloud only has 1 core, but this argument can be used when multiple cores are available.
