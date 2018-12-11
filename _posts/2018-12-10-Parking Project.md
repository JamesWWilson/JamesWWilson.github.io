Project Summary
---------------

In this document we will analyize parking tickets in Westwood CA.

``` r
## Parking Project 

#I. Setup -----

#Remove Objects
rm(list = ls())

#Clear Memory
gc(reset = TRUE)
```

    ##          used (Mb) gc trigger (Mb) limit (Mb) max used (Mb)
    ## Ncells 453454 24.3     980285 52.4         NA   453454 24.3
    ## Vcells 884037  6.8    8388608 64.0      16384   884037  6.8

``` r
#Set Working Directory
setwd("/Users/JamesW/Desktop/Personal Projects/Data Science Projects/Parking Project")

#Load Packages
require(stringr)
```

    ## Loading required package: stringr

``` r
require(tidyverse)
```

    ## Loading required package: tidyverse

    ## ── Attaching packages ──────────────────────────────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.1.0     ✔ readr   1.2.1
    ## ✔ tibble  1.4.2     ✔ purrr   0.2.5
    ## ✔ tidyr   0.8.2     ✔ dplyr   0.7.8
    ## ✔ ggplot2 3.1.0     ✔ forcats 0.3.0

    ## ── Conflicts ─────────────────────────────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
require(dplyr)      #Data frame functions
require(data.table)
```

    ## Loading required package: data.table

    ## 
    ## Attaching package: 'data.table'

    ## The following objects are masked from 'package:dplyr':
    ## 
    ##     between, first, last

    ## The following object is masked from 'package:purrr':
    ## 
    ##     transpose

``` r
require(dtplyr)
```

    ## Loading required package: dtplyr

``` r
require(stringi)
```

    ## Loading required package: stringi

``` r
require(ggplot2)        #Graphics
require(lubridate)
```

    ## Loading required package: lubridate

    ## 
    ## Attaching package: 'lubridate'

    ## The following objects are masked from 'package:data.table':
    ## 
    ##     hour, isoweek, mday, minute, month, quarter, second, wday,
    ##     week, yday, year

    ## The following object is masked from 'package:base':
    ## 
    ##     date

``` r
require(readxl)
```

    ## Loading required package: readxl

``` r
require(reshape2)
```

    ## Loading required package: reshape2

    ## 
    ## Attaching package: 'reshape2'

    ## The following objects are masked from 'package:data.table':
    ## 
    ##     dcast, melt

    ## The following object is masked from 'package:tidyr':
    ## 
    ##     smiths

``` r
require(rgdal)
```

    ## Loading required package: rgdal

    ## Loading required package: sp

    ## rgdal: version: 1.3-6, (SVN revision 773)
    ##  Geospatial Data Abstraction Library extensions to R successfully loaded
    ##  Loaded GDAL runtime: GDAL 2.1.3, released 2017/20/01
    ##  Path to GDAL shared files: /Library/Frameworks/R.framework/Versions/3.5/Resources/library/rgdal/gdal
    ##  GDAL binary built with GEOS: FALSE 
    ##  Loaded PROJ.4 runtime: Rel. 4.9.3, 15 August 2016, [PJ_VERSION: 493]
    ##  Path to PROJ.4 shared files: /Library/Frameworks/R.framework/Versions/3.5/Resources/library/rgdal/proj
    ##  Linking to sp version: 1.3-1

``` r
#load("/Users/JamesW/Desktop/R Programming/Functions/nci_cleanDT/1.0/nci_cleanDT.r")
```

``` r
# load data ------
parkingData <- read_csv(
  "Parking_Citations.csv",
  col_types = cols(.default = "c"),
  na = c("", " ", "NA")
) %>%
  # convert all variable names to lower
  rename_all(.funs = ~ tolower(.)) 

#parkingData <- parkingData %>% sample_n(1000)
# sum(is.na(parkingData$longitude)) # missing 511 dates 
# parkingData[is.na(parkingData$longitude),]

parkingData <- parkingData %>% filter(!(is.na(parkingData$longitude)),
                                      !(is.na(parkingData$latitude)))
```
