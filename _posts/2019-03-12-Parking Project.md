---
title: "Parking Violations @ UCLA"
author: "James Wilson"
date: "1/21/2019"
output: html_document
---

```{r setup, include=FALSE}
### SET UP ----
knitr::opts_chunk$set(echo = TRUE)

#Remove Objects
rm(list = ls())

#Clear Memory
gc(reset = TRUE)

#Set Working Directory
setwd("/Users/JamesW/Desktop/Personal Projects/Data Science Projects/Parking Project")

#Load Packages
require(stringr)
require(tidyverse)
require(dplyr)		#Data frame functions
require(data.table)
require(dtplyr)
require(stringi)
require(ggplot2)		#Graphics
require(lubridate)
require(readxl)
require(reshape2)
require(rgdal)
require(ggmap)
require(ggthemes)
require(viridis) #devtools::install_github("sjmgarnier/viridis")
require(scales)
require(grid)
require(gridExtra)


# Overall Analysis -----
WWParking <- readRDS("WWParking.rds")
attach(WWParking)

```

# Parking Violations at UCLA 
## Where, when, and why are students getting ticketed in Westwood?

Picture this: you're walking home on a bright, sunny UCLA day. Life is great.

That is until you find that dreaded slip on your car's front dash: a parking ticket. 

For many students with cars, parking is daily hassle on the residential side of Westwood. With rising rates of congestion* and a lack of infrasture to handle more car owners, the competition for students to fit cars wherever possible increases. I myself, along with most other drivers in Westwood, have been face to face with a ticket at some point or another. This led me to the question: how are students getting ticketed, and are there possible ways to minimizes such tickets? 

Utilizing Los Angeles's Open Data Initiative, started by Mayor Eric Garceti in 2013, we can collect every parking ticket handed out in Los Angeles since the beginning of 2015. The raw data set contains about nine million parking tickets total. Using the data's longitude and latiutde colunmns, we can subset our data to just the village of Westwood. 

From January 1st, 2015 to December 31st, 2018, there have been some 52,447 tickets written for over fifty different type of parking violations in our local area. The raw data set is quite messy, and can use some further investigation. 

For instance; several of the violation descriptions and street names are often mismtached, and need to be cleaned and aggregated.  

Violation Description | Street Address
------------- | -------------
DISABLED PARKING/NO DP ID | 515 S LAND FAIR AVE
DISABLED PARKING/ OBSTRUCT ACCESS | 515 LANDFAIR AVENUE
DISABLED PARKING/BOUNDARIES | 515 LANDFAIR

The overall trend in ticked violations is on the rise. From the start of 2015 to the beginning of 2018, there was a rise in tickets by a little over 9%. Westwood is already one of the most ticketed neighborhoods in all of Los Angeles [cite]. 


## Types of tickets 

Of the 50 to 70 different variations of parking violations (depending on how you group them) the top 10 violation categories account for 95% of the total tickets given. We will focus on the top 6 categories, which account for 86% of parking ticket violations alone and hold at least 3% of the total share of tickets. 

```{r, echo = F, warning=F, fig.align = 'center'}
violations_stats <- WWParking %>% 
  group_by(violation_category) %>%
  summarize(counts = n()) %>% arrange(desc(counts)) %>%
  mutate(percent_total = counts / sum(counts) * 100)
violations_stats[1:6,] # use this table
```

The majority of parking tickets (40%) are due to street cleaning violations. 


### Most common violations 
```{r, echo = F, warning=F, fig.align = 'center'}
### common violations graphic per street 



```

# talk about commonly ticket streets for categories 



## When are tickets given? 

Now lets look at the _time_ that violations happen. First, we notice right away that Thursdays and Fridays are when a majority of tickets are given out. Almost 58% of parking tickets occur on Thursday and Friday. In Westwood, all street cleaning happens on these two days of the week. 

```{r, echo = F, warning=F,fig.align = 'center'}
WWParking$day <- weekdays(as.Date(WWParking$date))
days_of_week=factor(c("Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"))

violations_per_day = ggplot(WWParking, aes(day)) + geom_bar(fill = "#2774AE") +
  labs(x = "Weekdays", y = "Number of Violations per Day", title = "Violations per Day") +
  scale_x_discrete(limits = days_of_week) + 
  theme_bw() + 
  theme(panel.grid.major=element_line(color="white"), 
        text=element_text(family="Helvetica"), 
        legend.position="bottom",
        plot.title = element_text(size = rel(2.0)),
        axis.text.x = element_text(size= rel(1.5), angle = 45, hjust=1),
        axis.text.y = element_text(size= rel(2.0)))
violations_per_day
```

Additionally, we see that Sundays have the least violations. This is due to many streets with two hour parking limits waiving this condition on Sundays. 

Street cleaning as a source of ticketing become even more apparent when we look at the time of day tickets are being given. A staggering amount of tickets are given bright and early at 8 AM, an uncomfortable time of day for many sleep deprived UCLA students. 


```{r, echo = F, warning=F, fig.align = 'center'}
violations_per_hour = ggplot(WWParking, aes(hour(timestamp))) + geom_bar(fill = "#2774AE") +
  labs(x = "Hour of Day", y = "Number of Violations per Hour", title = "Violations per Hour") +
  scale_x_discrete(limits = c(0:24)) + 
  theme_bw() + 
  theme(panel.grid.major=element_line(color="white"), 
        text=element_text(family="Helvetica Neue"), 
        legend.position="bottom",
        plot.title = element_text(size = rel(2.0)),
        axis.text.x = element_text(size= rel(1.5), 
                                   angle = 45, 
                                   hjust=1),
        axis.text.y = element_text(size= rel(2.0)))
violations_per_hour
```


There are also bumps in tickets given from 9 AM to 11AM, as well as 3 PM to 5PM. 
* explain this * 



## Where are violations happening? 



```{r, echo = F, warning=F, fig.align = 'center'}
### Bar chart of streets with highest count

```

```{r, echo = F, warning=F, fig.align = 'center'}
### Table of addresses with highest count 

```

```{r, include = FALSE}
location_cnt <- WWParking %>% group_by(longitude, latitude) %>% tally()
register_google(key = "AIzaSyDHitNn2oqk51nRBF7jY_AQBkB7LFL9Tr8")
ggmap_credentials()
```

```{r, echo = F, warning=F, fig.align = 'center'}
westwood <- get_map(location=c(-118.451253, 34.066312),color="bw", crop=FALSE, zoom=16)
gg <- ggmap(westwood)
heatmap <- ggmap(westwood, extent = "panel", maprange=FALSE) +
  geom_density2d(data = WWParking, aes(x = longitude, y = latitude)) +
  stat_density2d(data = WWParking, aes(x = longitude, y = latitude, fill = ..level.., alpha = ..level..),
                 size = 0.01, bins = 16, geom = 'polygon') +
  scale_fill_gradient(low = "green", high = "red") +
  scale_alpha(range = c(0.00, 0.25), guide = FALSE) +
  theme(legend.position = "none", 
        axis.title = element_blank(), 
        axis.text.x = element_blank(),
        axis.text.y = element_blank(),
        text = element_text(size = 12)) + 
    labs(title = "Heatmap of Parking Violatons 2015-2018")
heatmap

```

```{r, echo = F, warning=F, fig.align = 'center'}
### Visualize costs per ticket 



```


## How much money is being made from Westwood?

From 2015 to 2019, $3,702,125 in revenuw has been made from the Westwood area. 


## Ways we can mitigate parking tickets in Westwood 

1) Set reminders, you can use SpotAngels
https://www.spotangels.com/#id=296636102&address=424%20Veteran%20Ave%20Los%20Angeles


2) Park your car in other designated parking areas, including:
  Veteran Avenue
  Parking lot next to blank a
  
  
3) Additional Signage should be placed @ _____ ,  ,  , etc. 




















