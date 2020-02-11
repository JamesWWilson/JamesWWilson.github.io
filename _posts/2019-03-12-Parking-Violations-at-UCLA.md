---
title: "Parking Violations at UCLA"
date: '2019-10-07'
layout: post
summary: Where, when, and why are students getting ticketed?
categories: null
---

A deep dive into how students get ticketed in Westwood.
---------------------------------------------------------------

{:refdef: style="text-align: center;"}
![Parking Ticket Picture](/assets/images/no_parking_photo.jpeg)
{: refdef}

Picture this: you're a UCLA student walking home on a bright, sunny
SoCal day. Life is great.

That is, until you find that dreaded slip on your car's front dash: *a
parking ticket*.

For many students with cars, parking is a daily hassle on the
residential side of Westwood. With rising rates of
congestion<sup>1</sup> and a lack of infrastructure to handle more car
owners, the competition increases for students to fit cars wherever possible.
I myself, along with many other drivers in Westwood, have
been face to face with a ticket at some point or another. This lead me
to the question: how are Westwood residents getting ticketed, and are there
possible ways to minimize such tickets?

Utilizing Los Angeles's Open Data Initiative<sup>2</sup>, started by
Mayor Eric Garceti in 2013, we can collect every parking ticket handed
out in the City of Los Angeles since the beginning of 2015. The raw data
set contains upwards of nine million parking tickets total. Using the data's
longitude and latitude variables, we can subset our data to just the
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


{:refdef: style="text-align: center; max-height: 80%;"}
![Timeseries of Tickets](/assets/images/______.png)
{: refdef}

Where are tickets given?
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
violations. We can get even more granular and see which
violations are most common per street in Westwood.

{:refdef: style="text-align: center;"}
![image](/assets/images/street_violations.jpeg){: .center-image }
{: refdef}


The dreaded Landfair Avenue still holds the title of being the worst
street in Westwood, namely due to its rough roads, tandem parking, and
top count of parking violations. Le Conte Ave and Montana Ave have
much stricter parking requirements then other streets, resulting in far
fewer parking violations. Gayley and Levering both have meters on portions
of their streets that inflict their fair amount of tickets. All streets suffer at
some point from street cleaning violations, as well as cars parked over the time limit.

We can create a heatmap of the tickets given to create a better visual of where
hotspots for ticketing occurs:

{:refdef: style="text-align: center;"}
![Heat Map](/assets/images/heatmap.png)
{: refdef}

```
code for plot
```

Overall, a high density of violations seems to occur around __, ___, ___,...


Subsetting for the type of violation lets us get more granular:



t1 _ t2


t3 _ t4





What street you live on makes a huge difference for how significant ticketing will affect you, as well as
what types of tickets will bother you.




When are tickets given?
-----------------------

Now lets look at the *time* that violations happen. First, we notice
right away that Thursdays and Fridays are when a majority of tickets are
given out. Almost 58% of parking tickets occur on Thursday and Friday.
In Westwood, all street cleaning happens on these two days of the week.

{:refdef: style="text-align: center;"}
![image](/assets/images/violations_per_day.png){: .center-image }
{: refdef}

Additionally, we see that Sundays have the least violations. This is
likely due to many streets normally having two hour parking limits, which are
waived on Sundays.

It becomes even more apparent that street cleaning is the main source of
ticketing when we look at the time of day tickets are being given. A
staggering amount of tickets are given bright and early at 8 AM, an
uncomfortable time of day for many sleep deprived UCLA students.

{:refdef: style="text-align: center;"}
![image](/assets/images/violations_per_hour.png){: .center-image }
{: refdef}

Street cleaning continues until 10 AM for Westwood streets. So why is
there no drop-in violations until 12ish? A second round of ticketing
starts up at 10 AM for parking over the time limit, which is 2 hours
every day (except Sunday) from 8 AM to 6 PM. After seeing every car at 8
AM, street patrols will come back around and mark up any car still left
on the street from that previous time. From 3-5 PM, the resulting spike
comes once again from another round of time limit violations.

Avoiding the Street Cleaning Ticket
-----------------------------------

Instead of idiling in your car from 8am to 11am once a week, wouldn't it be great if you
could move your car back early? Lets look at when every street cleaning ticket
was given, and determine when you do and don't have to move your car.




The first tickets given consistently make the 8AM mark,


The last tickets given are significantly different by street.







How much money does Los Angeles make from Westwood tickets?
--------------------------------------------------------

Ticket prices have continued to climb over the years. At present, five
of the six violations we have discussed cost over $58 per violation.
Given the already rising tuition, rent, and general fees associated with
being a UCLA student, getting an additional fee can put someone over the
financial edge.

{:refdef: style="text-align: center;"}
![image](/assets/images/costs.png){: .center-image }
{: refdef}

From 2015 to the end of 2018, *$3,702,125* in revenue has been made from
the Westwood area in tickets. This is a staggering amount of money to be taken
from the Westwood general area, largely due to the poor infrastructure
currently available for the growing UCLA community.

This isn't to say that parking fines are inherently evil. Ticketing serve a public
good, and is important for policing our neighborhood streets. But if your street has
already been cleaned, there is no point idling in your car waiting for 10 AM to
roll around. It only serves to add more traffic and pollution that can be fixed with
informed decision making. Hopefully, this information can help car owners in reducing
the chaos and problems associated with parking in the hills of Westwood.


Citations
---------

[Data](https://data.lacity.org/A-Well-Run-City/Parking-Citations/wjz9-h9np)

[Code](https://github.com/JamesWWilson/UCLA-Parking-Tickets-Analysis)

1 [Traffic Congestion in Los Angeles will get Worse](https://www.citywatchla.com/index.php/2016-01-01-13-17-00/los-angeles/17537-traffic-congestion-in-los-angeles-will-get-worse)

2 [Los Angeles's Open Data Initiative](https://data.lacity.org/)

3 [Mapping the Most Parking-Ticketed Blocks in All of Los Angeles](https://la.curbed.com/2014/12/30/10006936/mapping-the-most-parkingticketed-blocks-in-all-of-los-angeles#more)
