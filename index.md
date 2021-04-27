--- 
title: "Museum of Spatial Transcriptomics"
author: 
  - Lambda Moses, dlu2@caltech.edu
  - Lior Pachter, lpachter@caltech.edu
date: "2021-04-27"
site: bookdown::bookdown_site
documentclass: book
bibliography: "museumst.bib"
#csl: nature-genetics.csl
link-citations: yes
description: "Museum of Spatial Transcriptomics"
github-repo: "pachterlab/museumst_catalogue"
---

# Preface {-}

This book is the much more detailed supplement of the paper Museum of Spatial Transcriptomics and is related to our [database of spatial transcriptomics literature](https://docs.google.com/spreadsheets/d/1sJDb9B7AtYmfKv4-m8XR7uc3XXw_k4kGSout8cqZ8bY/edit?usp=sharing) akin to how a museum exhibition catalog relates to the exhibits. Code in this book can be run interactively on [RStudio Cloud](https://rstudio.cloud/project/2492054). This book presents analyses of metadata of the database, but more analyses can be found in the `more_analyses` directory of this repo and can be run on RStudio Cloud. As the field of spatial transcriptomics is rapidly evolving, this book will be continuously updated to reflect the current state of the field. As this book is on GitHub, it is version controlled and historical versions can be viewed. If you find errors or have suggestions, please submit an issue on GitHub: https://github.com/pachterlab/LP_2021

This book is built with the `bookdown` package from a collection of R Markdown files. How some figures look depends on parameters that can be changed, such as size of bins when binning number of publications in time to show a trend. The source code of this book is on [RStudio Cloud](https://rstudio.cloud/project/2492054). The dependencies are pre-installed in the RStudio Cloud project. By default, when the database is queried by code in this book, the most up to date version is used, which can be newer than the rendered static version of the book on github.io. To build the book in RStudio Cloud (will build both the web page `gitbook`), run this in the R console:


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