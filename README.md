# BeatTheFreak

## Introduction

As the NBA regular season comes to a close, fans across the globe wait eagerly for some exciting playoff action (shoutout Dame Dolla). Coming off an insane MVP season last year, Giannis Antetokounpo and the Milwaukee Bucks yet again sit at the top of the Eastern Conference. With Giannis in the running for another MVP title, it's no secret that they will be a force to be reckoned with in the post-season. Before the sudden shutdown, the Bucks had a whopping 53-12 record, in which Giannis only played in 9 of those losses.

It's obvious that Giannis is one of the most important factors to the Bucks' success, so what can you do to stop him? This project will focus on finding the strengths/weaknesses of the Bucks/Giannis, and what strategies could potentially be used to stop them.

## Goals

There are a few different questions I want to answer in this analysis:

* **What makes Giannis good?**

* **What traits are prevalent in teams that have proven to be successful against the Bucks?**

* **What tendencies does Giannis have when shooting?**

* **Is there a model that can predict how many points Giannis will score in a given game?**

## Tools (Python)

* **Data Collection:** *nba_api, Pandas*

* **Data Visualization:** *matplotlib*

* **Machine Learning:** *sklearn, statsmodels*

## Results

***What makes Giannis so good?***

To simply answer this question, we first looked at Giannis as an individual player. Giannis, a near 7 footer, uses his massive size to dominate the paint at the forward position. Not only does he possess the height, but he has also acquired more and more muscle year by year. 

-insert collage here -

I think anyone that's watched Giannis play can confirm that his physique definitely gives him an advantage over other players. But how does he compare to other forwards in the league? 

-insert pts vs. total rebounds scatterplot here- 

Here is a scatterplot of the top 20 scoring forwards in the league this season. Here we can see the clear gap between him and the best forwards in the NBA, including the likes of LeBron James (4x MVP, 3x NBA Champion, 16x All-Star) and Kawhi Leonard (reigning NBA Finals MVP, 2x NBA Champion, x6 All-Star). 

Another aspect we looked at was the rest of the Bucks roster. I think a lot of Giannis' success in the league can and should be acredited to his teammates. Although he doesn't have a Steph Curry in his back pocket, Giannis definitely has some three-point assasains that allow him to use his length and athleticism with ease down low. The league average three-point percentage sits at 33.8% this regular season. How does the rest of the Bucks starting lineup compare?

| Player       | 3-PT PCT|
| ------------- |:-------------:|
| Eric Bledsoe| 34.4% |
| Wesley Matthews| 36.4% |   
| Brook Lopez | 31.4% |
| Khris Middleton | 41.5% |

We can see that the Bucks starters are above average three point shooters with the exception of Brook Lopez (who is still an excellent shooter for a big man). This brings us to the dilemma that opponents constantly face when playing the Bucks. Do we beef up the defense on an animal in Giannis down low? Or should we take our chances in giving the rest of the Bucks a more open shot? Let's further visualize the Bucks using a kernel density plot that displays the frequency and location in which each player shoots.

-insert kernel density plot 1-

-insert kernet density plot 2-

Truthfully, there are countless reasons that contribute to Giannis' success, but these are the few we chose.


***What traits are prevalent in teams that have proven to be successful against the Bucks?***

This regular season (including Bubble play) the Bucks lost 17 games, in which Giannis was in 12 of them. Of these 12 games, we looked at the 10 unique teams that faced the Bucks and looked for differences in team statistics between these "winners" and the other "losing" teams in the league. In particular, we ran several t-tests on various team statistics between the winners and losers.

Of the team statistics tested on, there appears to be significant differences in **FGM,FG_PCT, FG3M, FG3A, DREB, REB, FTA, PTS**. To further investigate this result, we created several scatterplots of these statistics to look for any obvious clustering.

-insert PTS vs FGM scatterplot-

This scatterplot shows a clear clustering in winning teams with regards to scoring. I initially expected there to be an outlier in at least one of the games that Giannis lost in due to the dynamic nature of basketball/sports. However, it looks like in order to be successful against the Bucks you need quite a lot of fire power offensively. 

-insert reb scatterplot-

Another intersting clustering we found was in regards to rebounding. Here we can see another clustering in rebounding with the winners. This makes a lot of sense especially when facing the 7 foot giant in Giannis. 

***What tendencies does Giannis have when shooting?***

I think it's clear that Giannis is a scoring machine. But are there any noticeable differences in his percision based on *where* he shoots?

To investigate this, we look at how Giannis' shooting changes as he gets farther from the basket.


| Location| % of Total Shots| % Made | % Miss |

| ------------- |------------| |:-------------| |:-------------:| 

| Down Low| 66.9% | 66.4% | 33.6% |

