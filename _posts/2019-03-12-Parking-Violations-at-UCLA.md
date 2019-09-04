---
layout:     post
title:      Parking Violations at UCLA
date:       2019-09-18
summary:    Where, when, and why are students getting ticketed?
categories: jekyll pixyll
---


Where, when, and why are students getting ticketed?
---------------------------------------------------------------

Picture this: you're walking home on a bright, sunny UCLA day. Life is
great.

That is until you find that dreaded slip on your car's front dash: *a
parking ticket*.

For many students with cars, parking is daily hassle on the residential
side of Westwood. With rising rates of congestion<sup>1</sup> and a lack
of infrastructure to handle more car owners, the competition for students to
fit cars wherever possible increases. I myself, along with most other
drivers in Westwood, have been face to face with a ticket at some point
or another. This led me to the question: how are students getting
ticketed, and are there possible ways to minimizes such tickets?

Utilizing Los Angeles's Open Data Initiative<sup>2</sup>, started by
Mayor Eric Garceti in 2013, we can collect every parking ticket handed
out in Los Angeles since the beginning of 2015. The raw data set
contains about nine million parking tickets total. Using the data's
longitude and latitude columns, we can subset our data to just the
village of Westwood.

From January 1st, 2015 to December 31st, 2018, there have been some
**52,447** tickets written for over fifty different type of parking
violations in our local area. The raw data set is quite messy, and can
use some further investigation.

For instance; several of the violation descriptions and street names are
often mismatched, and need to be cleaned and aggregated.

<table>
<thead>
<tr class="header">
<th>Violation Description</th>
<th>Street Address</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>DISABLED PARKING/NO DP ID</td>
<td>515 S LAND FAIR AVE</td>
</tr>
<tr class="even">
<td>DISABLED PARKING/ OBSTRUCT ACCESS</td>
<td>515 LANDFAIR AVENUE</td>
</tr>
<tr class="odd">
<td>DISABLED PARKING/BOUNDARIES</td>
<td>515 LANDFAIR</td>
</tr>
</tbody>
</table>

The overall trend in ticketed violations is on the rise. From the start
of 2015 to the beginning of 2018, there was a rise in tickets given by a
little over 9%. Westwood is already one of the most ticketed
neighborhoods in all of Los Angeles <sup>3</sup>.

Types of tickets
----------------

Of the 50 to 70 different variations of parking violations (depending on
how you group them) the top 10 violation categories account for 95% of
the total tickets given. We will focus on the top 6 categories, which
account for 86% of parking ticket violations alone and hold at least 3%
of the total share of tickets.

    ## # A tibble: 6 x 3
    ##   violation_category       counts percent_total
    ##   <chr>                     <int>         <dbl>
    ## 1 NO PARK/STREET CLEAN      21223         39.1
    ## 2 PARKED OVER TIME LIMIT    14303         26.4
    ## 3 DISPLAY OF PLATES / TABS   4082          7.52
    ## 4 METER EXPIRED              2503          4.61
    ## 5 REFERENTIAL PARKING        2329          4.29
    ## 6 RED ZONE                   1983          3.65

The majority of parking tickets (40%) are due to street cleaning
violations.

### Most common violations

Talk about commonly ticket streets for categories

When are tickets given?
-----------------------
![image](/assets/images/violations_per_day.png){: .center-image }

Now lets look at the *time* that violations happen. First, we notice
right away that Thursdays and Fridays are when a majority of tickets are
given out. Almost 58% of parking tickets occur on Thursday and Friday.
In Westwood, all street cleaning happens on these two days of the week.

![image](/assets/images/violations_per_hour.png){: .center-image }




Additionally, we see that Sundays have the least violations. This is due
to many streets with two hour parking limits waiving this condition on
Sundays.

Street cleaning as a source of ticketing become even more apparent when
we look at the time of day tickets are being given. A staggering amount
of tickets are given bright and early at 8 AM, an uncomfortable time of
day for many sleep deprived UCLA students.




There are also bumps in tickets given from 9 AM to 11AM, as well as 3 PM
to 5PM. \* explain this \*

Where are violations happening?
-------------------------------


![image](/assets/images/heatmap.png){: .center-image }

We can see a concentration of






How much money is being made from Westwood?
-------------------------------------------

From 2015 to 2019, $3,702,125 in revenuw has been made from the Westwood
area.

Ways we can mitigate parking tickets in Westwood
------------------------------------------------

1.  Set reminders, you can use
    [SpotAngels](https://www.spotangels.com/#id=296636102&address=424%20Veteran%20Ave%20Los%20Angeles)

2.  Park your car in other designated parking areas, including: Veteran
    Avenue Parking lot next to blank a

3.  Additional Signage should be placed @ \_\_\_\_\_ , , , etc.
