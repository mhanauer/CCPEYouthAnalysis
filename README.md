---
title: "Enhanced Results"
output:
  pdf_document: default
  html_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Load up CCPE youth data sets
```{r}
setwd("S:/Indiana Research & Evaluation/CCPE/CCPE SPSS - Datasets/YOUTH Datasets")
BaseYouth = read.csv("Baseline CCPE GPRA Youth.csv", header= TRUE, na.strings = c(97,98,99))
ReassessYouth = read.csv("Reassess 3M CCPE GPRA Youth.csv", header = TRUE, na.strings = c(97,98,99))
```
Ok should be able to merge them on ID then subset

Need to subset if Interview type is two get rid of it
```{r}
dim(BaseYouth)
dim(ReassessYouth)
head(BaseYouth)
head(ReassessYouth)


BaseYouth = subset(BaseYouth, INTTYPE != 2)
ReassessYouth = subset(ReassessYouth, INTTYPE != 2)


Base_Reassess_Youth = merge(BaseYouth, ReassessYouth, by = "PARTID")
dim(Base_Reassess_Youth)

```

```{r}
# Get the percentage change for youth on each risk and outcome variable
mean((Base_Reassess_Youth$RSKALC.y-Base_Reassess_Youth$RSKALC.x)/Base_Reassess_Youth$RSKALC.x, na.rm = TRUE)

mean((Base_Reassess_Youth$RSKCIG.y-Base_Reassess_Youth$RSKCIG.x)/Base_Reassess_Youth$RSKCIG.x, na.rm = TRUE)

mean((Base_Reassess_Youth$RSKMJ.y-Base_Reassess_Youth$RSKMJ.x)/Base_Reassess_Youth$RSKMJ.x, na.rm = TRUE)

mean((Base_Reassess_Youth$RSKANYSEX_UNP.y-Base_Reassess_Youth$RSKANYSEX_UNP.x)/Base_Reassess_Youth$RSKMJ.x, na.rm = TRUE)
```







