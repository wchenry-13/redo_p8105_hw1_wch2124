redo_p8105_hw1_wch2124
================
2023-09-21

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
library(moderndive)
data("early_january_weather")
nrow(early_january_weather)
```

    ## [1] 358

``` r
ncol(early_january_weather)
```

    ## [1] 15

``` r
mean(pull(early_january_weather, temp))
```

    ## [1] 39.58212

The variables are the characteristics of the weather in January in 2013,
including hour, temperature, humidity, wind, precipitation, and
visibility. It has 358 rows and 15 columns, with a mean temperature of
39.58212.

``` r
ggplot(early_january_weather, aes(x = time_hour, y = temp, color = humid)) + geom_point(color='darkblue')
```

![](hw1_files/figure-gfm/graph-1.png)<!-- -->

``` r
ggsave("p8105_hw1_wch2124.pdf")
```

    ## Saving 7 x 5 in image

The scatter plot shows that temperature overall increases over the
course of the month of January.

``` r
my_df = 
  tibble(
  vec_numeric = rnorm(10),
  vec_char = c(1, 2, 3, 4, 5, 6, 7, 8, 9, 10),
  vec_factor = factor(c("LOW", "HIGH", "LOW", "MEDIUM", "LOW","MEDIUM", "LOW", "MEDIUM", "MEDIUM", "LOW" ))
  
)
my_df
```

    ## # A tibble: 10 × 3
    ##    vec_numeric vec_char vec_factor
    ##          <dbl>    <dbl> <fct>     
    ##  1       1.77         1 LOW       
    ##  2      -0.988        2 HIGH      
    ##  3      -0.710        3 LOW       
    ##  4       0.938        4 MEDIUM    
    ##  5      -1.42         5 LOW       
    ##  6      -0.609        6 MEDIUM    
    ##  7      -0.805        7 LOW       
    ##  8       0.710        8 MEDIUM    
    ##  9       0.748        9 MEDIUM    
    ## 10      -1.16        10 LOW
