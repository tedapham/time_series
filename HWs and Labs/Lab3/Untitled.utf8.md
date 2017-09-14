---
title: "Lab3_tp_v1"
output: pdf_document
---




```r
library(Hmisc)
```

```
## Loading required package: lattice
```

```
## Loading required package: survival
```

```
## Loading required package: Formula
```

```
## Loading required package: ggplot2
```

```
## 
## Attaching package: 'Hmisc'
```

```
## The following objects are masked from 'package:base':
## 
##     format.pval, round.POSIXt, trunc.POSIXt, units
```

```r
library(forecast)

# Set working directory, change to appropriate 
path <- "/Users/tedpham/Documents/W271 Time Series/HWs and Labs/Lab3"
setwd(path)
df <- read.csv("UNRATENSA.csv", stringsAsFactors = FALSE)
summary(df)
```

```
##      DATE             UNRATENSA     
##  Length:834         Min.   : 2.400  
##  Class :character   1st Qu.: 4.700  
##  Mode  :character   Median : 5.600  
##                     Mean   : 5.801  
##                     3rd Qu.: 6.900  
##                     Max.   :11.400
```

```r
describe(df)
```

```
## df 
## 
##  2  Variables      834  Observations
## ---------------------------------------------------------------------------
## DATE 
##        n  missing distinct 
##      834        0      834 
## 
## lowest : 1948-01-01 1948-02-01 1948-03-01 1948-04-01 1948-05-01
## highest: 2017-02-01 2017-03-01 2017-04-01 2017-05-01 2017-06-01
## ---------------------------------------------------------------------------
## UNRATENSA 
##        n  missing distinct     Info     Mean      Gmd      .05      .10 
##      834        0       84        1    5.801    1.881      3.3      3.8 
##      .25      .50      .75      .90      .95 
##      4.7      5.6      6.9      8.1      9.1 
## 
## lowest :  2.4  2.5  2.6  2.7  2.8, highest: 10.5 10.6 10.8 11.3 11.4
## ---------------------------------------------------------------------------
```

```r
print(df[which.min(df$UNRATENSA),])
```

```
##          DATE UNRATENSA
## 58 1952-10-01       2.4
```

```r
print(df[which.max(df$UNRATENSA),])
```

```
##           DATE UNRATENSA
## 421 1983-01-01      11.4
```

The unemployment rate data spans from January 1948 to June 2017, accounting for 834 months. There was no missing value in the data.
The highest and lowest rate are within reasonably range [2.4,11.4] corresponding to 1952-10-01
and 1983-01-01
