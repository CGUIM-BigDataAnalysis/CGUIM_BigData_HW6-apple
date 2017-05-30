林昱珊 許凱晶 台灣地區登革熱分析
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

登革熱（Dengue fever），是一種由登革病毒所引起的急性傳染病，這種病毒會經由蚊子傳播給人類。並且依據不同的血清型病毒，分為Ⅰ、Ⅱ、Ⅲ、Ⅳ四種型別，而每一型都具有能感染致病的能力。 全球登革熱的好發地區，主要集中在熱帶、亞熱帶等有埃及斑蚊和白線斑蚊分布的國家，隨著全球化發展逐漸便利，各國之間相互流通及往返也趨於頻繁，自1980年代之後，登革熱也開始向各國蔓延，成為嚴重的公共衛生問題。臺灣位於亞熱帶地區，像這樣有點熱、又有點溼的環境，正是蚊子最喜歡的生長環境，為登革熱流行高風險地區。 預防此疾病的議題受大家的重視，因為少部分患者可能因此受生命的威脅，雖然有發展登革熱疫苗，但預防還是勝於治療，除了減少接觸斑紋，也需要減少斑紋滋生地和數目。 \#\# 分析動機 秋夏季節來臨有些疾病也伴隨著而來，分析疾病的資料有助於我們對環境的了解，也可以讓我們避免疾病的惡化並改善地區環境的整潔。 \#\# 使用資料 我們從疾病管制署的開放平台分析有關登革熱的開放式資料，登革熱的資料一共八筆，而我們分析的是"地區年齡統計表-登革熱"這個資料。(<https://data.cdc.gov.tw/dataset/aagstable-dengue/resource/0c267503-e158-4bdf-b879-eddb5d3e0c6f>)

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

說明處理資料的步驟 1.檢查是否有空值

``` r
#這是R Code Chunk
Age_County_Gender_061NA<-Age_County_Gender_061[complete.cases(Age_County_Gender_061),]
```

探索式資料分析
--------------

圖文並茂圖文並茂

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

    ## # A tibble: 22 × 2
    ##     .dots  病例
    ##    <fctr> <int>
    ## 1  高雄市 40796
    ## 2  台南市 26406
    ## 3  屏東縣  1762
    ## 4  台北市   701
    ## 5  新北市   633
    ## 6  台中市   449
    ## 7  桃園市   438
    ## 8  彰化縣   159
    ## 9  澎湖縣   137
    ## 10 新竹縣   114
    ## # ... with 12 more rows

``` r
#install.packages("ggplot2")
#library(ggplot2)
#ggplot()+geom_bar(data=Age_County_Gender_061NA,
#aes(x=發病月份,y=發病年份),
#                 stat = "identity") 
```

期末專題分析規劃
----------------

透過資料的分析了解在台灣登革熱的發生區域，進而我們還可以了解醫療資源的分配和一些疾病的預防。 之後還會再從資料中分析出台灣常見的疾病，還有地區、氣候跟疾病的關係。
