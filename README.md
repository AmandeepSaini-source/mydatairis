# Loading libraries
library(stats)
library(dplyr)
library(ggplot2)
library(ggfortify) 
library(cluster)
library(tidyverse)
library(factoextra)
library(NbClust)
# Unsupervised learning hence converting iris into unlabelled data
View(iris)
mydata <- select(iris,c(1,2,3,4))

# WSS plot to choose the optimum number of clusters
set.seed(123)
fviz_nbclust(mydata, kmeans,method = "wss")
# Optimum number of clusters is 2

# k-Means Cluster
KM = kmeans(mydata,2)

# Evaluating Cluster Analysis
# Cluster Plot
autoplot(KM,mydata,frame = TRUE) 

