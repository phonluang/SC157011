Multidisciplinary
================
phonluang
2025-03-05

``` r
library(dplyr)
```

    ## Warning: package 'dplyr' was built under R version 4.4.3

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
#เปิดไฟล์ iris
head(iris)
```

    ##   Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1          5.1         3.5          1.4         0.2  setosa
    ## 2          4.9         3.0          1.4         0.2  setosa
    ## 3          4.7         3.2          1.3         0.2  setosa
    ## 4          4.6         3.1          1.5         0.2  setosa
    ## 5          5.0         3.6          1.4         0.2  setosa
    ## 6          5.4         3.9          1.7         0.4  setosa

``` r
#กรองเฉพาะ setosa
filter(iris, Species == "setosa")
```

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1           5.1         3.5          1.4         0.2  setosa
    ## 2           4.9         3.0          1.4         0.2  setosa
    ## 3           4.7         3.2          1.3         0.2  setosa
    ## 4           4.6         3.1          1.5         0.2  setosa
    ## 5           5.0         3.6          1.4         0.2  setosa
    ## 6           5.4         3.9          1.7         0.4  setosa
    ## 7           4.6         3.4          1.4         0.3  setosa
    ## 8           5.0         3.4          1.5         0.2  setosa
    ## 9           4.4         2.9          1.4         0.2  setosa
    ## 10          4.9         3.1          1.5         0.1  setosa
    ## 11          5.4         3.7          1.5         0.2  setosa
    ## 12          4.8         3.4          1.6         0.2  setosa
    ## 13          4.8         3.0          1.4         0.1  setosa
    ## 14          4.3         3.0          1.1         0.1  setosa
    ## 15          5.8         4.0          1.2         0.2  setosa
    ## 16          5.7         4.4          1.5         0.4  setosa
    ## 17          5.4         3.9          1.3         0.4  setosa
    ## 18          5.1         3.5          1.4         0.3  setosa
    ## 19          5.7         3.8          1.7         0.3  setosa
    ## 20          5.1         3.8          1.5         0.3  setosa
    ## 21          5.4         3.4          1.7         0.2  setosa
    ## 22          5.1         3.7          1.5         0.4  setosa
    ## 23          4.6         3.6          1.0         0.2  setosa
    ## 24          5.1         3.3          1.7         0.5  setosa
    ## 25          4.8         3.4          1.9         0.2  setosa
    ## 26          5.0         3.0          1.6         0.2  setosa
    ## 27          5.0         3.4          1.6         0.4  setosa
    ## 28          5.2         3.5          1.5         0.2  setosa
    ## 29          5.2         3.4          1.4         0.2  setosa
    ## 30          4.7         3.2          1.6         0.2  setosa
    ## 31          4.8         3.1          1.6         0.2  setosa
    ## 32          5.4         3.4          1.5         0.4  setosa
    ## 33          5.2         4.1          1.5         0.1  setosa
    ## 34          5.5         4.2          1.4         0.2  setosa
    ## 35          4.9         3.1          1.5         0.2  setosa
    ## 36          5.0         3.2          1.2         0.2  setosa
    ## 37          5.5         3.5          1.3         0.2  setosa
    ## 38          4.9         3.6          1.4         0.1  setosa
    ## 39          4.4         3.0          1.3         0.2  setosa
    ## 40          5.1         3.4          1.5         0.2  setosa
    ## 41          5.0         3.5          1.3         0.3  setosa
    ## 42          4.5         2.3          1.3         0.3  setosa
    ## 43          4.4         3.2          1.3         0.2  setosa
    ## 44          5.0         3.5          1.6         0.6  setosa
    ## 45          5.1         3.8          1.9         0.4  setosa
    ## 46          4.8         3.0          1.4         0.3  setosa
    ## 47          5.1         3.8          1.6         0.2  setosa
    ## 48          4.6         3.2          1.4         0.2  setosa
    ## 49          5.3         3.7          1.5         0.2  setosa
    ## 50          5.0         3.3          1.4         0.2  setosa

``` r
#ตั้งชื่อข้อมูลที่กรองแล้วว่า setosa
setosa <- filter(iris, Species == "setosa") 

#สรุปข้อมูลของ setosa
summary(setosa)
```

    ##   Sepal.Length    Sepal.Width     Petal.Length    Petal.Width   
    ##  Min.   :4.300   Min.   :2.300   Min.   :1.000   Min.   :0.100  
    ##  1st Qu.:4.800   1st Qu.:3.200   1st Qu.:1.400   1st Qu.:0.200  
    ##  Median :5.000   Median :3.400   Median :1.500   Median :0.200  
    ##  Mean   :5.006   Mean   :3.428   Mean   :1.462   Mean   :0.246  
    ##  3rd Qu.:5.200   3rd Qu.:3.675   3rd Qu.:1.575   3rd Qu.:0.300  
    ##  Max.   :5.800   Max.   :4.400   Max.   :1.900   Max.   :0.600  
    ##        Species  
    ##  setosa    :50  
    ##  versicolor: 0  
    ##  virginica : 0  
    ##                 
    ##                 
    ## 

``` r
#ได้ค่า mean ของ petal length=1.462
#กรองข้อมูล petal length ที่มีค่ามากกว่า 1.462
filter(setosa, Petal.Length > 1.462) 
```

    ##    Sepal.Length Sepal.Width Petal.Length Petal.Width Species
    ## 1           4.6         3.1          1.5         0.2  setosa
    ## 2           5.4         3.9          1.7         0.4  setosa
    ## 3           5.0         3.4          1.5         0.2  setosa
    ## 4           4.9         3.1          1.5         0.1  setosa
    ## 5           5.4         3.7          1.5         0.2  setosa
    ## 6           4.8         3.4          1.6         0.2  setosa
    ## 7           5.7         4.4          1.5         0.4  setosa
    ## 8           5.7         3.8          1.7         0.3  setosa
    ## 9           5.1         3.8          1.5         0.3  setosa
    ## 10          5.4         3.4          1.7         0.2  setosa
    ## 11          5.1         3.7          1.5         0.4  setosa
    ## 12          5.1         3.3          1.7         0.5  setosa
    ## 13          4.8         3.4          1.9         0.2  setosa
    ## 14          5.0         3.0          1.6         0.2  setosa
    ## 15          5.0         3.4          1.6         0.4  setosa
    ## 16          5.2         3.5          1.5         0.2  setosa
    ## 17          4.7         3.2          1.6         0.2  setosa
    ## 18          4.8         3.1          1.6         0.2  setosa
    ## 19          5.4         3.4          1.5         0.4  setosa
    ## 20          5.2         4.1          1.5         0.1  setosa
    ## 21          4.9         3.1          1.5         0.2  setosa
    ## 22          5.1         3.4          1.5         0.2  setosa
    ## 23          5.0         3.5          1.6         0.6  setosa
    ## 24          5.1         3.8          1.9         0.4  setosa
    ## 25          5.1         3.8          1.6         0.2  setosa
    ## 26          5.3         3.7          1.5         0.2  setosa

``` r
#ตั้งชื่อไฟล์ที่กรองแล้วว่า nongcho_so_cute
nongcho_so_cute <- filter(setosa, Petal.Length > 1.462) 

#สร้าง histogram ของ setosa ที่มี petal length มากกว่าค่า mean
hist(nongcho_so_cute$Petal.Length)
```

![](setosa_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

``` r
#สร้าง boxplot ค่า petal lenght และ sepal length
boxplot(nongcho_so_cute[,c("Sepal.Length", "Petal.Length")])
```

![](setosa_files/figure-gfm/unnamed-chunk-1-2.png)<!-- -->
