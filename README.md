
<!-- README.md is generated from README.Rmd. Please edit that file -->

# prismaread

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://www.tidyverse.org/lifecycle/#experimental)
[![Travis build
status](https://travis-ci.org/lbusett/prismaread.svg?branch=master)](https://travis-ci.org/lbusett/prismaread)
<!-- badges: end -->

The goal of prismaread is allowing to easily import PRISMA L1
hyperspectral images and convert them in a easier to use format (ENVI or
GeoTiff).

## Installation

You can install the development version from
[GitHub](https://github.com/) with:

``` r
# install.packages("remotes")
remotes::install_github("lbusett/prismaread")
```

## Usage

The function to be used is `convert_prisma`. It takes as input the full
path of a PRISMA hdf5 image, an output file name and format, and a
series of switches allowing to decide which datasets should be saved.
For example the code:

``` r
library(prismaread)

 in_file  <- "/home/lb/tmp/test/PRS_L1_STD_OFFL_20190825103112_20190825103117_0001.he5"
 out_file <- "/home/lb/tmp/test/test_1"
 out_format <- "ENVI"
 
 # Save a full image, prioritizing the SWIR spectrometer and save in EVI format
 convert_prisma(in_file    = in_file,
                out_file   = out_file,
                out_format = out_format,
                FULL = TRUE,
                PAN  = TRUE,
                CLD  = TRUE
                )
```

accesses the input file and saves both the VNIR and SWIR cubes, as well
as a full hyperspectral cube and the PAN and CLOUD images. See
[documentation](reference/convert_prisma.html) of the convert\_prisma()
function for info on available arguments.