Vis I
================
2024-10-10

Import the weather data

``` r
remotes::install_github("ropensci/rnoaa", force = TRUE)
```

    ## Using GitHub PAT from the git credential store.

    ## Downloading GitHub repo ropensci/rnoaa@HEAD

    ## data.table (1.16.0 -> 1.16.2) [CRAN]

    ## Installing 1 packages: data.table

    ## 
    ## The downloaded binary packages are in
    ##  /var/folders/22/szn61jc14t71kxhr57h0tn840000gn/T//RtmpK8jhuV/downloaded_packages
    ## ── R CMD build ─────────────────────────────────────────────────────────────────
    ##      checking for file ‘/private/var/folders/22/szn61jc14t71kxhr57h0tn840000gn/T/RtmpK8jhuV/remotesfe9040e3d950/ropensci-rnoaa-95868c9/DESCRIPTION’ ...  ✔  checking for file ‘/private/var/folders/22/szn61jc14t71kxhr57h0tn840000gn/T/RtmpK8jhuV/remotesfe9040e3d950/ropensci-rnoaa-95868c9/DESCRIPTION’
    ##   ─  preparing ‘rnoaa’:
    ##    checking DESCRIPTION meta-information ...  ✔  checking DESCRIPTION meta-information
    ##   ─  checking for LF line-endings in source and make files and shell scripts
    ##   ─  checking for empty or unneeded directories
    ##    Removed empty directory ‘rnoaa/vignettes’
    ## ─  building ‘rnoaa_1.4.0.tar.gz’
    ##      
    ## 

``` r
weather_df = read_csv(file = "weather_df.csv")
```

    ## Rows: 2190 Columns: 6

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (2): name, id
    ## dbl  (3): prcp, tmax, tmin
    ## date (1): date
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
write_csv(weather_df, file = "weather_df.csv")
```

Making our first plot

``` r
ggplot(weather_df, aes(x = tmin, y = tmax)) + 
  geom_point()
```

    ## Warning: Removed 17 rows containing missing values or values outside the scale range
    ## (`geom_point()`).

![](vis_I_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

This does the same thing -

``` r
ggp_weather = 
  weather_df |>
  ggplot(aes(x = tmin, y = tmax)) + 
  geom_point()
```
