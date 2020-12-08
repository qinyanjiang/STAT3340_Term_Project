

---
title: "Stat3340 Final Project: Real Estate Regression Model"
author: "Nicole Torrie & Qinyan Jiang"
date: "07/12/2020"
output: html_document
---
```{r setup, include=FALSE}
library(dplyr)
knitr::opts_chunk$set(echo = TRUE)
```

## 1 - Abstract
## 2 - Introduction
## 3 - Data Description
Add and view Real Estate Data
```{r}
Data <- read.csv("Real estate.csv")  
attach(Data)
head(Data)
```


Basic Map with scalebar
```{r}
# gene world map
world <- ne_countries(scale = "medium", returnclass = "sf")
ggplot(data = world) +
  geom_sf() +
  labs( x = "Longitude", y = "Latitude") +
  coord_sf(xlim = c(121.460,121.58), ylim = c(24.92,25.023), expand = FALSE) +
  annotation_scale(location = "bl", width_hint = 0.5) +
  annotation_north_arrow(location = "bl", which_north = "true", 
                         pad_x = unit(0.02, "in"), pad_y = unit(0.3, "in"),
                         style = north_arrow_fancy_orienteering) +
  geom_point(data = Data, aes(x = X6.longitude, y =X5.latitude ),col="red", size=2)+
  theme_bw()

```


Detailed map
```{r}
qmplot(X6.longitude, X5.latitude, data = Data, maptype = "toner-lite", color = I("red"))+
         labs( x = "Longitude", y = "Latitude") 

```
### 3.1 - Data Sources
### 3.2 - Real Estate
### 3.3 - Additional data point
## 4 - Methods
### 4.1 Multi-linear Regression
### 4.2 Model Adequacy
### 4.3 Model Validation
## 5 - Results
## 6 - Conclusion



