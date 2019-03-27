<html><body><p>Recently, Papa Whisky published an <a href="https://medium.com/@papawhiskey/how-do-rankings-work-1d0a1c5bc5d3"><strong>article on how the WFTDA Ranking system works</strong></a>.

This was a good introduction to the system, but perhaps missed a few technical points, which we feel are important. In addition, we think it might be useful to introduce other rating systems used in Roller Derby for comparison.

This article aims to address these two issues, and should be read in concert with the above linked article.

In this article, there is some maths. In this maths, we use: <strong>Pu</strong> to mean "the points scored by your team", <strong>Po</strong> to mean "the points scored by the opponent", as well as some other values later on.
</p><h2>Other Ranking systems - <a href="http://www.flattrackstats.com">FTS</a></h2>
While Papa Whisky implies that Flat Track Stats does ranking and rating in a similar way to WFTDA's own official ratings and rankings, in fact the FTS algorithm is somewhat different.

FTS ratings are a variant of <em>Elo ratings</em> - named for Arpad Elo, who developed them for Chess in the late 1950s. Rather like WFTDA Ratings, FTS Ratings are an indication of how well you should do, but with a different basis - Elo Ratings are logarithmic, like Richter factors for earthquakes, or decibels for sound, so every 400 (or so) difference in Elo Rating is a ten-<em>fold</em> (or so) factor in expected score <em>ratio</em>. [FTS probably doesn't use the number 400 exactly.]

FTS ratings also update based upon how well you do, versus your expected performance. FTS measures performance in terms of what they call "difference over sum" (DoS) - this is the ratio of the point spread (your points minus their points) to the total points (your points plus their points) in the game:
<p style="text-align:center;">(Pu-Po) / (Pu+Po)</p>
 Essentially, every game you play adds points to your rating, based upon how well you beat the expectation from your relative ratings. (The actual calculation used by FTS is not published, but classical Elo ratings give you a bonus based on the sum of your opponent's rating and a factor proportional to the fraction of the score you got.)

At any given time, a team's FTS Rating is the sum of all of the bonus points they have gotten over the team's entire history. [In fact, most teams will have more than one FTS Rating - FTS maintains multiple ratings; for WFTDA, MRDA, Europe, North America etc - which differ mostly in which games count towards a teams' total points.]
<h2>Other Ranking systems - MRDA</h2>
The MRDA also does not use WFTDA ratings or rankings for their quarterly ratings. In fact, non-members have no knowledge of how the MRDA Rankings are calculated.

This also means we can't say much more about it here, which is extremely problematic.
<h2>Other Ranking systems - <a href="http://aoanla.pythonanywhere.com/SRDRankv2.html">SRDRank (v1,2)</a></h2>
Our own rating system, SRDRank, is the most different in principles to the rating systems here.

Every other rating system works on pairwise comparison - a given game affects only the ratings of the two teams which play, and the rating of Team A will be the sum of all the effects from the games in its history.

SRDRank is based on global optimisation: every game doesn't just tell us something about the two teams which played, but also something about every other team which has played them recently, and so on.

SRDRank v1 and v2 perform this calculation in slightly different ways, but in both cases they care about the points ratio:
<p style="text-align:center;">Pu/Po</p>
in any given game. (Technically, we use log(Pu/Po), but that doesn't affect understanding.)

SRDRank v1 models each game as a "spring" between the two teams (which has a natural length proportional to the result of the game) - we run a simulation of the system with all the springs in place, and see where it ends up putting all the teams. The relative positions of the teams as the result of the springs tensioning against each other give their "ratings", and "Rankings".

SRDRank v2 uses least-squares linear regression to do the same thing. This is a technique to find the values for a set of unknowns (in this case, the team strengths) which "best fit" the observations (in this case, the ratio of scores in the games played) by minimising the distance between the results in reality, and the results predicted by the rankings.

Both SRDRank v1 and v2 adjust the importance of games so that older games are less significant than newer ones (by making the springs "weaker", or by allowing more distance with less penalty) - the amount we do so has been optimised itself by analysis of the history of the sport.

SRDRank v2 also attempts to detect teams which have changed suddenly in strength (because, say, their roster completely changed at the start of the season), by performing statistical tests on the predictions it makes. Teams which do change suddenly are "split" into a new and an old team, at the point of the change - which means both that the new roster can be given a different rating to the old one; and also that the history of the team doesn't contaminate our predictions for teams which play them in future.

SRDRank v1 and v2 are included in our github repo for prediction code, <a href="https://github.com/aoanla/ranking-chain-inference"><strong>here</strong></a>.
<h2>Pros and Cons of Rating Systems - WFTDA</h2>
In his article, Papa Whisky notes that one of the weaknesses of the WFTDA rating system is that it is currently slightly opaque - the magic "median" value isn't what you'd expect it to be from the published results, because the WFTDA median is calculated from a longer list which is not published.

However, that isn't the real problem with WFTDA ratings - although it is related. To explain their issues, we'll need to do a little bit of simple mathematics.

As you know from the article, WFTDA ratings award you points for any sanctioned games based on the result of the calculation:
<p style="text-align:center;">300 * Pu * So / (Pu+Po)</p>
where So is the Strength Factor of the opponent. Given that a Strength Factor is just the WFTDA Ranking Points divided by the median Ranking Points, we can write this as
<p style="text-align:center;">300 * Pu * Ro / ( Pu+Po) * Rm</p>
where Ro is the opponent's ranking points, and Rm is the median of them.

In order to "keep the same rating", a team needs to score equal to its current WFTDA Ranking Points. So, we can write the condition for retaining Rating as:
<p style="text-align:center;">300 * Pu * Ro / ( Pu+Po) * Rm = Ru</p>
This relationship is the source of all of the issues with the WFTDA Rating system.

Firstly, let's rearrange this to give the fraction of points the team needs to score to maintain rating, in terms of everything else:
<p style="text-align:center;">Pu/(Pu+Po) = (Ru/Ro) * (Rm/300)</p>
So, the first thing we notice is that the "fraction of points" you need is proportional to the <em>ratio</em> of the two teams' WFTDA Ranking Points. This is the source of those "weird results" which Papa Whisky notes for bouts between teams of very different strengths.  In particular, it can mean that there's simply not enough available points for a team to retain its ranking, even if it got 100% of the points.

To see that that's true, let's imagine that our team gets 100% of the points, so Pu/(Pu+Po) is 1. That implies that
<p style="text-align:center;">(Ru/Ro) = (300/Rm)</p>
<p style="text-align:center;">or</p>
<p style="text-align:center;">Ru = (300/Rm)*Ro</p>
300/Rm is a bit more than 2 (we'll come back to this later), so our team needs a 100% blowout to break-even against a team with about<em> twice</em> its Rating. In the example Papa Whisky uses, Gotham had a SF (and thus rating) more than twice that of Windy: there was no possible way for Gotham to benefit from that game, as they would need to score <em>more than 100%</em> of the points!

The other problem is that teams need to continually beat expectations in order to retain ranking. To see that this is the case, let's assume that the two teams have identical WFTDA Ranking Points, Rx. In that case, the formula gives:
<p style="text-align:center;">Pu/(Pu+Po) = (Rx/Rx) * (Rm/300) = Rm/300</p>
where the final step is straightforward.
If a team plays a team with exactly the same strength as it, we would expect the points to be divided equally, so Pu/(Pu+Po) should be 0.5 ... which implies
<p style="text-align:center;">0.5 = Rm/300  ⇒ Rm = 150</p>
Of course, Rm does not equal 150 - it's set to the median WFTDA Ranking Points, which is currently around 141.

The result of this is that teams need to <em>beat</em> their own expectation by about 7% in every game, <em>just to stay where they are</em>. In a case where two well matched teams perform as expected... not only does the losing team lose ranking, but so does the <em>winning</em> team. (This does balance out a little, in that it affects all teams, so there's a general "deflation" in scores one month to the next... but it is still counterintuitive.)

The Pro of the WFTDA rating system is that it's very easy to understand, and you can calculate expected scores and so on with just a piece of paper and some mental arithmetic (as long as you know the median Ranking Points). However, with computers ubiquitous nowadays, it is not clear how much of an advantage this is - <a href="https://derbyontoast.com/head-to-head"><strong>DerbyOnToast</strong></a> (and our own SRDRank visualiser) can both automate ratings calculations for you, so you don't need to be able to do them yourself.
<h2>Pros and Cons of Rating Systems - FTS</h2>
The FTS Rating system has all the problems that Elo systems have in general.

In particular, Elo ratings consider that all results are relevant, even years after they happened. Rating changes only happen as a result of new games being played - so if you don't play any games for a year or two, you'll just keep the same FTS rating regardless.

This has the counter-intuitive result that it's sometimes better to just not play games, rather than lose rating. (If Gotham had decided not to play any games at Champs or later, they'd still be top of the leaderboard... more strikingly, the Oly Rollers retained a significant FTS rating for several years, despite not entering any scores at all.)

Related to this, FTS ratings take time to adjust to sudden changes - if a team suddenly becomes much weaker or strong (due to, say, a complete change of roster), it takes quite a lot of games for FTS to catch up, as there's only so much change FTS can accommodate in a single bout. Additionally, while this adjustment is taking place, all of the opponents have unfair rating changes - FTS changes are symmetric, so for team A to gain rating, team B must lose rating, even if the cause is entirely due to a change in team A.

FTS's advantage is that, like WFTDA Ratings, FTS ratings are quick and easy to calculate. So quick, in fact, that FTS recalculates all of its ratings at least once an hour, to guarantee that predictions are as up to date as possible.

FTS also does not suffer from either of the problems of WFTDA Rankings - there is no combination of teams for which either team "can't win".
<h2>Pros and Cons of Rating Systems - SRDRank</h2>
SRDRank, being a different class of rating system to the other two, has entirely different issues.

SRDRank's main issue is its relative complexity. Whilst least-squares regression, and statistical tests, are no more advanced than first year undergraduate level, this is still a significant increase in complexity over the other two.

SRDRank's other issue stems from the global nature of its calculation. As with FTS, an undetected sudden change in team strength can cause unwanted effects in the ratings of other teams. As SRDRank is a globally optimised rating, this effect can make (small) changes in rating even for teams which never play the team in question. We attempt to minimise this effect via the statistical test and splitting step, but there will always been a short period where there's not enough evidence to detect a sudden change, and where ratings will be somewhat affected.

Finally, SRDRank is limited by the depth and quality of information available to it. Because it uses FTS's own records as a data source, it can only use information that FTS consider relevant. Because of this, there a several uncontrolled sources of error which reduce SRDRank's accuracy - we don't always know if there's a "home" team, as FTS doesn't track the host of a bout, and assumes that one team must be a "home" team regardless - and for tournaments, FTS is poor at assigning hosts for tournament type events which run over many fixtures; we don't know the length of a bout (which affects the reliability of a rating); we don't know rosters for most games (because most bouts don't upload statsbooks), so we can't model expectations based on players who are missing or present - and so on.
We also, of course, as with all rating systems, can't rate teams for whom there is no information at all. If your team doesn't upload stats or scores to FTS, then FTS and SRDRank can't rate you. Historically, this has affected Mexico and Latin America as whole more than most other reasons, which is extremely problematic, as it also decreases visibility of the fantastic amount of derby happening in those areas.

In comparison, SRDRank can rank and rate the entire world's roller derby teams, not just subsets of them. It also allows detection of cliques within the community - groups of teams which play each other more than others, and thus are better rated relative to other members of the group than the outside world - and selection of ratings based on geographical location.
<h2>Summary</h2>
Knowing a bit about possibilities for rating systems is important in judging how to use them (and which ones are good at which things).

If you're interested in gaming your WFTDA rating, it's best to avoid playing teams with less than 70% of your rating (to avoid matchings where you simply can't score enough to improve your rating, regardless of what you do); and preferably play teams closer in rank to you, but who you think you can beat by more than 10% of the score...</body></html>
