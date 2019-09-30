HW3
================
Stephen Powers
9/26/2019

## Problem 1

``` r
library(readxl)
library(tidyverse)
```

    ## ── Attaching packages ───────────────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.2.1     ✔ purrr   0.3.2
    ## ✔ tibble  2.1.3     ✔ dplyr   0.8.3
    ## ✔ tidyr   1.0.0     ✔ stringr 1.4.0
    ## ✔ readr   1.3.1     ✔ forcats 0.4.0

    ## ── Conflicts ──────────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

Importing and Cleaning
Data

``` r
TrashWheel = read_excel(path = "./data/HealthyHarborWaterWheelTotals2018-7-28.xlsx",
                        sheet = 1) %>%
  janitor::clean_names() %>%
  drop_na (dumpster) %>%
  mutate(sports_balls = round(sports_balls, digits = 0)) %>%
  mutate(sports_balls = as.integer(sports_balls))
```

    ## New names:
    ## * `` -> ...15
