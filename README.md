# sample1

library(ggmap)
library(tidyverse)
library(dplyr)
library(mapview)
library(sf)

Banad <- filter(SomNig, disorder_type =="Political violence", year == 2020, admin1 == "Banadir",) %>% select(disorder_type, year, admin1, latitude, longitude)   

names(Banad)
head(Banad, 250)


library(mapview)
library(sf)
mymap1 <- st_as_sf(Banad, coords = c("longitude", "latitude"), crs = 4326)
mapview(mymap1)


library(mapview)
mymap1 <- st_as_sf(Banad, coords = c("longitude", "latitude"), crs = 4326)
mapview(mymap1, color="black", col.regions="red",
        alpha.regions=0.5, legend = FALSE,
        homebutton = FALSE, map.types = "OpenStreetMap" )
        
