---
title: "Jeopardy Contestants Case Study [Part 2]"
date: '2020-04-19'
layout: post
summary: Who makes it onto Jeopardy, and just how interesting are they?
categories: Workshop Python Jeopardy
---

*This is a three part workshop for DataFest 2020 competitors on
how to organize a basic data analytics project with Python.*

In Part 1 of this workshop series, Python's BeautifulSoup and Tweepy libraries were utilized to collect data online for the analysis of Jeopardy contestant profiles. 

Now that we have a complete dataset of contestants and their associated details, we can start our investigation! 

### Part 2: Contestant Analytics and Predicting Winnings

#### Demographics & Characteristics 

Let's start with a general evaluation of the demographic data provided. 

Contestants for Jeopardy are selected by taking an online quiz and meeting a certain evaluation criteria. Contestants are eligible to come from the United States or Canada, and are often widely dispersed across the countries.

<div style="text-align: center"><img src="/assets/jeopardy_images/contestant_count.png"
height="90%" width="90%" /></div>

Contestants hometown state locations tend to correlate with population demographics, with many indiviudals coming from California (382), New York (316), and Illinois (217). 

51% of contestants are unique to their hometown, demostrating that individuals are not just selected from the large cities that can seem to dominate the selection process. 

#### Occupations 

A wide range of occupations are represented by candidates. Within our range of contestants, there are approximately 1,317 distinct careers held by individual contestants. 

Doing the grunt work, I went ahead and grouped each of these occupations into a 'job category'. For instance, a '10th grade english teacher' and 'violin teacher' are labeled as just 'teacher', and occupations such as 'public health doctor' and 'emergency physician' are grouped as simply 'physician'. Doing so presents us with a count of 33 distinct occupation categories.

So which career paths seem to appear more on Jeopardy? 

<table>
<thead>
<tr class="header">
<th>Job Category[3]</th>
<th>Number of Contestants</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Unemployed</td>
<td>169</td>
</tr>
<tr class="even">
<td>Teacher</td>
<td>180</td>
</tr>
<tr class="odd">
<td>Student</td>
<td>145</td>
</tr>
<tr class="even">
<td>Manager</td>
<td>138</td>
</tr>
<tr class="odd">
<td>Lawyer</td>
<td>135</td>
</tr>
<tr class="even">
<td>Writer / Author</td>
<td>133</td>
</tr>
<tr class="odd">
<td>Graduate Student</td>
<td>98</td>
</tr>
<tr class="even">
<td>Artist / Designer</td>
<td>62</td>
</tr>
<tr class="odd">
<td>...</td>
<td>...</td>
</tr>
</tbody>
</table>

We see that the most common jobs tend to follow three themes: free time, tournment categories, and writing/reading heavy roles. Individuals who are unemployed likely have free time on their hands to study miscellaneous topics and build up their trivia skills, where as those with full time jobs may not. Jeopardy's most common tournments consist of 'Teen', 'College' and 'Teachers' categories that fuel the high number of these roles we see in the data. What is of interest is those job categories outside of the standard tournaments, where we still often see those pursuing reading/ research heavy roles (Lawyers/ Graduate Students) and those with creative work that might often lead to exposure of different fields of work (Writers/ Artists). 
Given this, let's also review the least common job categories: 

<table>
<thead>
<tr class="header">
<th>Job Category</th>
<th>Number of Contestants</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td>...</td>
<td>...</td>
</tr>
<tr class="odd">
<td>Salesperson</td>
<td>18</td>
</tr>
<tr class="even">
<td>Coordinator</td>
<td>17</td>
</tr>
<tr class="odd">
<td>Musician</td>
<td>17</td>
</tr>
<tr class="even">
<td>Military / Clergy</td>
<td>16</td>
</tr>
<tr class="odd">
<td>Laborer</td>
<td>13</td>
</tr>
<tr class="even">
<td> Marketing </td>
<td> 11 </td>
</tr>
</tbody>
</table>

Nothing too special about these job categories from first glance. 'Musician' seems somewhat suprising given the number of music related subject matter seen in Jeopardy questions. Of significant note is the general lack of jobs that tend to involve physical labor requirements (Military/ Laborer). Jeopardy has always tended to be the most pronounced "white collar" focused game show, and the data seems to support that. 

But of a given job category, which tends to produce more *winners*?  

** review winners proportion of each category 






#### Winnings & Winners

Contestants typically play an average of 1.6 games. Roughly 72% of all conetestants will only ever play a single game, with 98% of contestants playing 5 games or less. Any player who gets above this 5 game threshold is considered to be a bit of an outlier, having carved out a significant amount of cash winnings for oneself.

The median end score needed to win and move on in any given game of a Jeopardy tournament is $18,800. To come in second place still requires that you win an average hefty sum of $10,399. 

Due to these statisitcs, it is typical that a strong player with a solid strategy and wit can keep dominating the board and win multiple games in a row. For example Julia Collins won 20 consecutive victories between April 21 and May 30 of 2014. 

While reviewing winners, its worth evaluting the proportion of winners produced from each state. Thinking back to the original number of contestants per state, we can take the proportion of winners out of the overall count of contestants from their home state to produce the following distribution: 

<div style="text-align: center"><img src="/assets/jeopardy_images/winner_ratio_map.png"
height="90%" width="90%" /></div>

blah blah blah 




#### Putting it all together: can we make a winner?   

But is it possible to *predict* who will win based on just the contestant data available?  This is a challenging quesiton the requires defining. Are we prediciting if a candidate will win, or simply the total amount of winnings they earn before being set into their final rank[2]?

For the purpose of the data available, we will address the former question. We can create a unique database of contestants and a flag on if they have won *at least once*. This helps address outliers like the infamous James H ___ who has played in 30+ games. 




-- Logistic Regression 



blah blah 

62% accuracy wow that's good right ? WRONG 

the model defaulted, as is an known problem , to everyone being labeled as a non-winner. Due to the the cut of the data wit there being X winners / total (aka %), inverses.

So what does this mean? If anything 

https://towardsdatascience.com/my-absolute-go-to-for-sentiment-analysis-textblob-3ac3a11d524

-- Final thoughts



Sometimes models *don't work*! That's just life! Wether its a lack of detailed data, 




##### Footnotes

[1] When calculating total scores, we are calculating the gross final scores that players earned in their game play. However, the majority of contestants will not see these totals in their winnings, as most tournaments settle to give second place $2,000 and third place $1,000, regardless of what they earned in game. 

[2] In Jeopardy, only first place takes home their overall winnings. Second place receives $2,000 and Third place receives $1,000. 

[3] Individuals listed as "retired", "originally", or by a unique 'age' are listed as "unemployed". 




