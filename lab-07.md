Lab 07 - Conveying the right message through visualisation
================
Tsion

### Load packages and data

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.2.0     ✔ readr     2.2.0
    ## ✔ forcats   1.0.1     ✔ stringr   1.6.0
    ## ✔ ggplot2   4.0.2     ✔ tibble    3.3.1
    ## ✔ lubridate 1.9.5     ✔ tidyr     1.3.2
    ## ✔ purrr     1.2.1     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
library(scales)
```

    ## 
    ## Attaching package: 'scales'
    ## 
    ## The following object is masked from 'package:purrr':
    ## 
    ##     discard
    ## 
    ## The following object is masked from 'package:readr':
    ## 
    ##     col_factor

``` r
library(lubridate)

# library(zoo) didn't work for me so I tried installing it in the console instead

df <- read_csv("kansas_grouped_rolling_avg.csv")
```

    ## Rows: 46 Columns: 3
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (1): mask_mandate
    ## dbl  (1): rolling_avg
    ## date (1): date
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

## Part 1: The Problem — Where’s the Data?

### Exercise 1

I think the original visualization appears to use data from **Kansas**
during the summer of 2020. The title says it is showing the **Kansas
COVID-19 7-day rolling average of daily cases per 100K population**.

It compares two groups: **counties with mask mandates** and **counties
without mask mandates**. I believe the phrase “per 100K population”
means the case counts were adjusted for population size, so counties or
groups with different populations can be compared more fairly.

### Exercise 2

I think the MMWR report gives two important details that were missing or
not obvious in the original visualization.

It names the 24 Kansas counties that had mask mandates in effect by July
3, 2020. These were:

Allen, Atchison, Bourbon, Crawford, Dickinson, Douglas, Franklin, Geary,
Gove, Harvey, Jewell, Johnson, Mitchell, Montgomery, Morris, Pratt,
Reno, Republic, Saline, Scott, Sedgwick, Shawnee, Stanton, and
Wyandotte.

It also says the COVID-19 case data came from USAFacts, which provides
county-level COVID-19 data. This is important because it lets us
download the raw county-level case data and reconstruct the
visualization ourselves.
