---
title: "CASE STUDY TITLE"
author: "YOUR NAME"
date: "May 10, 2018"
output:
  html_document:  
    keep_md: true
    toc: true
    toc_float: true
    code_folding: hide
    fig_height: 6
    fig_width: 12
    fig_align: 'center'
editor_options: 
  chunk_output_type: console
---







```r
datat5 <- read_csv("hrvgdp.csv")
newdatat5 <- filter(datat5, Year == 2013) %>%
  na.omit()

continents <- countrycode(newdatat5$State, "country.name", "continent")

c <- merge(newdatat5, continents)

p1 <-ggplot(c, aes( GDP, HR, size = Pop, color = y)) +
  geom_point()

p1
```

![](Task6_files/figure-html/unnamed-chunk-2-1.png)<!-- -->


This is a plot I attempted to recreate from the website comparing the level to which countries respect human rights to their GDP per capita. Some issues that have shown up are scale on the population side of the legend as well as correct color coding of the countries which will have to be fixed



```r
p2 <- ggplot(child_mortality, aes(year, child_mort))+
          geom_line()
p2
```

![](Task6_files/figure-html/unnamed-chunk-3-1.png)<!-- -->

Here is the plot I was able to produce on child mortality rates, it too needs a lot of cleaning but does show a declining trend.


