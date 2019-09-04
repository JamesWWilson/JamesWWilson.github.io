---
layout:     post
title:      Parking Violations at UCLA
date:       2019-09-08
summary:    Where, when, and why are students getting ticketed?
categories:
---

A deep dive into how UCLA students get ticketed in Westwood.
---------------------------------------------------------------

![Heat map](/assets/images/heatmap.png){:class="img-responsive" height="400px" width="400px"}

Picture this: you're a UCLA student walking home on a bright, sunny
SoCal day. Life is great.

That is, until you find that dreaded slip on your car's front dash: *a
parking ticket*.

For many students with cars, parking is a daily hassle on the
residential side of Westwood. With rising rates of
congestion<sup>1</sup> and a lack of infrastructure to handle more car
owners, the competition for students to fit cars wherever possible
increases. I myself, along with many other drivers in Westwood, have
been face to face with a ticket at some point or another. This lead me
to the question: how are students getting ticketed, and are there
possible ways to minimize such tickets?

(Note: I am taking the assumption that *a large majority* of those living
  in this part of Westwood are students, having lived in the area for
  four years.)

Utilizing Los Angeles's Open Data Initiative<sup>2</sup>, started by
Mayor Eric Garceti in 2013, we can collect every parking ticket handed
out in the City of Los Angeles since the beginning of 2015. The raw data
set contains about nine million parking tickets total. Using the data's
longitude and latitude columns, we can subset our data to just the
village of Westwood.

From January 1st, 2015 to December 31st, 2018, there have been some
**52,447** tickets written for over fifty different type of parking
violations in Westwood's local area. The raw data set is quite messy,
and needs some further investigation.

For instance; several of the violation descriptions and street names are
mismatched, and need to be corrected and aggregated.

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

Of the 50 to 70 different categories of parking violations (depending on
how you categorize them) the top 10 violation categories account for 95%
of the total tickets given. We will focus on the top 6 categories, which
still account for 86% of parking ticket violations alone, and hold at
least 3% of the total share of tickets.

<table>
<thead>
<tr class="header">
<th>Violation Category</th>
<th>Count of Violations</th>
<th>Percent of Total</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>NO PARK/STREET CLEAN</td>
<td>20965</td>
<td>39.97</td>
</tr>
<tr class="even">
<td>PARKED OVER TIME LIMIT</td>
<td>14149</td>
<td>26.98</td>
</tr>
<tr class="odd">
<td>DISPLAY OF PLATES/ TABS</td>
<td>3868</td>
<td>7.38</td>
</tr>
<tr class="even">
<td>METER EXPIRED</td>
<td>2479</td>
<td>4.73</td>
</tr>
<tr class="odd">
<td>RED ZONE</td>
<td>1907</td>
<td>3.64</td>
</tr>
<tr class="even">
<td>PARKED ON SIDEWALK</td>
<td>1851</td>
<td>3.53</td>
</tr>
</tbody>
</table>

The majority of parking tickets, nearly 40%, are due to street cleaning
violations. We can get even more granular and see which of these
violations are most common per street in Westwood.

![image](/assets/images/street_violations.jpeg){: .center-image }


The dreaded Landfair Avenue still holds the title of being the worst
street in Westwood, namely due to its rough roads, tandem parking, and
top count of parking violations. Le Conte, Montana, and Weyburn Ave have
much stricter parking requirements then other streets, resulting in far
fewer parking violations.

Some key takeaways: - Gayley and Levering both have meters on portions
of their streets that inflict their fair amount of tickets. - ALL
streets suffer at some point from street cleaning violations, as well as
cars parked over the time limit.

When are tickets given?
-----------------------

Now lets look at the *time* that violations happen. First, we notice
right away that Thursdays and Fridays are when a majority of tickets are
given out. Almost 58% of parking tickets occur on Thursday and Friday.
In Westwood, all street cleaning happens on these two days of the week.

![image](/assets/images/violations_per_day.png){: .center-image }

Additionally, we see that Sundays have the least violations. This is
likely due to many streets that normally have two hour parking limits
waiving this condition on Sundays.

It becomes even more apparent that street cleaning is the main source of
ticketing when we look at the time of day tickets are being given. A
staggering amount of tickets are given bright and early at 8 AM, an
uncomfortable time of day for many sleep deprived UCLA students.

![image](/assets/images/violations_per_hour.png){: .center-image }

Street cleaning continues until 10 for Westwood streets. So why are
there no drop-in violations until 12ish? A second round of ticketing
starts up at 10 AM for parking over the time limit, which is 2 hours
every day (except Sunday) from 8 AM to 6 PM. After seeing every car at 8
AM, street patrols will come back around and mark up any car still left
on the street from that previous time. From 3-5 PM, the resulting spike
comes once again from another round of time limit violations.

Avoiding the Street Cleaning Ticket
-----------------------------------









How much money does the city make from Westwood tickets?
--------------------------------------------------------

Ticket prices have continued to climb over the years. At present, five
of the six violations we have discussed cost over $58 per violation.
Given the already rising tuition, rent, and general fees associated with
being a UCLA student, having to contribute to pay an additional fee can
put one over the edge.

![image](/assets/images/costs.png){: .center-image }

From 2015 to the end of 2018, *$3,702,125* in revenue has been made from
the Westwood area in tickets. This is a huge amount of money to be taken
from the Westwood general area, largely due to the poor infrastructure
currently available.

Whether its an increase parking, a decrease in demand for cars, or a
change in the time associated with street cleaning, officials should be
looking to solve the root problem instead of harassing its citizens
with fines.



Citations
---------

[Data](https://data.lacity.org/A-Well-Run-City/Parking-Citations/wjz9-h9np)

Code

1 [Traffic Congestion in Los Angeles will get Worse](https://www.citywatchla.com/index.php/2016-01-01-13-17-00/los-angeles/17537-traffic-congestion-in-los-angeles-will-get-worse)

2 [Los Angeles's Open Data Initiative](https://data.lacity.org/)

3 [Mapping the Most Parking-Ticketed Blocks in All of Los Angeles](https://la.curbed.com/2014/12/30/10006936/mapping-the-most-parkingticketed-blocks-in-all-of-los-angeles#more)
