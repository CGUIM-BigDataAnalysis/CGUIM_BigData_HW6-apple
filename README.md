長庚大學 大數據分析方法 作業六
================

作業說明 （繳交時請直接刪除這個章節）
-------------------------------------

作業目的：期末專題暖身

依下列指示，完成期末分析專題作業規劃：

-   訂出分析問題，並將R Markdown的一級標題(第一行的title:)中的"長庚大學 大數據分析方法 作業六"取代為期末專題的分析問題，並在分析議題背景前加上組員姓名 (`10pt`)
-   分析議題背景 (`10pt`) 與動機 (`10pt`)
-   資料說明 (`10pt`) 與 載入 (`10pt`)
-   資料處理與清洗 (`10pt`) 說明 (`10pt`)
-   對資料們進行探索式資料分析，圖文並茂佳!(`20pt`)
-   期末專題分析規劃與假設 (`10pt`)

分析議題背景
------------

背景介紹背景介紹

分析動機
--------

分析動機分析動機

使用資料
--------

說明使用資料們

載入使用資料們

``` r
#這是R Code Chunk
library(readr)
```

    ## Warning: package 'readr' was built under R version 3.3.3

``` r
Age_County_Gender_061 <- read.csv("C:/Users/user/Downloads/Age_County_Gender_061.csv",fileEncoding = "big5")
```

資料處理與清洗
--------------

說明處理資料的步驟

處理資料

``` r
#這是R Code Chunk
library(dplyr)
```

    ## Warning: package 'dplyr' was built under R version 3.3.3

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
group_by(Age_County_Gender_061,.dots=縣市) %>%
  summarise(病例=sum(確定病例數)) %>%
  arrange(desc(病例))
```

    ## # A tibble: 22 x 2
    ##     .dots  病例
    ##    <fctr> <int>
    ##  1 高雄市 40796
    ##  2 台南市 26406
    ##  3 屏東縣  1762
    ##  4 台北市   701
    ##  5 新北市   633
    ##  6 台中市   449
    ##  7 桃園市   438
    ##  8 彰化縣   159
    ##  9 澎湖縣   137
    ## 10 新竹縣   114
    ## # ... with 12 more rows

``` r
#install.packages("ggplot2")
#library(ggplot2)
#ggplot()+geom_bar(data=Age_County_Gender_061NA,
#aes(x=發病月份,y=發病年份),
#                 stat = "identity") 
```

探索式資料分析
--------------

圖文並茂圖文並茂

``` r
#這是R Code Chunk
```

期末專題分析規劃
----------------

期末專題要做XXOOO交叉分析
