# Lab_meeting
#A file to play with


#Mirae Guenther
#August 20, 2018
#mapping stream locations

#Packages: ggmap, ggplot2

#clear R's brain
rm(list=ls())
#where is R looking
getwd()
#tell R where to look
setwd("/Users/mguenther5/Desktop/R data")
#confirm it's looking there
getwd()

#New attempt from online resource
library(tidyverse)
library(ggplot2)
library(ggmap)


##Create data frame with lat and long from GPS points
d<-data.frame(lat=c(4.795535, 40.811577, 40.773502, 41.300251, 42.717188, 42.782313, 42.76752, 42.796752, 42.790673, 42.090479),lon=c(-96.670658, -96.688154, -96.62225, -98.876281, -103.012753, -100.025519, -99.939084, -100.116522, -100.056588, -101.45589))

NEmap<-get_map("Nebraska,USA", zoom=7)
p<-ggmap(NEmap)
p<-p+geom_point(data=d, aes(x=lon,y=lat))
p
ggplot_build(p)

#and that's the end, there isn't any more
