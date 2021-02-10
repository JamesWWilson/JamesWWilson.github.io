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

### Part 2: Contestant Analytics and Predicting Winners

#### Demographics & Characteristics 

Let's start with a general evaluation of the demographic data provided. 

Contestants for Jeopardy are selected by taking an online quiz and meeting a certain evaluation criteria. Contestants are eligible to come from the United States or Canada, and are often widely dispersed across the countries.

<div style="text-align: center"><img src="/assets/jeopardy_images/contestant_count.png"
height="90%" width="90%" /></div>

Contestants hometown state locations tend to correlate with population demographics, with many indiviudals coming from California (268), New York (200), and Illinois (125). 

71% of contestants are unique to their hometown, demostrating that individuals are not just selected from the large cities that can seem to dominate the selection process. 

#### Occupations 

A wide range of occupations are represented in our sample of Jeopardy contestants. Within our range of contestants, there are approximately 1,317 distinct careers held by individual contestants. 

Doing the grunt work, I went ahead and grouped each of these occupations into a 'job category'. For instance, a '10th grade english teacher' and 'violin teacher' are categorized as just 'teacher', and occupations such as 'public health doctor' and 'emergency physician' are grouped as simply 'physician'. Doing so presents us with a count of 33 distinct job categories.

So which career paths appear more often on Jeopardy? 

<table>
<thead>
<tr class="header">
<th>Job Category[3]</th>
<th>Number of Contestants</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align:center">Unemployed</td>
<td style="text-align:center">169</td>
</tr>
<tr class="even">
<td style="text-align:center">Teacher</td>
<td style="text-align:center">180</td>
</tr>
<tr class="odd">
<td style="text-align:center">Student</td>
<td style="text-align:center">145</td>
</tr>
<tr class="even">
<td style="text-align:center">Manager</td>
<td style="text-align:center">138</td>
</tr>
<tr class="odd">
<td style="text-align:center">Lawyer</td>
<td style="text-align:center">135</td>
</tr>
<tr class="even">
<td style="text-align:center">Writer / Author</td>
<td style="text-align:center">133</td>
</tr>
<tr class="odd">
<td style="text-align:center">Graduate Student</td>
<td style="text-align:center">98</td>
</tr>
<tr class="even">
<td style="text-align:center">Artist / Designer</td>
<td style="text-align:center">62</td>
</tr>
<tr class="odd">
<td style="text-align:center">...</td>
<td style="text-align:center">...</td>
</tr>
</tbody>
</table>


We see that the most common jobs tend to follow three themes: free time, tournment categories, and writing/reading heavy roles. Individuals who are unemployed likely have free time on their hands to study miscellaneous topics and build up their trivia skills, where as those with full time jobs may not have such a luxury. Jeopardy's most common tournaments consist of 'Teen', 'College' and 'Teacher' categories that fuel the high number of these roles we see in the data. What is of interest is those job categories outside of the standard tournaments, where we  often see those with reading/ research heavy roles (Lawyers/ Graduate Students) and those with creative work that may lead to a wide range of educational and different fields of work (Writers/ Artists). 

We can also review the least common job categories: 

<table>
<thead>
<tr class="header">
<th>Job Category</th>
<th>Number of Contestants</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td style="text-align:center">...</td>
<td style="text-align:center">...</td>
</tr>
<tr class="odd">
<td style="text-align:center">Salesperson</td>
<td style="text-align:center">18</td>
</tr>
<tr class="even">
<td style="text-align:center">Coordinator</td>
<td style="text-align:center">17</td>
</tr>
<tr class="odd">
<td style="text-align:center">Musician</td>
<td style="text-align:center">17</td>
</tr>
<tr class="even">
<td style="text-align:center">Military / Clergy</td>
<td style="text-align:center">16</td>
</tr>
<tr class="odd">
<td style="text-align:center">Laborer</td>
<td style="text-align:center">13</td>
</tr>
<tr class="even">
<td style="text-align:center"> Marketing </td>
<td style="text-align:center"> 11 </td>
</tr>
</tbody>
</table>

From first glance, nothing seems too special about these job categories. 'Musician' seems somewhat suprising given the number of music related subject matter seen in Jeopardy questions. Of significant note is the general lack of jobs that tend to involve physical labor requirements (Military/ Laborer). Jeopardy has always tended to be one of the most pronounced "white collar" focused game shows on television, and the data seems to support that argument. 

So of a given job category, which tends to produce the most *winners*? [4]

<div style="text-align: center"><img src="/assets/jeopardy_images/winner_ratio_map.png"
height="90%" width="90%" /></div>

Several of our underrepresented job categories seem to feature a higher than average proportion of winners! 







#### Gender & Personal Anecdotes 











#### Winnings & Winners

Contestants typically play an average of 1.6 games. Roughly 72% of all conetestants will only ever play a single game, with 98% of contestants playing 5 games or less. Any player who gets above this 5 game threshold is considered to be a bit of an outlier, having carved out a significant amount of cash winnings for oneself.

The median end score needed to win and move on in any given game of a Jeopardy tournament is $18,800. To come in second place still requires that you win a hefty average sum of $10,399. 

Due to these statisitcs, it is typically seen that a strong player with a solid strategy and wit can keep dominating the board and win multiple games in a row. For example Julia Collins won 20 consecutive victories between April 21 and May 30 of 2014. 

While reviewing winners, it's worth evaluting the proportion of winners produced from each state. Thinking back to the original number of contestants per state, we can take the proportion of winners out of the overall count of contestants from their home state to produce the following heatmap: 

<div style="text-align: center"><img src="/assets/jeopardy_images/winner_ratio_map.png"
height="90%" width="90%" /></div>

Unsurprisingly, states with few overall contestants tend to have a higher proportion of winners from their home state, such as Arkansas and Deleware. The South in general seems to produce a high number of winners proportionally, where as states such as California and New York get washed out in this ranking. 


#### Putting it all together: can you *make* a winner?   

But is it possible to *predict* who will win based on just a contestant's demographic data (e.g. hometown, gender, job category, and personal anecode)?  This is a challenging quesiton that requires defining. Are we prediciting if a candidate will win, or prediciting their total amount of winnings they earn before being set into their final rank[2]?

For the purpose of the data available, we will address the former question. We can create a unique database of contestants and a flag on if they have won *at least one* game of Jeopardy. This helps address outliers like the infamous James Holzhauer who has played in 30+ games, and boil him down to a single snapshot. 


Evaluating this criteria in the form of a logistic regression model, we find next to no correlation between the variables (R-Squared 0.05). In fact, when attempting to predict results with several different models, we find next to everyone in the test dataset being labeled as a non-winner! (Which produces close to 68 % accuracy, a misleading statistic.)

#### Final thoughts

So what does this mean? Has all this work been for nothing? Quite the contrary. Sometimes models *aren't accurate*! That's just life! Wether its a lack of detailed data, or a challenging problem to solve, sometimes we aren't able to find any interesting results. 

Or are we? Instead, I would argue our investigation has shown that *anyone* can make it onto Jeopardy and be a successful contestant. Regardless of your hometown, job, gender, or your funny quip during the show, what really likely matters is the strategy and effort contestants take to study and prepare for these challenges. As in the famous words of my favorite disney movie " Anyone can cook" translate to "Anyone can win Jeopardy!". 




##### Footnotes

[1] When calculating total scores, we are calculating the gross final scores that players earned in their game play. However, the majority of contestants will not see these totals in their winnings, as most tournaments settle to give second place $2,000 and third place $1,000, regardless of what they earned in game. 

[2] In Jeopardy, only first place takes home their overall winnings. Second place receives $2,000 and Third place receives $1,000. 

[3] Individuals listed as "retired", "originally", or by a unique 'age' are listed as "unemployed". 

[4] For the purposes of the winner table I removed "Student" / "Teacher" / "unemployed" given that these individuals have their own tournaments. Those indicated as "Professor" are NOT featured in Teacher's tournaments and therefore do not need to be excluded. 


