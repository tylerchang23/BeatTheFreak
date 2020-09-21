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

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/giannis_collage.jpg)

I think anyone that's watched Giannis play can confirm that his physique definitely gives him an advantage over other players. But how does he compare to other forwards in the league? 

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/pts_reb_scatter.png)

Here is a scatterplot of the top 20 scoring forwards in the league this season. Here we can see the clear gap between him and the best forwards in the NBA, including the likes of LeBron James (4x MVP, 3x NBA Champion, 16x All-Star) and Kawhi Leonard (reigning NBA Finals MVP, 2x NBA Champion, x6 All-Star). 

Another aspect we looked at was the rest of the Bucks roster. I think a lot of Giannis' success in the league can and should be acredited to his teammates. Although he doesn't have a Steph Curry in his back pocket, Giannis definitely has some three-point assasains that allow him to use his length and athleticism with ease down low. The league average three-point percentage sits at 33.8% this regular season. How does the rest of the Bucks starting lineup compare?

| Player       | 3-PT PCT|
| ------------- |:-------------:|
| Eric Bledsoe| 34.4% |
| Wesley Matthews| 36.4% |   
| Brook Lopez | 31.4% |
| Khris Middleton | 41.5% |

We can see that the Bucks starters are above average three point shooters with the exception of Brook Lopez (who is still an excellent shooter for a big man). This brings us to the dilemma that opponents constantly face when playing the Bucks. Do we beef up the defense on an animal in Giannis down low? Or should we take our chances in giving the rest of the Bucks a more open shot? Let's further visualize the Bucks using a kernel density plot that displays the frequency and location in which each player shoots. (Shoutout to [hkair](https://github.com/hkair/nba-shotcharts) for shot viz) 

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/heatmap_team.png)

Truthfully, there are countless reasons that contribute to Giannis' success, but these are the few we chose.


***What traits are prevalent in teams that have proven to be successful against the Bucks?***

This regular season (including Bubble play) the Bucks lost 17 games, in which Giannis was in 12 of them. Of these 12 games, we looked at the 10 unique teams that faced the Bucks and looked for differences in team statistics between these "winners" and the other "losing" teams in the league. In particular, we ran several t-tests on various team statistics between the winners and losers.

Of the team statistics tested on, there appears to be significant differences in **FGM,FG_PCT, FG3M, FG3A, DREB, REB, FTA, PTS**. To further investigate this result, we created several scatterplots of these statistics to look for any obvious clustering.

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/pts_fgm_scatter.png)

This scatterplot shows a clear clustering in winning teams with regards to scoring. I initially expected there to be an outlier in at least one of the games that Giannis lost in due to the dynamic nature of basketball/sports. However, it looks like in order to be successful against the Bucks you need quite a lot of fire power offensively. 

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/reb_scatter.png)

Another intersting clustering we found was in regards to rebounding. Here we can see another clustering in rebounding with the winners. This makes a lot of sense especially when facing the 7 foot giant in Giannis. 

***What tendencies does Giannis have when shooting?***

I think it's clear that Giannis is a scoring machine. But are there any noticeable differences in his percision based on *where* he shoots?

To first investigate this, we look at how Giannis' shooting changes as he gets farther from the basket.

| Location| % of Total Shots| % Made | % Miss |
| ------------- |-------------| --- | --- |
| Down Low| 66.9% | 66.4% | 33.6% |
| Mid-Range| 9.4% | 38.8% | 61.2% | 
| Three| 23.7% | 30.4% | 69.6% |

![alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/downlow_shotchart.png)

[alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/midrange_shotchart.png)

[alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/three_shotchart.png)

There are a few observations we can see from this. **First, we can see that Giannis' accuracy obviously gets worse the farther away he is from the basket.** This is most likely due to him not beign able to use his athleticism as much from distance.

Interestingly, **Giannis takes more threes than mid-range jumpers, even though he has a greater shooting percentage from mid-range**. From a coaching perspective (and possibly his perspective), if Giannis is taking a shot within the arc, that means he's attempting a basket worth two points. That being said, it makes more sense for Giannis to take a shot closer to the basket with a higher percentage since the point value would be the same (since he would be scoring more points in expectation).

When we took a look at Giannis' jump shots from mid-range and beyond, we can see **he took twice the amount of shots from the left side than the right side**. Not only does he *attempt* more jump shots from the left side, **he also becomes less accurate when he shoots on the right when compared to the left**. This possibly could be due to him being right-handed and being less comfortable driving from the left side. 

Can we see any of these tendencies in the games he lost? 

[alt text](https://github.com/tylerchang23/BeatTheFreak/blob/master/images/opponents_shotchart.png)

We also found that **in the 9 of the 12 losses that Giannis played in, he attempted more three's than he does on average (per game). Of those threes, the vast majority were taken from the left**.

***Multiple Linear Regression***

With much of the focus on this project on Giannis, I thought it would be useful to create a model that can predict how many points he will score in a given game. In particular we used a multiple linear regression model using: **FTA, OREB, AST, STL, BLK, PF, shot attempts (by region), number of threes made by teammates, opponent defensive rating, etc..**. For more details on multiple linear regression see this [link!](http://mezeylab.cb.bscb.cornell.edu/labmembers/documents/supplement%205%20-%20multiple%20regression.pdf)

After checking the assumptions for the model, we obtained an **R-squared of 0.279**, which isn't too great. I suspect the main issue comes from the data used in the model.Firstly, I think the features being fed to the model weren't able to capture our goal. Each of the stats being used were on a per game basis. Although we were indeed trying to predict how many points Giannis would score in a given game, I think it would be much better if we used play-by-play stats. Since the points Giannis scores in a given game is just the aggregate of the number of points he scores in each play, it would be much more useful to know his environment in a given play. Who was guarding him? How far was his defender when he took the shot? What was the play type (ISO, pick-and-roll, fastbreak, etc.)? With this type of information, I think we could have been able to produce significantly better results. Unfortunately, the NBA does not release this kind of "play-by-play" data, so predicting his buckets might have to be put on hold for a little while.
