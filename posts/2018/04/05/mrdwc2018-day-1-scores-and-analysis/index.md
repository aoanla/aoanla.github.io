<html><body><p>This year, the <a href="http://mrdwc.com/schedule-2018/"><strong>Men's Roller Derby World Cup</strong></a> is trying something new with its tournament format. Nothing so radical as the Roller Derby World Cup in Manchester - they're still using Groups and Elimination to sort their teams - but they're playing a bit with that transition from Group to Elimination Tournament in an interesting way.

Traditionally, we want to arrange the number of Groups to be a power of 2 - 2,4,8 - because this means that if we allow the top 1 or 2 to graduate in each Group, we also have a power of 2 number of teams playing in the Elimination phase. Elimination phases work most straightforwardly when there are a power of 2 teams playing, so this is a good thing.

MRDWC also wants a power of 2 number of teams in their Elimination - they want 8 of them - but there are 24 teams playing. (Originally, there were 25, which is even worse, and that situation made the following approach look like the best one.) Whilst 24 is divisible by 8, the result is 3, and Groups of 3 are rather hard to balance well; similarly, Groups of 6 (with 4 such) are quite large, and need a lot of games per Group (15, for a total of 60 games in the Group phase).
Instead, MRDWC have decided to have 6 Groups of 4...

...but this leaves them with the problem of how do you pick 8 teams to go forward, when there's only 6 Groups?
The solution MRDWC have adopted is to allow all 6 "winners" of their Group to go through, and then supplement them with the "best" 2 of the 2nd-place teams in the Groups. (That is: of the 6 teams who placed 2nd in a Group, we try to pick the best 2 of them.) This is obviously tricky to do fairly, and the solution which MRDWC are using is to assume that the "total points difference, not counting the worst game" is a fair enough yardstick.

All of the teams have played 2/3 of their games now, at the end of Day 1, so we should have a pretty good idea of how they're doing - and we can have a stab at using inference to predict their final games, too, to make a prediction of who will get those two extra Elimination Slots.

Where we have used actual scores, these are taken from the official MRDWC score page, linked at the top of this article.

Groups: <strong><a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/2">RED</a></strong> <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/3"><strong>ORANGE</strong></a> <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/4"><strong>YELLOW</strong></a> <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/5"><strong>GREEN</strong></a> <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/6"><strong>BLUE</strong></a> <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/7"><strong>PURPLE</strong></a>
Day Two: <a href="https://scottishrollerderbyblog.com/2018/04/05/mrdwc2018-day-1-scores-and-analysis/8"><strong>Predictions and Games To Watch</strong></a>
<!--nextpage-->
Starting with Group RED:

the Scores to date are:

USA 286 : 0 NED
BEL 189 : 53 JPN
USA 311 : 0 JPN
BEL 164 : 46 NED

Given that the USA are very likely group winners, we can ignore games against them for points difference, as those will be the worst games for the other team - as a result, we only know Belgium's final "effective" P/D for the group, which is 254.
Japan take their -136 from the Belgium game, and will add to it their P/D against Netherlands tomorrow. Similarly, Netherlands take their -118 from their Belgium game, and will add it to the P/D from the same game against Japan tomorrow.

Performing a linear regression against the existing scores, we can predict the following relative strengths in terms of expected P/D:
</p><p class="p1"><span class="s1">USA:192.25
</span><span class="s1">BEL:20.25
</span><span class="s1">NED:-95.25
</span><span class="s1">JPN:-117.25</span></p>
Thus, the "most likely" results for the Japan/Netherlands game are a narrow 22 point win for Netherlands, giving a <strong>predicted</strong> P/D for the two teams as:
Netherlands: -96
Japan: -158

This group has been remarkably consistent, and the R-squared value (a measure of how well we can explain the performances so far with a linear approximation) is 0.99, almost at the maximum value of 1!

<!--nextpage-->
Next, we'll look at Group ORANGE:
Scores to date are:
SWE 80 : 81 ESP
ENG 202 : 11 CHI
ENG 248 : 20 ESP
SWE 81 : 33 CHI

The big surprise for this group was the exceptionally close game between Sweden and Spain, which literally came down to the final pass in the final jam! England are causing no surprises, however, and are very likely to win the group - so we can discount their contributions to P/D for the other teams.
As a result, we only know the effective P/D for Sweden, which will be 47.
Spain carry forward their 1 point P/D against Sweden, and will add to it the P/D from playing Chile tomorrow; Chile carry forward their -48 from their game against Sweden, and will add the P/D against Spain.

Again, performing linear regression against the games so far, we predict relative strength as:
<p class="p1"><span class="s1">ENG:151.25
</span>SWE:-34.75
<span class="s1">ESP:-55.25</span>
CHI:-61.25</p>
Giving a predicted exceptionally close game between Spain and Chile tomorrow, with a P/D of only 6 for Spain (to win).
Thus, the most likely <strong>predicted</strong> P/Ds for those teams are:
Spain: 7
Chile: -54

The R-squared measure for this group is noticeably lower than that for the previous group, at 0.848 - we expect the Spain/Chile game to be exceptionally hard to call, and 2nd place is up for grabs between Spain and Sweden as a result.

<!--nextpage-->
Moving now to Group YELLOW, where the final positions are possibly the hardest to call out of any of the groups.

Scores so far are:
AUS 254 : 42 COL
SCO 183 : 74 ITA
AUS 225 : 25 ITA
SCO 224 : 6 COL

Coming into this tournament, Australia were seeded as the "expected" winners of this group - however, comparing just the two games against Colombia, Scotland have the higher points differential (and held Colombia to a much lower score). As a result, it is exceptionally hard to predict even the 1st place position in this group.

Linear regression on the scores so far gives a <strong>predicted</strong> relative strength of:
<p class="p1"><span class="s1">AUS:114.75
SCO:70.75
ITA:-63.25
</span><span class="s1">COL:-122.25</span></p>
However, the R-squared for this group is just 0.053, an incredibly low value. As a result, the expected standard error (the amount by which these strengths could be out by) is a huge 28 - larger than half the difference between Australia and Scotland, and thus an indicator that an upset is definitely possible.

Group YELLOW, then, will come down to the results of the final two group games tomorrow!

<!--nextpage-->
Our next group, GREEN, is a return to a somewhat more predictable group in terms of performance.

Scores so far:
MEX 275 : 3 POL
CAN 182 : 5 GER
GER 160 : 34 POL
CAN 94 : 43 MEX

Whilst Mexico's performance against Poland was very impressive, Canada's win against them confirms Canada as the 1st place team in this group, and Mexico as 2nd place.

As such, we can only confirm the P/D for Poland at this point, at -398.
Germany will bring forward their P/D against Poland, 126, and add to it their P/D against Mexico; Mexico will bring forward their P/D against Poland, 272, and add it to their P/D against Germany!

Linear regression predicts:
<p class="p1"><span class="s1">CAN:135.25
MEX:89.25
GER:-46.75
</span><span class="s1">POL:-177.75</span></p>
(with an R-squared of 0.988, so a very consistent group)
And thus a resulting P/D between Germany and Mexico of 136 to the Mexicans.

The resulting <strong>predicted</strong> P/Ds for Germany and Mexico will therefore be:
Mexico: 408  (!)
Germany: -10

<!--nextpage-->
Moving on to our second-last group, BLUE, we're back to a slightly inconsistent group - although nowhere to the extent of Yellow.

The scores so far are:
FRA 255 : 10 PHI
FIN 86 : 62 IRE
FRA 214 : 25 IRE
FIN 183 : 32 PHI

It's fairly clear that France are, as their seed suggested, the very likely winners of the group - so we can assume that their P/D contributions will be ignored for the other members of the group.
As a result, the only team with a "final" P/D is Finland, with 175.
Philippines will take their P/D versus Finland, of -151, and add the result of their game against Ireland; Ireland will take their P/D against Finland, of -24, and add the result of the same game to it.

Again, linear regression suggests likely strengths within the group are:
<p class="p1"><span class="s1">FRA:129.625
FIN:15.125
IRE:-34.125
</span><span class="s1">PHI:-110.625</span></p>
<p class="p1">Leading to a predicted P/D for the Philippines / Ireland game of 76.5 in Ireland's favour, with a resulting <strong>predicted</strong> total P/D for those teams of:
Ireland: 52.5
Philippines: -227.5</p>
The R-squared for this group is a fairly low 0.644, however, with an attendant high standard error, so these results also come with a caution!

<!--nextpage-->

Our final group is PURPLE.

Results for this group are:
WAL 225 : 22 DEN
ARG 244 : 38 NZ
WAL 185 : 23 NZ
ARG 231 : 21 DEN

Even without doing linear regression, we can see that the scores suggest that Wales and Argentina are actually fairly closely matched - like group Yellow, it's actually not completely certain that the top seed for the Group, Argentina, will win against the second seed, Wales.

Linear regression suggests strengths like:
<p class="p1"><span class="s1">ARG:110.375
WAL:84.875
NZ:-86.375
DEN:-108.875</span></p>
With the standard error on those strengths a relatively low 10.342 - but given the closeness of Argentina and Wales' strengths, enough to allow a possible upset.

<strong>Predicted</strong> P/Ds for the two games tomorrow are:
NZ - DEN: 22.5
ARG - WAL: 25.5

but the result for Argentina / Wales only matters to decide which team will be the 1st and which will be 2nd, as both have already played the games which decide their P/D for the group - Wales with P/D 365 and Argentina with P/D 416.

<!--nextpage-->
<h3>Predictions looking ahead.</h3>
<p class="p1"><span class="s1">Looking ahead to the elimination phase, then, we can ask what the most likely 2nd Place teams are to make it into the top tier of the playoffs...</span></p>
For some of the groups, the 2nd place team is fairly predictable, and we can use our "estimated" P/D to place their rough position in their peers when the teams have not played all relevant games. Where we have "predicted", we've used our best guess at the P/D for a game which has not been played - in the other cases, we're assuming only that the current likely winner of the Group actually wins.

RED: Belgium (P/D 254)
ORANGE: Spain (P/D [<strong>predicted</strong>] 7) [note: Sweden will probably have a higher P/D, but less wins]
(It is possible that Chile will win against Spain, in which case Sweden would take 2nd Place, with a P/D of 48, not enough to qualify for the Top 8)
GREEN: Mexico (P/D [<strong>predicted</strong>] 408)
BLUE: Finland (P/D 175)

For YELLOW and PURPLE, there is the potential for upsets, as 1st Place is in contention for both groups.

YELLOW: Scotland? (P/D 327)
YELLOW: Australia? (P/D 415)

PURPLE: Wales? (P/D 365)
PURPLE: Argentina? (P/D 416)

This leaves us with a very interesting position in terms of the promotion structure: if Australia and Argentina lose their groups, their P/Ds are very close, and very close to our estimated P/D for Mexico after their final game - the teams who qualify for the top 8 will be determined by Mexico's performance against Germany.

If Australia or Argentina lose their groups, then it looks like Wales and Scotland will be fighting it out between Yellow and Purple for the second "2nd Place" spot in the Top 8, with the result also depending on how well Mexico does...

So, it really is all to play for tomorrow, with the top 8 (and the rest of the leaderboard) really hinging on 3 important games:

Wales v Argentina [9am BST Track 2]
Australia v Scotland [10am BST Track 1]
Mexico v Germany [11am BST Track 2]
(Spain v Chile [midday BST Track 1])

 
<p class="p1"></p></body></html>
