---
title: "The Seven Pillars of Statistical Wisdom *Visualized*"
date: '2021-03-20'
layout: post
summary: Using the Palmer's Penguins Dataset, I visualize the "7 Pillars of Statistics" with worked out examples to bolster my own and other's understanding of the foundation of the field. 
categories: Book Review
---

*A visual book review of Stephen M. Stigler's The Seven Pillars of Statistical Wisdom*

After our UCLA commencement ceremony, the Statistics program gave each graduate a copy of Stephen M. Stigler's *The Seven Pillars of Statistical Wisdom* as a sort of yearbook to sign amongst classmates and cement our capstone as undergraduates. Almost two years later, and I  finally got around to reading the book! Reviewing the so called "pillars of statistics" has grown my appreciation of its simple description of the functionality and durability of the field of Statisitcs (which is still in it's infancy relative to most sciences). The one shortfall of the book, in my opinion, is a lack of visualizations to convey each of the 7 pillars that define the field. So in reviewing and summarizing the book, let's try to visualize each concept with one of my new favorite datasets: the Palmer's Penguin dataset [1][2]. The Penguins dataset contains data for 344 penguins, which were collected and made available by Dr. Kristen Gorman and the Palmer Station located at the Palmer Archipelago in Antarctica.

<div style="text-align: center"><img src="/assets/penguin_images/lter_penguins.png"
height="90%" width="90%" /></div>
[3]

### Aggregation

The first pillar described by Stigler is Aggregation, or the general summary of information by *throwing information away*! "What do you mean throw away information, shouldn't it all be relevant?" Well, there are many cases when changing the way we interpret information can be useful. For instance, generating the _average value_ of a numeric field can quickly illuminate the reality of that field in relation to other fields. But to generate an average, an individual has to throw away granular information for the summary. While this may seem commonplace and intuitive in today's information age, this wasn't always the case. The use of an average wasn't mainstream until the 1800s, when it became a popular measurement in the earth and planetary sciences. Since then, statistical summaries that eliminate granularity for summarization have grown. A useful visuzaltion for determining such summary statistics is the BOXPLOT.

<div style="text-align: center"><img src="/assets/penguin_images/aggregation_combo.png"
height="90%" width="90%" /></div>

Boxplots allow statisticians to 'boil down' the data into a clean illustration of averages, medians, quartiles, and ranges of the underlying data. This can be useful for quick comparisons between cuts of the data, outlier diagnostics, and easier communication of the data at hand.  Instead of saying "Penguins in our sample are recorded as having bill lengths of 181 mm, 186 mm , 195 mm, 207 mm..." you can say "Penguins in our sample are recorded as having an *average* bill length of roughly 201 mm." This is a simple and immensly powerful tool for communicating relevant information. 

### Information
    
Speaking of information, how do we, as Stigler puts it, "measure the value and aquisition of information"? How do we determine when we have enough data, and that the data we have can accurately measure the goal of the investigation in question? This has been a challenge for reseachers for a long time, dating back to when the Bank of England had to determine the accuracy of the weight and density of gold coins. At that point in time, the bank would sample coins to determine if the whole was accurate, to varying degrees of accuracy[4]. Since that point in time, statisticians have refined their methodology of sample review to develop the now famous Central Limit Theorem. The Central Limit Theorem, or CTL for short, states that as the size of the sample increases, the distribution of the mean across multiple samples will approximate a Gaussian (aka "normal") distribution. Just what does this mean? 

When performing a study, multiple observations are drawn from the sample population. Additional independent observations are collected repeatedly that represent a sample of observations. When we generate an average from this sample, it will be an *estimate* of the average for the general population from which those samples were drawn. However, this estimated average will contain some *error*. What the CTL allows for is for researchers to draw multiple *other* samples and calculate their means, and which together those means will form a normal distribution (around the average).

CTL is impressive, as it will occur no matter the shape of the population distribution from which we are drawing samples. It demonstrates that the distribution of errors from estimating the population mean fit a distribution that the field of statistics knows a lot about.

This estimate of the Gaussian distribution will be more accurate as the size of the samples drawn from the population is increased. This means that if we use our knowledge of the Gaussian distribution in general to start making inferences about the means of samples drawn from a population, that these inferences will become more useful as we increase our sample size.

So where do we see the central limit theorem, or rather, the normal distribution it is built off of, appear in real research? Let's assume we are curious to know the average body mass of penguins in our study, regardless of species. We have the luxury of having a large sample size which pinpoint an average body mass of roughly 4,200 grams. 

<div style="text-align: center"><img src="/assets/penguin_images/information_1.png"
height="90%" width="90%" /></div>

But let's assume we *didn't* have our data, and that the 344 penguins in our study represent all the penguins available in the population. Now imagine that 100 different research teams had, independetly, gone down to Antartica and gathered data for 30 penguins each from our population, and then calculated an average body mass for their group of penguins. If we were to take each of those average values and combine them, they would *still* accurate produce the average body mass of 4,200 grams, as seen in the randomly sampled version of this concept below. 

<div style="text-align: center"><img src="/assets/penguin_images/information_2.png"
height="90%" width="90%" /></div>

The point is best driven home if we were to repeat this experiment not 100 times, but *10,000* times. The larger the number of repeated samples, the closer we get to not only a normal distribution, but a normal distribution centered on the population's average value. 

<div style="text-align: center"><img src="/assets/penguin_images/information_3.png"
height="90%" width="90%" /></div>

### Likelihood

"A measurement with no context is just a number" Stigler writes to start out his chapter on Likelihood. Probability distributions are one of many ways to provide such context.  Probability distributions are used to summarize the probabilities of possible values of a random variable, as well as to calculate the confidence intervals for parameters involved in hypothesis testing. Bayesian statisticians use probability distributions in their defining of their prior and posterior distributions for hypothesis testing. Two common way of approaching probabilty distributions include probability density functions (PDF) and cummulative distribution functions (CDF), which we will see shortly. 

In the real world, the shape of a histogram of most random samples will match a well-known probability distribution. Common distributions are common because they occur again and again in different and sometimes unexpected domains. Determining the type of distribution is useful when you need to know which outcomes are most likely, the spread of potential values, and the likelihood of different results. 

In our case, the Penguin reaserch team that produced our data collected "Delta13C and Delta15N SI signatures of blood tissue, obtained during egg laying". The Delta 15 N values from the blood samples were helpful in testing the amount of Nitrogen in the biome, which can aid in indicating the foraging/ dieting behaviors and niches that male and female penguins might occupy. 

Let's pretend a researcher comes across a Delta 15 N value of 9 (). What is the probability of finding a value greater than 9 () in our population? Rather, can we determine how rare of a chance this value occurs in our data? 

First, we need to fit a distribution to our data. We can visualize our data as a histogram, and try to visualize which distributions fit best to our data. Our data appears to ...

* distribution of 15 N values 

Next, we can use the *fitditr* package in R to test multiple probability distributions against our data . The package let's us first review potential fits based on common models, then we can fit a few of these models ourselves and review their criteria / diagnostic plots. 

* QQ plot for best fits 
    -- how to interpret QQ / AIC 


Reviewing a variey of models, we find that a Generalized Gamma (GenGamma) distribution fits our data best. 
The Generalized Gamma Distribution adds a scale parameter in the ... 

Using this best fit probability distribution, we can now utlize its underlying ___ to answer our question. Using a simple r commad ( ), we find that there is a ____ chance of a __ value of less than 9. We can visualize this concept with the use of the Cummulative Distribution Function ... 

* CDF of values 



### Intercomparison
Statisitcans are often tasked with determining the differences between specified populations. A powerful application of this differentiaion is the concept that it can be done *internally*, or rather, without the reference of exterior criteria. The idea first become prominent with Francis Galton's famous essay "Statistics by Intercomparison"...   
    
William Gosset introduced the idea when employed as a Chemist for the Guiness Company [5] and found practical appliations for statistics in the brewing process. "The Probable Error of a Mean" in 1908 under the "Student" pseudonym, where "Student's T-Test" now gets its name [6].

    This concept expanded upon by fisher

    Allowed for the comparison of sample means with mathematical assumptions based on normality of sample sizes. 

    Create the ttest table we know today 

*of standard deviations a parameter is away from a constant 

** show case formula ** 


* visual of female vs male bill lengths 


* TTest results 



### Regression
    
    Prediction is the main component of modern day data science practices, where intricate machine learning models are used to attempt to classify and evaluate future inferences based on prior data. The concept of building a model that allows us to compare predicted results to the expected results was originally formed by ___ Galton in 1885, where he first defined the term "regression". In his analysis of children and parent height data, Galton introduced the concept of individual data points 'regressing to the average', exemplified where parents of above average height tended to produce shorter children, and parents of belo average height tend to produce taller children. Predicitive models, ranging in complextion from simple linear regression to (Support Vector Machines? Neural Networks?), allow us to utilize the concept that <groups within data tend to produce variation of varying definitions that >
    
    For the purpose of illustration, we can take a stab at replicating one of the models performed by the Penguins research team. One of the main goals of their team's research was evaluating a penguin's sex based on it's physical characteristics. This sort of research question is a great case example for a logistic regression model, which allows us (and the research team) to determine and evaluate a binary classification of the data, in this case Male (1) vs Female (0). In the study notes, penguins are controlled by species, and then a mix of numerical variables such as [] and [] are used. Reivewing the researchers notes, we can create a simplifid version of the Chinstrap penguin model, and try to predict sex based on just their flipper length.

    Using R, we can illustrate 

* Plot for logistic regression of Gender ~ Bill Length for chinstrap penguins 

##### report R2 value 

A reminder that *correlation is not causation*. For instance, being born with an abnomally large bill doesn't imply that a penguin will be male. Rather, males *on average* have larger bills, and we can use that metric to explain the difference in the groups. 



### Design
    Randomization 
    Florence Nightengale 
    How does one design a study to control for randomization / error / sample sizes. 

    

    The Penguin research team took design qualities into practice when they produced the underlying data for the study they performed. 

    Collected data from three different islands 
    OF population, randomly sampled populations 

    Considered the power of the sample 










### Residual 
    Difference between predicted and actual results in overall model. Regression to the mean. Evaluation of success of model.

    Going back to our previous logistic regression, let's 'diagnose' the issues the plot may have. Residuals are a way of comparing our model's predicted training data results to it's raw testing data, and seeing how well our model performs in the real world 



    OR Linear Regression based on DELTA15N 
    ? log vs normal scale for residuals





### Conclusion 

Statistics is a field of varying methodolgies and techinques that attempt to give us a better understanding of our world through the data we collect and analyze. The seven pillars that form it's foundaton provide us with a concrete understanding of how to 















Footnotes
[1] Cite penguins data https://github.com/allisonhorst/palmerpenguins
[2] Common replacement for IRIS data - which has recently been 'canceled' by many statisticians due to recent growth in knowledge that is create ___ (fisher?) had policial views that do not sit well with our current generation (i.e. )
[3] Photo citation. 
[4] Trial of Pyx 
[5] Yum beer stats 
[6] Guniess policy against publicaiton of work under its name. 
 


https://cran.r-project.org/web/packages/fitdistrplus/vignettes/paper2JSS.pdf
https://en.wikipedia.org/wiki/Generalized_gamma_distribution


CTL 
https://machinelearningmastery.com/a-gentle-introduction-to-the-central-limit-theorem-for-machine-learning/
https://en.wikipedia.org/wiki/Central_limit_theorem  <- SEE PLOT 
https://sphweb.bumc.bu.edu/otlt/mph-modules/bs/bs704_probability/BS704_Probability12.html

