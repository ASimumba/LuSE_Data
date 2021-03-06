Lusaka Securities Exchange Overview
================
Aaron Simumba
2017-03-12

``` r
## loading the required packages
library(xts)
library(PerformanceAnalytics)
library(dygraphs)
```

``` r
# loading the data

# The first two data sets are the ALSI excluding ZCCCM_IH
LASI_yearly <- read.csv("LUSE_yearly1.csv", header = TRUE) # End of the year price of the Lusaka Securities Exchange All Share  (LASI)

LASI_monthly <- read.csv("LUSE_monthly1.csv", header = TRUE)

# Excluding ZCCM_IH
LASI_yearly_zccm <- read.csv("LUSE_yearly2.csv", header = TRUE)

LASI_monthly_zccm <- read.csv("LUSE_monthly2.csv", header = TRUE)
```

``` r
# Since the Year and the ALSI have been entered as factors rather than as date and numeric classes respectively, we have to convert them to their appropriate class to be able to do the computations we desire.
# convert the data frame to an xts
LASI_monthly <- xts(x = LASI_monthly[,-1], order.by = as.Date(LASI_monthly[,1]))

LASI_monthly_zccm <- xts(x = LASI_monthly_zccm[,-1], order.by = as.Date(LASI_monthly_zccm[,1]))

LASI_yearly <- xts(x = LASI_yearly[,-1], order.by = as.Date(LASI_yearly[,1]))

LASI_yearly_zccm <- xts(x = LASI_yearly_zccm[,-1], order.by = as.Date(LASI_yearly_zccm[,1]))
```

``` r
# quick plots to visualise the data

plot(LASI_monthly$Return, xlab=" Period", ylab="Return",main="The LuSE LASI Monthly Returns For the Period 2005-2014
     (excl. ZCCM-IH)",cex.main =1, font.main=2)
```

![](README_files/figure-markdown_github/unnamed-chunk-4-1.png)

``` r
plot(LASI_monthly_zccm$Return,xlab=" Period", ylab="Return", main="The LuSE LASI Monthly Returns For the Period 2005-2014 
     (incl. ZCCM-IH)",cex.main =1, font.main=2)
```

![](README_files/figure-markdown_github/unnamed-chunk-4-2.png)

``` r
plot(LASI_yearly$Return,xlab=" Period", ylab="Return", main="The LuSE LASI yearly Returns For the Period 1997-2014 
     (excl. ZCCM-IH)",cex.main =1, font.main=2)
```

![](README_files/figure-markdown_github/unnamed-chunk-4-3.png)

``` r
plot(LASI_yearly_zccm$Return, xlab=" Period", ylab="Return", main="The LuSE LASI yearly Returns For the Period 1997-2014 
     (incl. ZCCM-IH)",cex.main =1, font.main=2)
```

![](README_files/figure-markdown_github/unnamed-chunk-4-4.png)

LuSE\_Data
----------

Lusaka Securities Exchange market data and analysis code.

The data covers the years 1997 to December 2014.

The link to the blog post : <http://aaronsimumba.blogspot.com/2017/01/whats-in-numbers-look-at-lusaka.html>
