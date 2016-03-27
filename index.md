# Weight Lifting Tekkers Analysis
mail@darrenbishop.com  
27 March 2016  


```r
library(knitr)
library(dplyr)
library(Hmisc)
library(lubridate)
library(ggplot2)
library(gridExtra)
library(scales)
library(caret)
library(rpart.plot)
library(forecast)

opts_chunk$set(message=FALSE, fig.path="figures/", fig.width=10, fig.align = "center")
```


```r
load.file <- function(filename, url) {
    if (!file.exists(filename)) {
        download.file(url, destfile = filename)
    }
    read.csv(filename)
}

training = load.file("pml-training.csv", "https://d396qusza40orc.cloudfront.net/predmachlearn/pml-training.csv")
testing = load.file("pml-testing.csv", "https://d396qusza40orc.cloudfront.net/predmachlearn/pml-testing.csv")
```
