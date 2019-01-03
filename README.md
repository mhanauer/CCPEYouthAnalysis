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
BaseYouth = read.csv("Baseline CCPE GPRA Youth.csv", header= TRUE)
ReassessYouth = read.csv("Reassess 3M CCPE GPRA Youth.csv", header = TRUE)
```
Ok should be able to merge them on ID then subset
```{r}
dim(BaseYouth)
dim(ReassessYouth)
head(BaseYouth)
head(ReassessYouth)
BaseYouth$INTDUR
ReassessYouth$INTDUR

Base_Reassess_Youth = merge(BaseYouth, ReassessYouth, by = "PARTID")
dim(Base_Reassess_Youth)

# Get the percentage change for youth on each risk and outcome variable
Base_Reassess_Youth


```
```{r}

```







