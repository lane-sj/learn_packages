
<!-- README.md is generated from README.Rmd. Please edit that file -->

# regexcite

<!-- badges: start -->

<!-- badges: end -->

The goal of regexcite is to improve interactions with regexs. We provide
convenience functions to make some common tasks with string manipulation
easier.

## Installation

You can install the development version of regexcite from
[GitHub](https://github.com/) with:

``` r
# install.packages("pak")
pak::pak("lane-sj/learn_packages")
```

## Usage

A fairly common task when dealing with strings is the need to split a
single string into many parts. This is what `base::strplit()` and
`stringr::str_split()` do.

``` r
(x <- "alfa,bravo,charlie,delta")
#> [1] "alfa,bravo,charlie,delta"
strsplit(x, split = ",")
#> [[1]]
#> [1] "alfa"    "bravo"   "charlie" "delta"
stringr::str_split(x, pattern = ",")
#> [[1]]
#> [1] "alfa"    "bravo"   "charlie" "delta"
```

Notice how the return value is a **list** of length one, where the first
element holds the character vector of parts. Often the shape of this
output is inconvenient, i.e. ==we want the un-listed version==.

That’s exactly what `regexcite::str_split_one()` does.

``` r
library(regexcite)

str_split_one(x, pattern = ",")
#> [1] "alfa"    "bravo"   "charlie" "delta"
```
