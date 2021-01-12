---
title: "Visualize your data"
teaching: 20
exercises: 20
questions:
- "How to visualise my data?"

objectives:
- "Visualise your data using xxx"
keypoints:
- ""
- ""
- ""

---

## Objects 

Two ways to run your data: 
1. Select the line, then click run on top right in `Editor` 
2. Select the line, then press control+command+enter

Information can be stored in user defined objects, in multiple forms:

* c(): a string of value 
* matrix(): a two dimensional matrix in one format 
* data.frame(): a two dimensional matrix where each column can be a different format
* list():

```diff

-c(): a string of value'

xc <- 1:10
xc
##  [1]  1  2  3  4  5  6  7  8  9 10

xc <- c(1,2,3,4,5,6,7,8,9,10)
xc
##  [1]  1  2  3  4  5  6  7  8  9 10

```diff

-c(): a matrix'

xm <- matrix(1:100, nrow = 10, ncol = 10, byrow = T)
xm

##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1    2    3    4    5    6    7    8    9    10
##  [2,]   11   12   13   14   15   16   17   18   19    20
##  [3,]   21   22   23   24   25   26   27   28   29    30
##  [4,]   31   32   33   34   35   36   37   38   39    40
##  [5,]   41   42   43   44   45   46   47   48   49    50
##  [6,]   51   52   53   54   55   56   57   58   59    60
##  [7,]   61   62   63   64   65   66   67   68   69    70
##  [8,]   71   72   73   74   75   76   77   78   79    80
##  [9,]   81   82   83   84   85   86   87   88   89    90
## [10,]   91   92   93   94   95   96   97   98   99   100

xm <- matrix(1:100, nrow = 10, ncol = 10, byrow = F)
xm

##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1   11   21   31   41   51   61   71   81    91
##  [2,]    2   12   22   32   42   52   62   72   82    92
##  [3,]    3   13   23   33   43   53   63   73   83    93
##  [4,]    4   14   24   34   44   54   64   74   84    94
##  [5,]    5   15   25   35   45   55   65   75   85    95
##  [6,]    6   16   26   36   46   56   66   76   86    96
##  [7,]    7   17   27   37   47   57   67   77   87    97
##  [8,]    8   18   28   38   48   58   68   78   88    98
##  [9,]    9   19   29   39   49   59   69   79   89    99
## [10,]   10   20   30   40   50   60   70   80   90   100

-c(): A data frame'

xd <- data.frame(
  x1 = c("aa","bb","cc","dd","ee",
         "ff","gg","hh","ii","jj"),
  x2 = 1:10,
  x3 = c(1,1,1,1,1,2,2,2,3,3),
  x4 = rep(c(1,2), times = 5),
  x5 = rep(1:5, times = 2),
  x6 = rep(1:5, each = 2),
  x7 = seq(5, 50, by = 5),
  x8 = log10(1:10),
  x9 = (1:10)^3,
  x10 = c(T,T,T,F,F,T,T,F,F,F)
)
xd

##    x1 x2 x3 x4 x5 x6 x7        x8   x9   x10
## 1  aa  1  1  1  1  1  5 0.0000000    1  TRUE
## 2  bb  2  1  2  2  1 10 0.3010300    8  TRUE
## 3  cc  3  1  1  3  2 15 0.4771213   27  TRUE
## 4  dd  4  1  2  4  2 20 0.6020600   64 FALSE
## 5  ee  5  1  1  5  3 25 0.6989700  125 FALSE
## 6  ff  6  2  2  1  3 30 0.7781513  216  TRUE
## 7  gg  7  2  1  2  4 35 0.8450980  343  TRUE
## 8  hh  8  2  2  3  4 40 0.9030900  512 FALSE
## 9  ii  9  3  1  4  5 45 0.9542425  729 FALSE
## 10 jj 10  3  2  5  5 50 1.0000000 1000 FALSE

-c(): A list'

xl <- list(xc, xm, xd)
xl[[1]]

##  [1]  1  2  3  4  5  6  7  8  9 10

xl[[2]]
##       [,1] [,2] [,3] [,4] [,5] [,6] [,7] [,8] [,9] [,10]
##  [1,]    1   11   21   31   41   51   61   71   81    91
##  [2,]    2   12   22   32   42   52   62   72   82    92
##  [3,]    3   13   23   33   43   53   63   73   83    93
##  [4,]    4   14   24   34   44   54   64   74   84    94
##  [5,]    5   15   25   35   45   55   65   75   85    95
##  [6,]    6   16   26   36   46   56   66   76   86    96
##  [7,]    7   17   27   37   47   57   67   77   87    97
##  [8,]    8   18   28   38   48   58   68   78   88    98
##  [9,]    9   19   29   39   49   59   69   79   89    99
## [10,]   10   20   30   40   50   60   70   80   90   100

xl[[3]]
##    x1 x2 x3 x4 x5 x6 x7        x8   x9   x10
## 1  aa  1  1  1  1  1  5 0.0000000    1  TRUE
## 2  bb  2  1  2  2  1 10 0.3010300    8  TRUE
## 3  cc  3  1  1  3  2 15 0.4771213   27  TRUE
## 4  dd  4  1  2  4  2 20 0.6020600   64 FALSE
## 5  ee  5  1  1  5  3 25 0.6989700  125 FALSE
## 6  ff  6  2  2  1  3 30 0.7781513  216  TRUE
## 7  gg  7  2  1  2  4 35 0.8450980  343  TRUE
## 8  hh  8  2  2  3  4 40 0.9030900  512 FALSE
## 9  ii  9  3  1  4  5 45 0.9542425  729 FALSE
## 10 jj 10  3  2  5  5 50 1.0000000 1000 FALSE

Selecting data


xc[5] # 5th element in xc

## [1] 5

xd$x3[5] # 5th element in col "x3"

## [1] 1

xd[5,"x3"] # row 5, col "x3"

## [1] 1

xd$x3 # all of col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3

xd[,"x3"] # all rows, col "x3"
##  [1] 1 1 1 1 1 2 2 2 3 3

xd[3,] # row 3, all cols
##   x1 x2 x3 x4 x5 x6 x7        x8 x9  x10
## 3 cc  3  1  1  3  2 15 0.4771213 27 TRUE

xd[c(2,4),c("x4","x5")] # rows 2 & 4, cols "x4" & "x5"
##   x4 x5
## 2  2  2
## 4  2  4

xl[[3]]$x1 # 3rd object in the list, col "x1
##  [1] "aa" "bb" "cc" "dd" "ee" "ff" "gg" "hh" "ii" "jj"
```
## Data Formats

Data can also be saved in many formats:
* numeric
* integer
* character
* factor
* logical

```
xd$x3 <- as.character(xd$x3)
xd$x3
##  [1] "1" "1" "1" "1" "1" "2" "2" "2" "3" "3"

xd$x3 <- as.numeric(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3

xd$x3 <- as.factor(xd$x3)
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 1 2 3

xd$x3 <- factor(xd$x3, levels = c("3","2","1"))
xd$x3
##  [1] 1 1 1 1 1 2 2 2 3 3
## Levels: 3 2 1

xd$x10
##  [1]  TRUE  TRUE  TRUE FALSE FALSE  TRUE  TRUE FALSE FALSE FALSE

as.numeric(xd$x10) # TRUE = 1, FALSE = 0
##  [1] 1 1 1 0 0 1 1 0 0 0

sum(xd$x10)
## [1] 5
```

Internal structure of an object can be checked with `str()`

```
str(xc) # c()
##  num [1:10] 1 2 3 4 5 6 7 8 9 10

str(xm) # matrix()
##  int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...

str(xd) # data.frame()
## 'data.frame':    10 obs. of  10 variables:
##  $ x1 : chr  "aa" "bb" "cc" "dd" ...
##  $ x2 : int  1 2 3 4 5 6 7 8 9 10
##  $ x3 : Factor w/ 3 levels "3","2","1": 3 3 3 3 3 2 2 2 1 1
##  $ x4 : num  1 2 1 2 1 2 1 2 1 2
##  $ x5 : int  1 2 3 4 5 1 2 3 4 5
##  $ x6 : int  1 1 2 2 3 3 4 4 5 5
##  $ x7 : num  5 10 15 20 25 30 35 40 45 50
##  $ x8 : num  0 0.301 0.477 0.602 0.699 ...
##  $ x9 : num  1 8 27 64 125 216 343 512 729 1000
##  $ x10: logi  TRUE TRUE TRUE FALSE FALSE TRUE ...

str(xl) # list()
## List of 3
##  $ : num [1:10] 1 2 3 4 5 6 7 8 9 10
##  $ : int [1:10, 1:10] 1 2 3 4 5 6 7 8 9 10 ...
##  $ :'data.frame':    10 obs. of  10 variables:
##   ..$ x1 : chr [1:10] "aa" "bb" "cc" "dd" ...
##   ..$ x2 : int [1:10] 1 2 3 4 5 6 7 8 9 10
##   ..$ x3 : num [1:10] 1 1 1 1 1 2 2 2 3 3
##   ..$ x4 : num [1:10] 1 2 1 2 1 2 1 2 1 2
##   ..$ x5 : int [1:10] 1 2 3 4 5 1 2 3 4 5
##   ..$ x6 : int [1:10] 1 1 2 2 3 3 4 4 5 5
##   ..$ x7 : num [1:10] 5 10 15 20 25 30 35 40 45 50
##   ..$ x8 : num [1:10] 0 0.301 0.477 0.602 0.699 ...
##   ..$ x9 : num [1:10] 1 8 27 64 125 216 343 512 729 1000
##   ..$ x10: logi [1:10] TRUE TRUE TRUE FALSE FALSE TRUE ...
```
## Packages
Additional libraries can be installed and loaded for use.

```
install.packages("scales")
```
```
library(scales)
xx <- data.frame(Values = 1:10)
xx$Rescaled <- rescale(x = xx$Values, to = c(1,30))
xx
```

```
##    Values  Rescaled
## 1       1  1.000000
## 2       2  4.222222
## 3       3  7.444444
## 4       4 10.666667
## 5       5 13.888889
## 6       6 17.111111
## 7       7 20.333333
## 8       8 23.555556
## 9       9 26.777778
## 10     10 30.000000
```

## Data Wrangling
[R for Data Science] (https://r4ds.had.co.nz/)

```
xx <- data.frame(Group = c("X","X","Y","Y","Y","X","X","X","Y","Y"),
                 Data1 = 1:10, 
                 Data2 = seq(10, 100, by = 10))
xx$NewData1 <- xx$Data1 + xx$Data2
xx$NewData2 <- xx$Data1 * 1000
xx
```

```
##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      X     6    60       66     6000
## 7      X     7    70       77     7000
## 8      X     8    80       88     8000
## 9      Y     9    90       99     9000
## 10     Y    10   100      110    10000
```
```
xx$Data1 < 5 # which are less than 5
##  [1]  TRUE  TRUE  TRUE  TRUE FALSE FALSE FALSE FALSE FALSE FALSE
```
```
xx[xx$Data1 < 5,]

##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
```
```
xx[xx$Group == "X", c("Group","Data2","NewData1")]

##   Group Data2 NewData1
## 1     X    10       11
## 2     X    20       22
## 6     X    60       66
## 7     X    70       77
## 8     X    80       88
```

Data wrangling with tidyverse and pipes (%>%)

```
library(tidyverse) # install.packages("tidyverse")
xx <- data.frame(Group = c("X","X","Y","Y","Y","Y","Y","X","X","X")) %>%
  mutate(Data1 = 1:10, 
         Data2 = seq(10, 100, by = 10),
         NewData1 = Data1 + Data2,
         NewData2 = Data1 * 1000)
xx

```
```
##    Group Data1 Data2 NewData1 NewData2
## 1      X     1    10       11     1000
## 2      X     2    20       22     2000
## 3      Y     3    30       33     3000
## 4      Y     4    40       44     4000
## 5      Y     5    50       55     5000
## 6      Y     6    60       66     6000
## 7      Y     7    70       77     7000
## 8      X     8    80       88     8000
## 9      X     9    90       99     9000
## 10     X    10   100      110    10000
```


```
filter(xx, Data1 < 5)
##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
```
```
xx %>% filter(Data1 < 5)
##   Group Data1 Data2 NewData1 NewData2
## 1     X     1    10       11     1000
## 2     X     2    20       22     2000
## 3     Y     3    30       33     3000
## 4     Y     4    40       44     4000
```
```
xx %>% filter(Group == "X") %>% 
  select(Group, NewColName=Data2, NewData1)

##   Group NewColName NewData1
## 1     X         10       11
## 2     X         20       22
## 3     X         80       88
## 4     X         90       99
## 5     X        100      110
```
```
xs <- xx %>% 
  group_by(Group) %>% 
  summarise(Data2_mean = mean(Data2),
            Data2_sd = sd(Data2),
            NewData2_mean = mean(NewData2),
            NewData2_sd = sd(NewData2))
xs


## # A tibble: 2 x 5
##   Group Data2_mean Data2_sd NewData2_mean NewData2_sd
##   <chr>      <dbl>    <dbl>         <dbl>       <dbl>
## 1 X             60     41.8          6000       4183.
## 2 Y             50     15.8          5000       1581.
```
```
xx %>% left_join(xs, by = "Group")
##    Group Data1 Data2 NewData1 NewData2 Data2_mean Data2_sd NewData2_mean NewData2_sd
## 1      X     1    10       11     1000         60 41.83300          6000    4183.300
## 2      X     2    20       22     2000         60 41.83300          6000    4183.300
## 3      Y     3    30       33     3000         50 15.81139          5000    1581.139
## 4      Y     4    40       44     4000         50 15.81139          5000    1581.139
## 5      Y     5    50       55     5000         50 15.81139          5000    1581.139
## 6      Y     6    60       66     6000         50 15.81139          5000    1581.139
## 7      Y     7    70       77     7000         50 15.81139          5000    1581.139
## 8      X     8    80       88     8000         60 41.83300          6000    4183.300
## 9      X     9    90       99     9000         60 41.83300          6000    4183.300
## 10     X    10   100      110    10000         60 41.83300          6000    4183.300
```

Two ways to run your data: 
1. Select the line, then click run on top right in `Editor` 
2. Select the line, then press control+command+enter

https://r4ds.had.co.nz/data-visualisation.html
http://www.sthda.com/english/wiki/r-base-graphs
https://bookdown.org/rdpeng/exdata/the-base-plotting-system-1.html

## Basic grahics
1. Basic X-Y plotting
We will start with some basic plotting using the base function `plot()`

-c() Load a data frame into R
![Screenshot of main code listing](../fig/Visualize-your-data-1.png)


```
# A basic scatter plot
plot(x = xd$x8, y = xd$x9)
```
![Screenshot of main code listing](../fig/Visualize-your-data-2.png)

```
# Adjust color and shape of the points
plot(x = xd$x8, y = xd$x9, col = "darkred", pch = 0)
```
![Screenshot of main code listing](../fig/Visualize-your-data-3.png)

```
plot(x = xd$x8, y = xd$x9, col = xd$x4, pch = xd$x4)
```
![Screenshot of main code listing](../fig/Visualize-your-data-4.png)

```
# Adjust plot type 
plot(x = xd$x8, y = xd$x9, type = "line")
```

![Screenshot of main code listing](../fig/Visualize-your-data-5.png)

```
# Adjust linetype
plot(x = xd$x8, y = xd$x9, type = "line", lty = 2)
```
![Screenshot of main code listing](../fig/Visualize-your-data-6.png)

```
# Plot lines and points
plot(x = xd$x8, y = xd$x9, type = "both")
```
![Screenshot of main code listing](../fig/Visualize-your-data-7.png)

How about we now create some random and normally distributed data to make some more complicated plots:

```
# 100 random uniformly distributed numbers ranging from 0 - 100
ru <- runif(100, min = 0, max = 100)
ru
```
```
##   [1] 93.7792722  5.2058264 69.3092606 87.8757695 93.3245922 67.9051869 46.9099487 35.5891664 74.7797008  2.7596956 53.4739481 92.1409410
##  [13]  8.9753618 45.5635354 71.3770539 16.3657328 51.0398228 13.4896518 12.4459450 25.7143970 68.1830481 40.4708243 74.0677972 59.2101567
##  [25] 38.7055322 48.5972122 27.1599634 69.2195419 80.2855715  9.1769648 31.2876002 79.9755078  8.4545997 47.5581250  6.5751686 71.1780116
##  [37] 49.5609812  0.6333086 67.3160462 76.7686795 94.2319493  3.2416026 27.0022919 77.9143718 83.3589595 45.0760499 57.9321392 40.9880216
##  [49] 93.9983372 68.8077655 30.6024296 12.3127829 90.7924286 45.3508709 50.4629388  6.7605921 30.6151922 92.4777183 80.2674523 20.9279168
##  [61] 89.8962399  0.5688416 66.3812347 63.3058209 86.7850871 31.7576001 82.8562194 49.3832795 83.5812209  5.6286126 90.5950977 30.5509194
##  [73] 91.2311482 96.7813272 24.4044569 94.8301130 95.8874951 86.4078381 26.7188237 10.4742400  0.3250012  8.2367471 77.0652131 16.9814142
##  [85] 60.8751291 71.5650256  4.8838718 76.2454340 68.9297517 27.1255990 20.9791733 39.2620779 57.4075861 84.4399911 91.8024827 15.0074634
##  [97] 39.4713569 27.2310661 35.9280103 80.9529896
```
```
plot(x = ru)
```
![Screenshot of main code listing](../fig/Visualize-your-data-8.png)

```
order(ru)
```
```
##   [1]  81  62  38  10  42  87   2  70  35  56  82  33  13  30  80  52  19  18  96  16  84  60  91  75  20  79  43  90  27  98  72  51  57
##  [34]  31  66   8  99  25  92  97  22  48  46  54  14   7  34  26  68  37  55  17  11  93  47  24  85  64  63  39   6  21  50  89  28   3
##  [67]  36  15  86  23   9  88  40  83  44  32  59  29 100  67  45  69  94  78  65   4  61  71  53  73  95  12  58   5   1  49  41  76  77
## [100]  74
```
```
ru<- ru[order(ru)]
ru
```
```
##   [1]  0.3250012  0.5688416  0.6333086  2.7596956  3.2416026  4.8838718  5.2058264  5.6286126  6.5751686  6.7605921  8.2367471  8.4545997
##  [13]  8.9753618  9.1769648 10.4742400 12.3127829 12.4459450 13.4896518 15.0074634 16.3657328 16.9814142 20.9279168 20.9791733 24.4044569
##  [25] 25.7143970 26.7188237 27.0022919 27.1255990 27.1599634 27.2310661 30.5509194 30.6024296 30.6151922 31.2876002 31.7576001 35.5891664
##  [37] 35.9280103 38.7055322 39.2620779 39.4713569 40.4708243 40.9880216 45.0760499 45.3508709 45.5635354 46.9099487 47.5581250 48.5972122
##  [49] 49.3832795 49.5609812 50.4629388 51.0398228 53.4739481 57.4075861 57.9321392 59.2101567 60.8751291 63.3058209 66.3812347 67.3160462
##  [61] 67.9051869 68.1830481 68.8077655 68.9297517 69.2195419 69.3092606 71.1780116 71.3770539 71.5650256 74.0677972 74.7797008 76.2454340
##  [73] 76.7686795 77.0652131 77.9143718 79.9755078 80.2674523 80.2855715 80.9529896 82.8562194 83.3589595 83.5812209 84.4399911 86.4078381
##  [85] 86.7850871 87.8757695 89.8962399 90.5950977 90.7924286 91.2311482 91.8024827 92.1409410 92.4777183 93.3245922 93.7792722 93.9983372
##  [97] 94.2319493 94.8301130 95.8874951 96.7813272
```

```
plot(x = ru)
```
![Screenshot of main code listing](../fig/Visualize-your-data-9.png)

```
# 100 normally distributed numbers with a mean of 50 and sd of 10
nd <- rnorm(100, mean = 50, sd = 10)
nd
```
```
##   [1] 38.40931 54.50517 61.00758 48.24371 55.05703 50.19036 75.92284 65.39284 58.75954 42.96810 45.87521 58.25970 47.82696 45.19008
##  [15] 54.57716 43.44305 67.67423 55.49420 42.37655 68.21933 49.80417 54.71856 33.31593 34.93320 46.63470 53.88502 48.86226 47.84021
##  [29] 65.98524 61.40776 40.74877 26.02507 30.57845 51.05247 43.76863 83.17006 25.25972 51.80369 54.21798 68.06235 53.69070 34.84286
##  [43] 64.18536 60.73534 58.38647 60.15617 53.86052 33.32625 49.78303 54.79121 42.29689 44.92490 57.54842 49.39659 65.47622 62.40080
##  [57] 58.58921 57.18908 48.48429 40.02540 49.49290 47.99492 59.49275 52.43222 64.25810 75.30217 72.62295 33.67732 81.02630 61.60500
##  [71] 61.17238 36.94567 32.65669 60.83920 54.88921 50.03472 66.01779 40.95968 65.58695 56.29101 48.98033 39.95974 50.33351 57.50313
##  [85] 44.06732 59.69696 45.56645 41.10511 46.04440 43.69505 64.95305 52.92210 53.65435 62.51068 52.27743 65.31862 72.85238 53.81886
##  [99] 49.44123 50.25871
```
```
nd <- nd[order(nd)]
nd
```
```
##   [1] 25.25972 26.02507 30.57845 32.65669 33.31593 33.32625 33.67732 34.84286 34.93320 36.94567 38.40931 39.95974 40.02540 40.74877
##  [15] 40.95968 41.10511 42.29689 42.37655 42.96810 43.44305 43.69505 43.76863 44.06732 44.92490 45.19008 45.56645 45.87521 46.04440
##  [29] 46.63470 47.82696 47.84021 47.99492 48.24371 48.48429 48.86226 48.98033 49.39659 49.44123 49.49290 49.78303 49.80417 50.03472
##  [43] 50.19036 50.25871 50.33351 51.05247 51.80369 52.27743 52.43222 52.92210 53.65435 53.69070 53.81886 53.86052 53.88502 54.21798
##  [57] 54.50517 54.57716 54.71856 54.79121 54.88921 55.05703 55.49420 56.29101 57.18908 57.50313 57.54842 58.25970 58.38647 58.58921
##  [71] 58.75954 59.49275 59.69696 60.15617 60.73534 60.83920 61.00758 61.17238 61.40776 61.60500 62.40080 62.51068 64.18536 64.25810
##  [85] 64.95305 65.31862 65.39284 65.47622 65.58695 65.98524 66.01779 67.67423 68.06235 68.21933 72.62295 72.85238 75.30217 75.92284
##  [99] 81.02630 83.17006
```
```
plot(x = nd)
```
![Screenshot of main code listing](../fig/Visualize-your-data-10.png)

## Histogram

```
hist(x = nd)
```
![Screenshot of main code listing](../fig/Visualize-your-data-11.png)

```
hist(nd, breaks = 20, col = "darkgreen")
```
![Screenshot of main code listing](../fig/Visualize-your-data-12.png)

```
plot(x = density(nd))
```
![Screenshot of main code listing](../fig/Visualize-your-data-13.png)

```
boxplot(x = nd)
```
![Screenshot of main code listing](../fig/Visualize-your-data-14.png)

```
boxplot(x = nd, horizontal = T)
```
![Screenshot of main code listing](../fig/Visualize-your-data-15.png)

## 1.1 Basic scatter plot




## ggplot2 package 
Comprare to basic plots, ggplot2 package provides better visually appealing plots. ggplot2 package needs to be installed before use. 
See bottom right on the RStudio:
click on `Packages` tab, select on `Install`, then search `ggplo2` under Packages to install ggplots2.


![Screenshot of main code listing](../fig/Visualize-your-data-16.png)


Additional packages such as `ggbeeswarm` and `ggrepel` also contain useful functions to add to the functionality of ggplot2.

https://ggplot2.tidyverse.org/
https://www.r-graph-gallery.com/ggplot2-package.html
http://r-statistics.co/ggplot2-Tutorial-With-R.html

```
library(ggplot2)
mp <- ggplot(xd, aes(x = x8, y = x9))
mp + geom_point()
```
![Screenshot of main code listing](../fig/Visualize-your-data-17.png)

```
mp + geom_point(aes(color = x3, shape = x3), size = 4)
```
(https://www.statsandr.com/blog/graphics-in-r-with-ggplot2/)
(https://derekmichaelwright.github.io/htmls/academic/envdata.html#)
 
 
![Screenshot of main code listing](../fig/Visualize-your-data-18.png)

```
mp + geom_line(size = 2)
```
![Screenshot of main code listing](../fig/Visualize-your-data-19.png)

```
mp + geom_line(aes(color = x3), size = 2)
```
![Screenshot of main code listing](../fig/Visualize-your-data-20.png)

```
mp + geom_smooth(method = "loess")
```

![Screenshot of main code listing](../fig/Visualize-your-data-21.png)

```
mp + geom_smooth(method = "lm")
```
![Screenshot of main code listing](../fig/Visualize-your-data-22.png)

```
xx <- data.frame(data = c(rnorm(50, mean = 40, sd = 10),
                          rnorm(50, mean = 60, sd = 5)),
                 group = factor(rep(1:2, each = 50)),
                 label = c("Label1", rep(NA, 49), "Label2", rep(NA, 49)))
mp <- ggplot(xx, aes(x = data, fill = group))
mp + geom_histogram(color = "black")
```

![Screenshot of main code listing](../fig/Visualize-your-data-23.png)

```
mp + geom_histogram(color = "black", position = "dodge")
```
![Screenshot of main code listing](../fig/Visualize-your-data-24.png)

```
mp1 <- mp + geom_histogram(color = "black") + facet_grid(group~.)
mp1
```
![Screenshot of main code listing](../fig/Visualize-your-data-25.png)

```
mp + geom_density(alpha = 0.5)
```
![Screenshot of main code listing](../fig/Visualize-your-data-26.png)

```
mp <- ggplot(xx, aes(x = group, y = data, fill = group))
mp + geom_boxplot(color = "black")
```
![Screenshot of main code listing](../fig/Visualize-your-data-27.png)

```
mp + geom_boxplot() + geom_point()
```

![Screenshot of main code listing](../fig/Visualize-your-data-28.png)

```
mp + geom_violin() + geom_boxplot(width = 0.1, fill = "white")
```
![Screenshot of main code listing](../fig/Visualize-your-data-29.png)

```
library(ggbeeswarm)
mp + geom_quasirandom()
```
* Make sure your have ggbeeswarm package installed 
![Screenshot of main code listing](../fig/Visualize-your-data-30.png)

```
mp + geom_quasirandom(aes(shape = group))
```
![Screenshot of main code listing](../fig/Visualize-your-data-31.png)

```
mp2 <- mp + geom_violin() + 
  geom_boxplot(width = 0.1, fill = "white") +
  geom_beeswarm(alpha = 0.5)
library(ggrepel)
mp2 + geom_text_repel(aes(label = label), nudge_x = 0.4)
```
![Screenshot of main code listing](../fig/Visualize-your-data-32.png)
```
library(ggpubr)
ggarrange(mp1, mp2, ncol = 2, widths = c(2,1),
          common.legend = T, legend = "bottom")
```
![Screenshot of main code listing](../fig/Visualize-your-data-33.png)