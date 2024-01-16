---
layout: post
title: Descriptive Statistics
subtitle: Comparing Lebron James and Michael Jordan
tags: [lab]
comments: true
---

## What datasets I used:
For this lab I used Basketball Reference to access Michael Jordan's and Lebron James' career statistics. 
[This is a link to Michael Jordan's stats](https://www.basketball-reference.com/players/j/jordami01.html#per_game), and [this is a link to Lebron James'](https://www.basketball-reference.com/players/j/jamesle01.html#per_game)

## Why those datasets:
{: .box-warning}I chose not to use advanced stats as many of them are really incomparable as the two players played in very different eras, and had very different roles on their team. As well as the fact that many advanced stats use speculation with no gurantee. 


Basketball Reference had alot of statistics on both players but the majority of the data is mostly irrelevant, and not talked about when typically comparing the players. So for my study I only choose: points, assists, offensive rebounds, field goal percent, defensive rebounds, steals, and blocks. I selected these as it was most representative of the two players defnsive and offensive capabilities. I found it necessary to seperate offensive rebounds and defensive rebounds to the more used stat of rebounding, but getting and offensive rebound and defensive rebound are two completely different skillsets making it important to differentiate. 

From these datasets I hope to be able to ascertain which player is more consistent in every category, as well as who had the higher peak. 

## Analyzing the datasets:
For every category I found that a boxplot was the best way to represent the two's careers in the categories. 

**Points**

![ptscomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/ptscomp.png){:height="400px" width="500px"}

The data shows that throughout the two's careers Michael Jordan averaged a signficantly higher points per game. But what is not shown in the graph is that at the end of his career when he was on the wizards he had a steep fall off, while LeBron throughout his entire career has only increased since his rookie season with little sign of slowing down despite entering year 21. 

**Assists**

![astcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/astcomp.png){:height="400px" width="500px"}

The data shows that LeBron has averaged a much higher assist per game. This is the first example of a statistic not telling the full story as it was simply never Jordan's role on any team to be the team's primary passer as he was literally a scorer. As well as the fact that despite LeBron being larger he has had years where he plays the point guard, where assists would become a much larger focus than it normally would than if he was playing his normal small forward position.

**Field Goal Percent**

![fgpcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/fgpcomp.png){:height="400px" width="500px"}

Field goal percent shows us how a effecient a certain player is, meaning if I gave LeBron the ball 100 times his median shows us that he would score 51% of the time. While there are advanced stats that can show us what the point attempted and whether it is considered a "good shot" or not but it's not necesarily relevant. For our purposes we can see that except for a signficant outlier the majority of the time Lebron has a much higher efficiency than Jordan does. 

**Offensive Rebounds**

![orbcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/orbcomp.png){:height="400px" width="500px"}

Offensive rebounds are a really key hustle stat, as in most circumstances obtaining one would mean you had to outhustle the defender and outstrength the box out. This is a really interesting stat because LeBron despite being three inches taller and currently 50 pounds heavier than Jordan was, Jordan was consistently getting more offensive rebounds. It's impossible to say why Jordan has more than LeBron as you cannot measure how badly a player wants to get a rebound, but it can be speculated that because Jordan was in a more physical era he was okay with getting hit and fighting more than LeBron is. 

**Defensive Rebounds**

![drbcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/drbcomp.png){:height="400px" width="500px"}

Defensive rebounds are not seen as much as a hustle stat but are still useful to look at nonetheless. Your role on the team plays a big part in how many defensive rebounds one can get, as smaller players are not normally under the basket when the ball falls. LeBron is almost always one of the largest players on the court so it has become almost an expectation for him to box out other centers and forwards. LeBron by far grabs more defensive rebounds than Jordan did.

**Steals**

![stlcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/stlcomp.png){:height="400px" width="500px"}

The data shows that Jordan is a much more consistent stealer than LeBron ever has been, but it is a difficult measure. In the modern era the level of dribbling has increased exponentially, and while it is a debate whether or not the dribbles are necessary the increase in skill is apparent. Stealing is also kind of a role based statistic, as it is significantly harder to steal the ball when someone is backing you down then dribbling face to face, but due to LeBron's fluctuation in position it becomes harder to measure whether or not it's an excuse. 

**Blocks**

![blkcomp](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/blkcomp.png){:height="400px" width="500px"}

It's almost an expectation that the taller you are the more blocks you will amass, as the taller you get the longer your wingspan gets and small guards get relatively smaller. What's interesting is that Jordan is a much more consistent blocker than Lebron is throughout his career. There is no real argument you can make for LeBron to have less blocks, but you can always take advanced statistcs such as +/- to try and measure a players impact. But with advanced statistcs it creates conversations of accuracy and relevancy, as no statistic can tell a full story.

**Relationship**
As LeBron and Jordan never played in the same era there is absolutely no relationship between their averages, nor are there statiscs in games played against eachother (even if they did you could argue the relevancy of the statistics of games played against eachother). Nevertheless I tried to see if I could find relationships in there own statistics using my dataset. 

![broncorr](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/broncorr.png){:height="500px" width="500px"}

Key Observations: 
- Strong positive correlation (.69) between FG% and PTS
- Very strong positive correlation (.83) between STL and PTS
- Strong positive correlation (.74) between ORB and PTS
- Strong positive correlation (.65) between AST and DRB
- Very strong positive correlation (.80) between FG% and STL
- Weak yet positive correlation (.38) between BLK and ORB

You can make arguments as to why these statistics have positive correlations for example, his scoring efficiency seemed to be linked with his ability to steal and rebound. However, it's important to remember that correlation does not imply causation, and these relationships could be influenced by various factors, including the specific dynamics of each game, strategies used, and the opponents faced.

![jordancorr](https://graypas.github.io/Art-of-Data/assets/img/lab3_images/jordancorr.png){:height=500px" width="500px"}

Key Observations:
- Positive correlation (.64) between FG% and DRB
- Moderate positive correlation (.56) between DRB and AST
- Moderate positive correlation (.51) between BLK and PTS
- Weakish positive correlation (.41) between STL and ORB
- Weakish positive correlation (.43) between DRB and PTS

Unlike LeBron James' statistics, which showed stronger correlations among certain variables, Michael Jordan's stats have more moderate correlations, indicating more isolated performance aspects. For instance, Jordan's scoring (PTS) doesn't seem to be as strongly correlated with other variables like FG% or STL as in LeBron's case.

**Limitations**
If I could have I definitely would have had statistics of every game they played as not only would the presence between correlation of variables, it would also be easier to observe the two players offensive and defensive peaks. Really a huge limitation of just the numbers is that it really cannot measure the impact a player is having on a team's overall season, as both these players played with hall of fame level teammates who had crazy impacts on each game. The datasets also cannot measure the difficulty and skill level of the teams both players are facing.

**Conclusion**
Just from the dataset you can definitely argue that Jordan is a better defensive player, as the numbers are really evident. Offensively, Jordan did get more offensive rebounds but there are many factors going into why LeBron was not getting many and why Jordan was, there is also a huge point differential between the two players with Jordan having a 30 ppg career average. The offensive impact can be argued though as it was Jordan's role to be a point scorer while it was always LeBron's role to be the "do it all" guy, so in my opinion it can really go both ways, as LeBron's career ppg is only three points less than Jordan's while averaging more assists as a bigger player. It really just depends on what you are prioritizing. 
