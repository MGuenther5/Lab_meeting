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
library(ggplot2)
library(ggmap)

#Stream GPS locations
#AntelopePark	-96.670658	40.795535
#UnionPlaza	-96.688154	40.811577
#RickmansRun	-96.62225	40.773502
#OakCreek	-98.876281	41.300251
#ChadronCreek	-103.012753	42.717188
#NVP1	-100.025519	42.782313
#HazelCreek	-99.939084	42.76752
#ArrowheadCreek	-100.116522	42.796752
#MiddleCreek	-100.056588	42.790673
#S. Branch Middle Loop	-101.45589	42.090479

##Create data frame with lat and long from GPS points
d<-data.frame(lat=c(4.795535, 40.811577, 40.773502, 41.300251, 42.717188, 42.782313, 42.76752, 42.796752, 42.790673, 42.090479),lon=c(-96.670658, -96.688154, -96.62225, -98.876281, -103.012753, -100.025519, -99.939084, -100.116522, -100.056588, -101.45589))

NEmap<-get_map("Nebraska,USA", zoom=7)
p<-ggmap(NEmap)
p<-p+geom_point(data=d, aes(x=lon,y=lat))
p
ggplot_build(p)


