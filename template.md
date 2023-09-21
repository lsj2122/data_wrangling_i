Simple document
================

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.3     ✔ readr     2.1.4
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.0
    ## ✔ ggplot2   3.4.3     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.2     ✔ tidyr     1.3.0
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
litters_data = read_csv(file = "./data/FAS_litters.csv")
```

    ## Rows: 49 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (2): Group, Litter Number
    ## dbl (6): GD0 weight, GD18 weight, GD of Birth, Pups born alive, Pups dead @ ...
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
names(litters_data)
```

    ## [1] "Group"             "Litter Number"     "GD0 weight"       
    ## [4] "GD18 weight"       "GD of Birth"       "Pups born alive"  
    ## [7] "Pups dead @ birth" "Pups survive"

``` r
litters_data = janitor::clean_names(litters_data)
names(litters_data)
```

    ## [1] "group"           "litter_number"   "gd0_weight"      "gd18_weight"    
    ## [5] "gd_of_birth"     "pups_born_alive" "pups_dead_birth" "pups_survive"

``` r
view(litters_data)
```

``` r
str(litters_data)
```

    ## spc_tbl_ [49 × 8] (S3: spec_tbl_df/tbl_df/tbl/data.frame)
    ##  $ group          : chr [1:49] "Con7" "Con7" "Con7" "Con7" ...
    ##  $ litter_number  : chr [1:49] "#85" "#1/2/95/2" "#5/5/3/83/3-3" "#5/4/2/95/2" ...
    ##  $ gd0_weight     : num [1:49] 19.7 27 26 28.5 NA NA NA NA NA 28.5 ...
    ##  $ gd18_weight    : num [1:49] 34.7 42 41.4 44.1 NA NA NA NA NA NA ...
    ##  $ gd_of_birth    : num [1:49] 20 19 19 19 20 20 20 20 20 20 ...
    ##  $ pups_born_alive: num [1:49] 3 8 6 5 6 6 9 9 8 8 ...
    ##  $ pups_dead_birth: num [1:49] 4 0 0 1 0 0 0 1 0 0 ...
    ##  $ pups_survive   : num [1:49] 3 7 5 4 6 4 9 8 8 8 ...
    ##  - attr(*, "spec")=
    ##   .. cols(
    ##   ..   Group = col_character(),
    ##   ..   `Litter Number` = col_character(),
    ##   ..   `GD0 weight` = col_double(),
    ##   ..   `GD18 weight` = col_double(),
    ##   ..   `GD of Birth` = col_double(),
    ##   ..   `Pups born alive` = col_double(),
    ##   ..   `Pups dead @ birth` = col_double(),
    ##   ..   `Pups survive` = col_double()
    ##   .. )
    ##  - attr(*, "problems")=<externalptr>

``` r
head(litters_data)
```

    ## # A tibble: 6 × 8
    ##   group litter_number gd0_weight gd18_weight gd_of_birth pups_born_alive
    ##   <chr> <chr>              <dbl>       <dbl>       <dbl>           <dbl>
    ## 1 Con7  #85                 19.7        34.7          20               3
    ## 2 Con7  #1/2/95/2           27          42            19               8
    ## 3 Con7  #5/5/3/83/3-3       26          41.4          19               6
    ## 4 Con7  #5/4/2/95/2         28.5        44.1          19               5
    ## 5 Con7  #4/2/95/3-3         NA          NA            20               6
    ## 6 Con7  #2/2/95/3-2         NA          NA            20               6
    ## # ℹ 2 more variables: pups_dead_birth <dbl>, pups_survive <dbl>

``` r
tail(litters_data)
```

    ## # A tibble: 6 × 8
    ##   group litter_number gd0_weight gd18_weight gd_of_birth pups_born_alive
    ##   <chr> <chr>              <dbl>       <dbl>       <dbl>           <dbl>
    ## 1 Low8  #79                 25.4        43.8          19               8
    ## 2 Low8  #100                20          39.2          20               8
    ## 3 Low8  #4/84               21.8        35.2          20               4
    ## 4 Low8  #108                25.6        47.5          20               8
    ## 5 Low8  #99                 23.5        39            20               6
    ## 6 Low8  #110                25.5        42.7          20               7
    ## # ℹ 2 more variables: pups_dead_birth <dbl>, pups_survive <dbl>
