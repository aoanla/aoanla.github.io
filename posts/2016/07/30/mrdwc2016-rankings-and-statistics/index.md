<html><body><p>As regular readers know, we've been regularly performing statistical analyses of Roller Derby for 2 years now. One of the first things we did was a <strong><a href="https://www.scottishrollerderbyblog.com/posts/2014/12/20/roller-derby-international-rankings-2014/">comparison</a></strong> of the rankings obtained at the 2014 Blood and Thunder World Cup with the inferred actual strengths of the teams present (as determined from the scores they achieved against other teams in the contest). We also performed a similar analysis against the first Men's Roller Derby World Cup, also in 2014.

At the time, we noted that MRDWC 2014 did rather better than B&amp;TWC2014, but that it was also much easier to run a tournament with good "true" rankings if you had less teams present. The <strong><a href="https://www.cerge-ei.cz/pdf/wp/Wp252.pdf">more teams</a></strong> you have, the more important seeding and tournament structure is in determining how close your final rankings are to the true orderings of team strength.

<strong><a href="http://mrdwc.com">Men's Roller Derby World Cup 2016</a></strong> has just completed, and it had rather more competitors than the first one (20, to the original's 15). This time, the teams were arranged in groups, carefully structured so that each group had 1 seed from the Top 4 of the 2014 MRDWC, 1 seed from the remaining Top 8, and the remaining 3 slots with teams from the bottom 7 from MRDC2014, or unseeded teams new to the tournament.

This seeding system, assuming that teams were roughly ordered in performance similarly to 2014 (and that no unseeded teams were better than the old Top 8) was designed to reduce the probability of poor rankings for teams in the tournament, whilst still allowing for the favoured "group playoffs + single-elimination tournament and consolation tournaments" structure.

So, how did they do?

</p><hr>

Although we no longer seriously use frequentist approaches to estimate team strength (as they're not capable of estimating the confidence range of the resulting estimates well, and have well-established deficiencies compared to Bayesian methods for these tasks), we will start with the (frequentist) Massey rankings for the teams, for comparison with the <strong><a href="https://www.scottishrollerderbyblog.com/posts/2014/12/20/roller-derby-international-rankings-2014/">previous article</a></strong>.
The table below shows Massey rankings (and calculated power) based on both Score Difference and Score Ratio, compared to the MRDWC official tournament placements. For both rankings, we've also calculated the rankings if you remove blowout bouts (defined here as bouts where the winner scored more than 10 times the loser), as blowouts particularly skew Ratio based rankings (as a single extra point scored by the loser can affect the ratio by a significant amount). We have <strong>bolded</strong> the teams where positions have changed, relative to the Official Ranking.
<table style="height:655px;" width="732">
<tbody>
<tr>
<td></td>
<td colspan="2"> All</td>
<td colspan="2"> No Blowouts (10%)</td>
</tr>
<tr>
<td>MRDWC Official
Ranking</td>
<td>Rank with respect to Score Difference</td>
<td>Rank with respect to Score Ratio</td>
<td>Rank with respect to Score Difference</td>
<td>Rank with respect to Score Ratio</td>
</tr>
<tr>
<td>
<ol>
	<li>USA</li>
	<li>ENG</li>
	<li>AUS</li>
	<li>CAN</li>
	<li>FRA</li>
	<li>ARG</li>
	<li>WAL</li>
	<li>FIN</li>
	<li>MEX</li>
	<li>SCO</li>
	<li>SWE</li>
	<li>BEL</li>
	<li>IRE</li>
	<li>GER</li>
	<li>ITL</li>
	<li>PR</li>
	<li>JPN</li>
	<li>CHI</li>
	<li>ESP</li>
	<li>NED</li>
</ol>
</td>
<td>
<ol>
	<li>USA 0.0</li>
	<li>ENG -136</li>
	<li>AUS -192</li>
	<li><strong>FRA</strong> -276</li>
	<li>CAN -292</li>
	<li><strong>MEX</strong> -416</li>
	<li><strong>ARG</strong> -418</li>
	<li><strong>WAL</strong> -435</li>
	<li><strong>FIN</strong> -454</li>
	<li>SCO -491</li>
	<li>SWE -538</li>
	<li>BEL -544</li>
	<li>IRE -546</li>
	<li>GER -618</li>
	<li>ITL -622</li>
	<li><strong>CHI</strong> -624</li>
	<li>JPN -630</li>
	<li><strong>ESP</strong> -693</li>
	<li><strong>PR</strong> -714</li>
	<li>NED -803</li>
</ol>
</td>
<td>
<ol>
	<li>USA 1.0</li>
	<li>ENG 0.338</li>
	<li>AUS 0.194</li>
	<li>CAN 0.119</li>
	<li>FRA 0.113</li>
	<li>ARG 0.0554</li>
	<li>WAL 0.044</li>
	<li><strong>MEX</strong> 0.0382</li>
	<li><strong>FIN</strong> 0.0325</li>
	<li>SCO 0.0209</li>
	<li>IRE 0.0187</li>
	<li>SWE 0.0183</li>
	<li>BEL 0.0182</li>
	<li>ITL 0.0132</li>
	<li>GER 0.0127</li>
	<li><strong>CHI</strong> 0.0092</li>
	<li><strong>PR</strong> 0.0088</li>
	<li><strong>JPN</strong> 0.0073</li>
	<li>ESP 0.0060</li>
	<li>NED 0.0031</li>
</ol>
</td>
<td>
<ol>
	<li>USA 0.0</li>
	<li>ENG -118</li>
	<li>AUS -218</li>
	<li><strong>FRA</strong> -266</li>
	<li>CAN -288</li>
	<li>ARG -409</li>
	<li><strong>MEX</strong> -412</li>
	<li><strong>WAL</strong> -435</li>
	<li><strong>FIN</strong> -447</li>
	<li>SCO -486</li>
	<li>SWE -532</li>
	<li>IRE -533</li>
	<li>BEL -542</li>
	<li>GER -614</li>
	<li>ITL -617</li>
	<li><strong>CHI</strong> -630</li>
	<li>JPN -637</li>
	<li><strong>PR</strong> -683</li>
	<li>ESP -692</li>
	<li>NED -787</li>
</ol>
</td>
<td>
<ol>
	<li>USA 1.0</li>
	<li>ENG 0.590</li>
	<li>AUS 0.286</li>
	<li>CAN 0.227</li>
	<li>FRA 0.223</li>
	<li>ARG 0.106</li>
	<li>WAL 0.0915</li>
	<li><strong>MEX</strong> 0.0869</li>
	<li><strong>FIN</strong> 0.0800</li>
	<li>SCO 0.0582</li>
	<li>IRE 0.0465</li>
	<li>SWE 0.0429</li>
	<li>BEL 0.0413</li>
	<li>ITL 0.0306</li>
	<li>GER 0.0283</li>
	<li>PR 0.0236</li>
	<li>JPN 0.0219</li>
	<li>CHI 0.0194</li>
	<li>ESP 0.0144</li>
	<li>NED 0.0099</li>
</ol>
</td>
</tr>
</tbody>
</table>

<hr>

Since the previous World Cup article, we've developed the theory of our statistical approaches somewhat, and now use Bayesian inference techniques to estimate the underlying strength of teams. (For example, see our <strong><a href="https://www.scottishrollerderbyblog.com/posts/2016/03/08/european-smackdown-the-statistics/">examination</a></strong> of the European Smackdown).

We took the full set of bouts from MRDWC 2016 and performed a Bayesian Monte-Carlo inference on them, to determine the estimated strengths of each team, relative to the top-ranked team, Team USA. As we are using Score Ratio here as our ranking mechanism, we also performed the same inference on the set of bouts with blowouts (&gt;1:10 ratio) removed.

<img class="alignnone size-full wp-image-8505" src="/2016/07/aus_wal_mex_fin_ire_can_ger_chi_itl_eng_arg_esp_sco_bel_fra_pr_jpn_swe_ned-mrdwc2016-all1.png" alt="AUS_WAL_MEX_FIN_IRE_CAN_GER_CHI_ITL_ENG_ARG_ESP_SCO_BEL_FRA_PR_JPN_SWE_NED-MRDWC2016-all" width="2000" height="1100"> Fig 1 - full set of estimated strength distributions, calculated with respect to estimated score ratio against Team USA

<img class="alignnone size-full wp-image-8495" src="/2016/07/aus_wal_mex_fin_ire_can_ger_chi_itl_eng_arg_esp_sco_bel_fra_pr_jpn_swe_ned-mrdwc2016-noblowouts.png" alt="AUS_WAL_MEX_FIN_IRE_CAN_GER_CHI_ITL_ENG_ARG_ESP_SCO_BEL_FRA_PR_JPN_SWE_NED-MRDWC2016-noblowouts" width="2000" height="1100"> Fig 2 - full set of estimated strength distributions, calculated with respect to estimated score ratio against Team USA, excluding bouts with blowouts (1:10 ratio)

It should be easy to see that, whilst removing blowouts does cause some global compression of the distributions (generally making the difference between the USA and everyone else look a bit smaller), there's a general maintenance of the relative features within the two results. The ordering of the results is the same as that for the Massey rankings derived from score ratios, although the precise values differ slightly (by less than 10% in all cases, and mostly less than 2%).

In particular, England, Australia, Canada and France are clearly in a class of their own at the top of the distribution (with England clearly separate from the other 3 as well), and Netherlands are clearly separate at the bottom end.
<table>
<tbody>
<tr>
<td>[gallery ids="8507,8508" type="rectangular"]</td>
</tr>
<tr>
<td>Fig 3: England and Australia highlighted in the results above.</td>
</tr>
</tbody>
</table>
<img class="alignnone size-full wp-image-8514" src="/2016/07/ned-mrdwc2016-noblowouts.png" alt="NED-MRDWC2016-noblowouts" width="2000" height="1100"> Fig 4: Netherlands distribution of score ratios, in the case where blowouts are excluded.

 

<hr>

 

As can be seen, there are actually relatively few points of disagreement between the MRDWC rankings and the true ordering of team ability. There are even fewer if we eliminate statistically insignificant differences (for example, Sweden, Belgium and Ireland are statistically identical in strength, so any permutation of their ordering is a valid one).

<img class="alignnone size-full wp-image-8517" src="/2016/07/mex_fin_wal-mrdwc2016-noblowouts.png" alt="MEX_FIN_WAL-MRDWC2016-noblowouts" width="2000" height="1100"> Mexico, Wales, Finland highlighted

The first placement error we see is Mexico. Narrowly missing out on the second group place in Group Green to Wales, the highest rank that Mexico could attain in the tournament stage was 9th, which they happily took. In fact, Mexico's predicted strength is  (narrowly) higher than that of Finland, who placed bottom of the Top 8 teams, qualifying via the second spot in Group Red. This results in a small placement error of just one position, as a result of the tournament structure (and the fact that Mexico is actually stronger than a seeded team). [Mexico does much better when ranked with score difference, as their bout against Canada was particularly low scoring, thanks to exceptional Mexican defence.]

Ironically, Mexico was originally in Group Red with Finland, only being moved to replace Colombia when they pulled out from the tournament only two weeks before. If they had remained in Group Red, they would likely have taken the second qualifier place, and attained that 8th place (while Finland would have taken 9th). In that instance, however, Scotland would have been significantly unfairly penalised for their group, being unable to attain the 10th place position that they did.

<img class="alignnone size-full wp-image-8520" src="/2016/07/jpn_chi_pr-mrdwc2016-noblowouts.png" alt="JPN_CHI_PR-MRDWC2016-noblowouts" width="2000" height="1100"> Japan, Puerto Rico, Chile highlighted (no-blowouts case)

Further down, the only other significant placement error concerns Puerto Rico, Japan and Chile. Coming 4th in their Group, Puerto Rico qualified for the 13th to 16th place tournament, where they placed 16th. The 5th Group place in their Group, Blue, was taken by Netherlands, the lowest-placed team in the tournament - literally every other team in the tournament was assured at least 4th place in that Group.

In fact, Puerto Rico's estimated true strength is statistically equivalent to that of Japan or Chile, who finished last in their group, and therefore were limited to a maximum final placement of 17th. (Complicating matters is that the team with which PR are statistically tied depends on if we include blow-outs or not - including that no-score game against USA pushes Japan's strength low enough that they look worse than Chile and PR, but this is probably unfair to Japan.)

Coming back to the statistically tied teams:

Team France will be cheered, perhaps, to note that their estimated strength is statistically inseparable from that of 4th place Team Canada. The France/Canada game was particularly closely contested in the first period, with Canada only managing a convincing win thanks to a much better second. [Indeed, when ranked on Score Difference, France look stronger than Canada, to a low significance, thanks to that low-scoring CAN/MEX game.]

<img class="alignnone size-full wp-image-8523" src="/2016/07/can_fra-mrdwc2016-noblowouts.png" alt="CAN_FRA-MRDWC2016-noblowouts" width="2000" height="1100"> France, Canada highlighted, showing statistical inseparability.

Our second set of statistically tied competitors are Sweden, Belgium and Ireland. While Belgium and Sweden played a close game, to Sweden's advantage, on Day 4, Ireland never played the other two - we'd suggest that such bouts would be worth organising!

Following them, Germany and Italy are also statistically inseparable, as are Puerto Rico and Chile (mentioned above).

If we consider statistically tied teams to have the same rank, then all of this means that our rankings for MRDWC would be (<strong>bold</strong> indicates disagreement with MRDWC, colours that there's a statistical tie with all teams of that colour and MRDWC's result might change if you ran it again):

 
<table>
<tbody>
<tr>
<td>1. USA
2. ENG
3. AUS
4= <span style="color:#ff00ff;">CAN</span>
4= <span style="color:#ff00ff;">FRA</span>
6. ARG
7. WAL
8. <strong>MEX</strong>
9. <strong>FIN</strong>
10. SCO
11= <span style="color:#3366ff;">IRE</span>
11= <span style="color:#3366ff;">SWE</span>
11= <span style="color:#3366ff;">BEL</span>
14= <span style="color:#993366;">ITL</span>
14= <span style="color:#993366;">GER</span>
16= <span style="color:#339966;">PR</span>
16= <span style="color:#339966;">JPN</span>
16= <span style="color:#339966;">CHI</span>
19. ESP
20. NED</td>
</tr>
</tbody>
</table>
 

Overall, MRDWC 2016 did particularly well for a "Groups+Single-elimination" style tournament of its size, with only ~2 significant placement errors, by only 1 or 2 ranks. Some of this is due to luck in the number of statistically-tied teams, but the construction of the seeded groups was clearly helpful in eliminating large-scale disparities - one of the two placement errors was specifically due to an unexpectedly high rank from an unseeded team. We hope that future tournaments will bear this in mind, if they decide to use a "Groups+Single-elimination" structure.

(This blog still favours <strong><a href="https://en.wikipedia.org/wiki/Swiss-system_tournament">Swiss-system tournaments</a></strong>, at least in place of Group stages; such a system would have eliminated both placement errors in this case, at the cost of a less easily read schedule on the second half of the first day, and much of the second.)

As always, these analyses are based on code available at our GitHub <strong><a href="https://github.com/aoanla/ranking-chain-inference">repository</a></strong>. (Some tweaking of filenames may be needed.)</body></html>
