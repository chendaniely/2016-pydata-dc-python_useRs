# useRs
Daniel Chen  



## How to get it?

Google 'R'

## How to get it?

- https://www.r-project.org/
- https://www.rstudio.com/products/rstudio/download/preview/

- `conda install -c r r-essentials`
- `jupyter notebook`

## Using it

Nothing to import!


```r
ebola_df <- read.csv('../data/country_timeseries.csv', stringsAsFactors = FALSE)
head(ebola_df)
```

```
##         Date Day Cases_Guinea Cases_Liberia Cases_SierraLeone
## 1   1/5/2015 289         2776            NA             10030
## 2   1/4/2015 288         2775            NA              9780
## 3   1/3/2015 287         2769          8166              9722
## 4   1/2/2015 286           NA          8157                NA
## 5 12/31/2014 284         2730          8115              9633
## 6 12/28/2014 281         2706          8018              9446
##   Cases_Nigeria Cases_Senegal Cases_UnitedStates Cases_Spain Cases_Mali
## 1            NA            NA                 NA          NA         NA
## 2            NA            NA                 NA          NA         NA
## 3            NA            NA                 NA          NA         NA
## 4            NA            NA                 NA          NA         NA
## 5            NA            NA                 NA          NA         NA
## 6            NA            NA                 NA          NA         NA
##   Deaths_Guinea Deaths_Liberia Deaths_SierraLeone Deaths_Nigeria
## 1          1786             NA               2977             NA
## 2          1781             NA               2943             NA
## 3          1767           3496               2915             NA
## 4            NA           3496                 NA             NA
## 5          1739           3471               2827             NA
## 6          1708           3423               2758             NA
##   Deaths_Senegal Deaths_UnitedStates Deaths_Spain Deaths_Mali
## 1             NA                  NA           NA          NA
## 2             NA                  NA           NA          NA
## 3             NA                  NA           NA          NA
## 4             NA                  NA           NA          NA
## 5             NA                  NA           NA          NA
## 6             NA                  NA           NA          NA
```

## Using it - tidyverse


```r
library(readr)
library(readxl)
library(haven)

ebola_df_tv <- read_csv('../data/country_timeseries.csv')
```

```
## Parsed with column specification:
## cols(
##   Date = col_character(),
##   Day = col_integer(),
##   Cases_Guinea = col_integer(),
##   Cases_Liberia = col_integer(),
##   Cases_SierraLeone = col_integer(),
##   Cases_Nigeria = col_integer(),
##   Cases_Senegal = col_integer(),
##   Cases_UnitedStates = col_integer(),
##   Cases_Spain = col_integer(),
##   Cases_Mali = col_integer(),
##   Deaths_Guinea = col_integer(),
##   Deaths_Liberia = col_integer(),
##   Deaths_SierraLeone = col_integer(),
##   Deaths_Nigeria = col_integer(),
##   Deaths_Senegal = col_integer(),
##   Deaths_UnitedStates = col_integer(),
##   Deaths_Spain = col_integer(),
##   Deaths_Mali = col_integer()
## )
```

## Using it - tidyverse


```r
ebola_df_tv2 <- readr::read_csv('../data/country_timeseries.csv')
```

```
## Parsed with column specification:
## cols(
##   Date = col_character(),
##   Day = col_integer(),
##   Cases_Guinea = col_integer(),
##   Cases_Liberia = col_integer(),
##   Cases_SierraLeone = col_integer(),
##   Cases_Nigeria = col_integer(),
##   Cases_Senegal = col_integer(),
##   Cases_UnitedStates = col_integer(),
##   Cases_Spain = col_integer(),
##   Cases_Mali = col_integer(),
##   Deaths_Guinea = col_integer(),
##   Deaths_Liberia = col_integer(),
##   Deaths_SierraLeone = col_integer(),
##   Deaths_Nigeria = col_integer(),
##   Deaths_Senegal = col_integer(),
##   Deaths_UnitedStates = col_integer(),
##   Deaths_Spain = col_integer(),
##   Deaths_Mali = col_integer()
## )
```

## Using it


```r
dim(ebola_df_tv)
```

```
## [1] 122  18
```


```r
summary(ebola_df_tv)
```

```
##      Date                Day          Cases_Guinea    Cases_Liberia   
##  Length:122         Min.   :  0.00   Min.   :  49.0   Min.   :   3.0  
##  Class :character   1st Qu.: 66.25   1st Qu.: 236.0   1st Qu.:  25.5  
##  Mode  :character   Median :150.00   Median : 495.0   Median : 516.0  
##                     Mean   :144.78   Mean   : 911.1   Mean   :2335.3  
##                     3rd Qu.:219.50   3rd Qu.:1519.0   3rd Qu.:4162.5  
##                     Max.   :289.00   Max.   :2776.0   Max.   :8166.0  
##                                      NA's   :29       NA's   :39      
##  Cases_SierraLeone Cases_Nigeria   Cases_Senegal  Cases_UnitedStates
##  Min.   :    0.0   Min.   : 0.00   Min.   :1.00   Min.   :1.000     
##  1st Qu.:   64.5   1st Qu.:15.00   1st Qu.:1.00   1st Qu.:3.000     
##  Median :  783.0   Median :20.00   Median :1.00   Median :4.000     
##  Mean   : 2427.4   Mean   :16.74   Mean   :1.08   Mean   :3.278     
##  3rd Qu.: 3801.0   3rd Qu.:20.00   3rd Qu.:1.00   3rd Qu.:4.000     
##  Max.   :10030.0   Max.   :22.00   Max.   :3.00   Max.   :4.000     
##  NA's   :35        NA's   :84      NA's   :97     NA's   :104       
##   Cases_Spain    Cases_Mali   Deaths_Guinea    Deaths_Liberia
##  Min.   :1     Min.   :1.00   Min.   :  29.0   Min.   :   2  
##  1st Qu.:1     1st Qu.:1.00   1st Qu.: 157.8   1st Qu.:  12  
##  Median :1     Median :2.50   Median : 360.5   Median : 294  
##  Mean   :1     Mean   :3.50   Mean   : 563.2   Mean   :1101  
##  3rd Qu.:1     3rd Qu.:6.25   3rd Qu.: 847.8   3rd Qu.:2413  
##  Max.   :1     Max.   :7.00   Max.   :1786.0   Max.   :3496  
##  NA's   :106   NA's   :110    NA's   :30       NA's   :41    
##  Deaths_SierraLeone Deaths_Nigeria  Deaths_Senegal Deaths_UnitedStates
##  Min.   :   0.0     Min.   :0.000   Min.   :0      Min.   :0.0000     
##  1st Qu.:   6.0     1st Qu.:4.000   1st Qu.:0      1st Qu.:1.0000     
##  Median : 334.0     Median :8.000   Median :0      Median :1.0000     
##  Mean   : 693.7     Mean   :6.132   Mean   :0      Mean   :0.8333     
##  3rd Qu.:1176.0     3rd Qu.:8.000   3rd Qu.:0      3rd Qu.:1.0000     
##  Max.   :2977.0     Max.   :8.000   Max.   :0      Max.   :1.0000     
##  NA's   :35         NA's   :84      NA's   :100    NA's   :104        
##   Deaths_Spain     Deaths_Mali   
##  Min.   :0.0000   Min.   :1.000  
##  1st Qu.:0.0000   1st Qu.:1.000  
##  Median :0.0000   Median :2.000  
##  Mean   :0.1875   Mean   :3.167  
##  3rd Qu.:0.0000   3rd Qu.:6.000  
##  Max.   :1.0000   Max.   :6.000  
##  NA's   :106      NA's   :110
```

## Subsetting in R


```r
ebola_df$Day
```

```
##   [1] 289 288 287 286 284 281 280 277 273 272 271 267 262 260 256 253 251
##  [18] 246 245 241 239 238 234 233 232 231 227 226 225 222 220 218 216 214
##  [35] 213 211 210 206 205 204 203 200 199 197 196 193 190 185 183 182 181
##  [52] 179 176 175 172 171 169 167 162 157 151 149 147 144 142 140 137 135
##  [69] 132 129 126 123 120 117 114 112 108 106 102 100  92  90  89  88  87
##  [86]  86  80  75  73  71  67  66  62  51  49  46  44  42  40  35  33  32
## [103]  31  30  29  26  25  24  23  20  18  16  13  10   9   7   6   5   4
## [120]   3   2   0
```

## Subsetting in R

```r
ebola_df[, 'Day']
```

```
##   [1] 289 288 287 286 284 281 280 277 273 272 271 267 262 260 256 253 251
##  [18] 246 245 241 239 238 234 233 232 231 227 226 225 222 220 218 216 214
##  [35] 213 211 210 206 205 204 203 200 199 197 196 193 190 185 183 182 181
##  [52] 179 176 175 172 171 169 167 162 157 151 149 147 144 142 140 137 135
##  [69] 132 129 126 123 120 117 114 112 108 106 102 100  92  90  89  88  87
##  [86]  86  80  75  73  71  67  66  62  51  49  46  44  42  40  35  33  32
## [103]  31  30  29  26  25  24  23  20  18  16  13  10   9   7   6   5   4
## [120]   3   2   0
```

## Subsetting in R

```r
head(ebola_df[, c('Day', 'Cases_Guinea')])
```

```
##   Day Cases_Guinea
## 1 289         2776
## 2 288         2775
## 3 287         2769
## 4 286           NA
## 5 284         2730
## 6 281         2706
```

## Subsetting in R

```r
head(ebola_df[, c(1, 2)]) # 1 indexed
```

```
##         Date Day
## 1   1/5/2015 289
## 2   1/4/2015 288
## 3   1/3/2015 287
## 4   1/2/2015 286
## 5 12/31/2014 284
## 6 12/28/2014 281
```

## Subsetting in R

```r
ebola_df[ebola_df$Cases_SierraLeone > 5000, c(1, 2)]
```

```
##             Date Day
## 1       1/5/2015 289
## 2       1/4/2015 288
## 3       1/3/2015 287
## NA          <NA>  NA
## 5     12/31/2014 284
## 6     12/28/2014 281
## 7     12/27/2014 280
## 8     12/24/2014 277
## 9     12/21/2014 273
## 10    12/20/2014 272
## NA.1        <NA>  NA
## 12    12/14/2014 267
## NA.2        <NA>  NA
## 14     12/7/2014 260
## NA.3        <NA>  NA
## 16    11/30/2014 253
## NA.4        <NA>  NA
## 18    11/23/2014 246
## NA.5        <NA>  NA
## 20    11/18/2014 241
## 21    11/16/2014 239
## NA.6        <NA>  NA
## 23    11/11/2014 234
## NA.7        <NA>  NA
## 25     11/9/2014 232
## NA.8        <NA>  NA
## NA.9        <NA>  NA
## NA.10       <NA>  NA
## 31    10/29/2014 220
## 32    10/27/2014 218
## NA.11       <NA>  NA
## NA.12       <NA>  NA
## NA.13       <NA>  NA
## NA.14       <NA>  NA
## NA.15       <NA>  NA
## NA.16       <NA>  NA
## NA.17       <NA>  NA
## NA.18       <NA>  NA
## NA.19       <NA>  NA
## NA.20       <NA>  NA
## NA.21       <NA>  NA
## NA.22       <NA>  NA
## NA.23       <NA>  NA
## NA.24       <NA>  NA
## NA.25       <NA>  NA
## NA.26       <NA>  NA
## NA.27       <NA>  NA
## NA.28       <NA>  NA
## NA.29       <NA>  NA
## NA.30       <NA>  NA
## NA.31       <NA>  NA
## NA.32       <NA>  NA
## NA.33       <NA>  NA
## NA.34       <NA>  NA
```

## Getting the types of things


```r
print(class(ebola_df$Day))
```

```
## [1] "integer"
```

```r
print(class(ebola_df[, c('Day', 'Cases_Guinea')]))
```

```
## [1] "data.frame"
```

## Creating new columns

```r
dim(ebola_df)
```

```
## [1] 122  18
```


```r
library(magrittr)
ebola_df %>% head()
```

```
##         Date Day Cases_Guinea Cases_Liberia Cases_SierraLeone
## 1   1/5/2015 289         2776            NA             10030
## 2   1/4/2015 288         2775            NA              9780
## 3   1/3/2015 287         2769          8166              9722
## 4   1/2/2015 286           NA          8157                NA
## 5 12/31/2014 284         2730          8115              9633
## 6 12/28/2014 281         2706          8018              9446
##   Cases_Nigeria Cases_Senegal Cases_UnitedStates Cases_Spain Cases_Mali
## 1            NA            NA                 NA          NA         NA
## 2            NA            NA                 NA          NA         NA
## 3            NA            NA                 NA          NA         NA
## 4            NA            NA                 NA          NA         NA
## 5            NA            NA                 NA          NA         NA
## 6            NA            NA                 NA          NA         NA
##   Deaths_Guinea Deaths_Liberia Deaths_SierraLeone Deaths_Nigeria
## 1          1786             NA               2977             NA
## 2          1781             NA               2943             NA
## 3          1767           3496               2915             NA
## 4            NA           3496                 NA             NA
## 5          1739           3471               2827             NA
## 6          1708           3423               2758             NA
##   Deaths_Senegal Deaths_UnitedStates Deaths_Spain Deaths_Mali
## 1             NA                  NA           NA          NA
## 2             NA                  NA           NA          NA
## 3             NA                  NA           NA          NA
## 4             NA                  NA           NA          NA
## 5             NA                  NA           NA          NA
## 6             NA                  NA           NA          NA
```

## Creating new columns

```r
ebola_df$some_deaths <- ebola_df$Deaths_Guinea + ebola_df$Deaths_Liberia

ebola_df %>% dim() %>% print()
```

```
## [1] 122  19
```

```r
ebola_df %>% head() %>% print()
```

```
##         Date Day Cases_Guinea Cases_Liberia Cases_SierraLeone
## 1   1/5/2015 289         2776            NA             10030
## 2   1/4/2015 288         2775            NA              9780
## 3   1/3/2015 287         2769          8166              9722
## 4   1/2/2015 286           NA          8157                NA
## 5 12/31/2014 284         2730          8115              9633
## 6 12/28/2014 281         2706          8018              9446
##   Cases_Nigeria Cases_Senegal Cases_UnitedStates Cases_Spain Cases_Mali
## 1            NA            NA                 NA          NA         NA
## 2            NA            NA                 NA          NA         NA
## 3            NA            NA                 NA          NA         NA
## 4            NA            NA                 NA          NA         NA
## 5            NA            NA                 NA          NA         NA
## 6            NA            NA                 NA          NA         NA
##   Deaths_Guinea Deaths_Liberia Deaths_SierraLeone Deaths_Nigeria
## 1          1786             NA               2977             NA
## 2          1781             NA               2943             NA
## 3          1767           3496               2915             NA
## 4            NA           3496                 NA             NA
## 5          1739           3471               2827             NA
## 6          1708           3423               2758             NA
##   Deaths_Senegal Deaths_UnitedStates Deaths_Spain Deaths_Mali some_deaths
## 1             NA                  NA           NA          NA          NA
## 2             NA                  NA           NA          NA          NA
## 3             NA                  NA           NA          NA        5263
## 4             NA                  NA           NA          NA          NA
## 5             NA                  NA           NA          NA        5210
## 6             NA                  NA           NA          NA        5131
```

## Creating new columns - tidyverse


```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

## Creating new columns - tidyverse

```r
ebola_df <- ebola_df %>%
    mutate(some_deaths2 = Deaths_Guinea + Deaths_Liberia)
ebola_df %>% dim() %>% print()
```

```
## [1] 122  20
```

```r
ebola_df %>% head() %>% print()
```

```
##         Date Day Cases_Guinea Cases_Liberia Cases_SierraLeone
## 1   1/5/2015 289         2776            NA             10030
## 2   1/4/2015 288         2775            NA              9780
## 3   1/3/2015 287         2769          8166              9722
## 4   1/2/2015 286           NA          8157                NA
## 5 12/31/2014 284         2730          8115              9633
## 6 12/28/2014 281         2706          8018              9446
##   Cases_Nigeria Cases_Senegal Cases_UnitedStates Cases_Spain Cases_Mali
## 1            NA            NA                 NA          NA         NA
## 2            NA            NA                 NA          NA         NA
## 3            NA            NA                 NA          NA         NA
## 4            NA            NA                 NA          NA         NA
## 5            NA            NA                 NA          NA         NA
## 6            NA            NA                 NA          NA         NA
##   Deaths_Guinea Deaths_Liberia Deaths_SierraLeone Deaths_Nigeria
## 1          1786             NA               2977             NA
## 2          1781             NA               2943             NA
## 3          1767           3496               2915             NA
## 4            NA           3496                 NA             NA
## 5          1739           3471               2827             NA
## 6          1708           3423               2758             NA
##   Deaths_Senegal Deaths_UnitedStates Deaths_Spain Deaths_Mali some_deaths
## 1             NA                  NA           NA          NA          NA
## 2             NA                  NA           NA          NA          NA
## 3             NA                  NA           NA          NA        5263
## 4             NA                  NA           NA          NA          NA
## 5             NA                  NA           NA          NA        5210
## 6             NA                  NA           NA          NA        5131
##   some_deaths2
## 1           NA
## 2           NA
## 3         5263
## 4           NA
## 5         5210
## 6         5131
```

## Missing Values


```r
NA
```

```
## [1] NA
```

## Missing Values

```r
is.na(NA)
```

```
## [1] TRUE
```


```r
is.null(NULL)
```

```
## [1] TRUE
```

## Combining Data

```r
# using the readr package
c1 = read_csv('../data/concat_1.csv')
```

```
## Parsed with column specification:
## cols(
##   A = col_character(),
##   B = col_character(),
##   C = col_character(),
##   D = col_character()
## )
```

```r
c2 = read_csv('../data/concat_2.csv')
```

```
## Parsed with column specification:
## cols(
##   A = col_character(),
##   B = col_character(),
##   C = col_character(),
##   D = col_character()
## )
```

## Combining Data


```r
rbind(c1, c2)
```

```
## # A tibble: 8 × 4
##       A     B     C     D
## * <chr> <chr> <chr> <chr>
## 1    a0    b0    c0    d0
## 2    a1    b1    c1    d1
## 3    a2    b2    c2    d2
## 4    a3    b3    c3    d3
## 5    a4    b4    c4    d4
## 6    a5    b5    c5    d5
## 7    a6    b6    c6    d6
## 8    a7    b7    c7    d7
```

## Combining Data


```r
cbind(c1, c2)
```

```
##    A  B  C  D  A  B  C  D
## 1 a0 b0 c0 d0 a4 b4 c4 d4
## 2 a1 b1 c1 d1 a5 b5 c5 d5
## 3 a2 b2 c2 d2 a6 b6 c6 d6
## 4 a3 b3 c3 d3 a7 b7 c7 d7
```

## Combining Data

```r
survey_visited = read_csv('../data/survey_visited.csv')
```

```
## Parsed with column specification:
## cols(
##   ident = col_integer(),
##   site = col_character(),
##   dated = col_date(format = "")
## )
```

```r
survey_site = read_csv('../data/survey_site.csv')
```

```
## Parsed with column specification:
## cols(
##   name = col_character(),
##   lat = col_double(),
##   long = col_double()
## )
```

## Combining Data

```r
merge(x = survey_visited, y = survey_site,
      by.x = 'site', by.y = 'name',
      all.x = TRUE, all.y = TRUE)
```

```
##    site ident      dated    lat    long
## 1  DR-1   619 1927-02-08 -49.85 -128.57
## 2  DR-1   622 1927-02-10 -49.85 -128.57
## 3  DR-1   844 1932-03-22 -49.85 -128.57
## 4  DR-3   734 1939-01-07 -47.15 -126.72
## 5  DR-3   735 1930-01-12 -47.15 -126.72
## 6  DR-3   751 1930-02-26 -47.15 -126.72
## 7  DR-3   752       <NA> -47.15 -126.72
## 8 MSK-4   837 1932-01-14 -48.87 -123.40
```

## Combining Data - tidyverse

```r
# from dplyr
survey_visited %>%
    full_join(survey_site, by = c('site' = 'name'))
```

```
## # A tibble: 8 × 5
##   ident  site      dated    lat    long
##   <int> <chr>     <date>  <dbl>   <dbl>
## 1   619  DR-1 1927-02-08 -49.85 -128.57
## 2   622  DR-1 1927-02-10 -49.85 -128.57
## 3   734  DR-3 1939-01-07 -47.15 -126.72
## 4   735  DR-3 1930-01-12 -47.15 -126.72
## 5   751  DR-3 1930-02-26 -47.15 -126.72
## 6   752  DR-3       <NA> -47.15 -126.72
## 7   837 MSK-4 1932-01-14 -48.87 -123.40
## 8   844  DR-1 1932-03-22 -49.85 -128.57
```

```r
# left_join
# right_join
# innder_join
```


## Vectored operations

```r
gapminder <- read_tsv('../data/gapminder.tsv')
```

```
## Parsed with column specification:
## cols(
##   country = col_character(),
##   continent = col_character(),
##   year = col_integer(),
##   lifeExp = col_double(),
##   pop = col_integer(),
##   gdpPercap = col_double()
## )
```


```r
lapply(X = gapminder, FUN = class)
```

```
## $country
## [1] "character"
## 
## $continent
## [1] "character"
## 
## $year
## [1] "integer"
## 
## $lifeExp
## [1] "numeric"
## 
## $pop
## [1] "integer"
## 
## $gdpPercap
## [1] "numeric"
```

## Vectored operations


```r
# margin 1 is rows, 2 is columns
gapminder$lifeExpPerCap <- apply(
    X = gapminder, MARGIN = 1,
    FUN = function(x){as.numeric(x['lifeExp']) / as.numeric(x['pop'])})
```

## Vectored operations


```r
calc_life_exp_per_cap <- function(row_of_data){
    life_exp_per_cap <- as.numeric(row_of_data['lifeExp']) / as.numeric(row_of_data['pop'])
    return(life_exp_per_cap)
}
gapminder$lifeExpPerCap2 <- apply(X = gapminder, MARGIN = 1, FUN = calc_life_exp_per_cap)
```

## Vectored operations


```r
all(gapminder$lifeExpPerCap == gapminder$lifeExpPerCap2)
```

```
## [1] TRUE
```

## Grouped operations

- I just use `dplyr` and the tidyverse stack for this
- Jared Lander has a talk about performance between base-r and various packages:
    - Making R Go Faster And Bigger
    - https://www.youtube.com/watch?v=jsK-tJWA46Q

## Grouped operations

<img src='https://github.com/chendaniely/2016-pydata-dc-python_useRs/raw/master/img/jared_r_benches.png', height=500>

## Grouped operations


```r
gapminder %>%
    group_by(year) %>%
    summarize(avg_lifeExp = mean(lifeExp),
              avg_gdpPercap = mean(gdpPercap))
```

```
## # A tibble: 12 × 3
##     year avg_lifeExp avg_gdpPercap
##    <int>       <dbl>         <dbl>
## 1   1952    49.05762      3725.276
## 2   1957    51.50740      4299.408
## 3   1962    53.60925      4725.812
## 4   1967    55.67829      5483.653
## 5   1972    57.64739      6770.083
## 6   1977    59.57016      7313.166
## 7   1982    61.53320      7518.902
## 8   1987    63.21261      7900.920
## 9   1992    64.16034      8158.609
## 10  1997    65.01468      9090.175
## 11  2002    65.69492      9917.848
## 12  2007    67.00742     11680.072
```

## Fit a model

Nothing to import!

## Fit a model


```r
model <- lm(formula = lifeExp ~ gdpPercap, data = gapminder)
```

## Fit a model


```r
summary(model)
```

```
## 
## Call:
## lm(formula = lifeExp ~ gdpPercap, data = gapminder)
## 
## Residuals:
##     Min      1Q  Median      3Q     Max 
## -82.754  -7.758   2.176   8.225  18.426 
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)    
## (Intercept) 5.396e+01  3.150e-01  171.29   <2e-16 ***
## gdpPercap   7.649e-04  2.579e-05   29.66   <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 10.49 on 1702 degrees of freedom
## Multiple R-squared:  0.3407,	Adjusted R-squared:  0.3403 
## F-statistic: 879.6 on 1 and 1702 DF,  p-value: < 2.2e-16
```

## Fit a model

- Broom package by David Robinson, PhD
    - https://github.com/dgrtwo/broom
    - https://www.youtube.com/watch?v=7VGPUBWGv6g


```r
library(broom)

tidy(model)
```

```
##          term     estimate    std.error statistic       p.value
## 1 (Intercept) 5.395556e+01 3.149949e-01 171.29025  0.000000e+00
## 2   gdpPercap 7.648826e-04 2.579039e-05  29.65766 3.565724e-156
```

## More tidyverse things

- Hadley Wickham, PhD
    - http://vita.had.co.nz/papers/tidy-data.pdf
    - https://cran.rstudio.com/web/packages/dplyr/vignettes/introduction.html
    - https://cran.rstudio.com/web/packages/dplyr/vignettes/
    - `tidyr` `dplyr` `purrr`

## These slides

`knitr` library and `RMarkdown`

```
---
title: "useRs"
author: "Daniel Chen"
output:
  ioslides_presentation:
    keep_md: yes
    widescreen: yes
  slidy_presentation: default
---
```
