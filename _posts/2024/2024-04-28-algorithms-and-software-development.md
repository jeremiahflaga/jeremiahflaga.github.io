---
layout: post
title: "Is learning algorithms irrelevant in software development for line-of-business applications"
excerpt: 
date: 2024-04-28 12:00:00 AM UTC
dateLastUpdated:
categories:
  - Programming
tags: 
  - Domain-Driven Design
  - DDD
  - Algorithms
published: false
---

A few days ago, I finished reading "Learning Domain-Driven Design" by Vlad Khononov.

After that, I started reading "The Algorithm Design Manual" by Steven S. Skiena.

![Learning Domain-Driven Design and The Algorithm Design Manual](2024-04-29-LearningDDD-and-AlgorithmDesignManual.jpg)

I am noticing some similarities in the wordings being used in the introductory chapters of both books. 

<!-- 
These similarities is important to me personally because I had heard someone before who said "solving algorithmic problems, like those problems in competitive programming, is not relevant in software engineering or software development". That was a huge factor in why I decided not to give that much time and effort in studying algorithms and related subjects.

Because of that, I did not give that much time honing my skill in solving algorithmic problems. 

I can understand that sentiment because [I had the same suspicion](https://jboyflaga2.blogspot.com/2015/10/frustration-during-college-solving.html) before I became a professional programmer for line-of-business applications.



Conclusion:

Skills in solving algorithmic problems is transferable to solving business problems using software.

 -->





Algorithm Design Manual (3rd edition)

page 11: Before we start thinking about algorithms, we need a careful description of the problem that needs to be solved.

page 13: Hunting for counterexamples iss a skill worth developing. It bears some similarity to the task of developing test sets for computer programs...

page 32: ... We use the RAM model because it is useul in practice.

Every model in science has a size range over which is is useful. Take for example, the model that the Earth is flat. You might argue that this is a bad model, since it is quite well established that the Earth is round...

Learning DDD

page 3: To design and build an effective solution, you have to understand the problem.

age 267


page 28:
a useful model is not a copy of the real world. Insted, a model is intended to solve a problem, and it should provide just enough information for that purpose.

"All models are wrong, but some are useful."

page 245:
only the paranoid survive.


Avoid the "things will be okay" mindset.



=================


Lesson: If you enjoy solving algorithmic problems, continue doing so because the skill you can gain from it is transferrable to other problem-solving domains such as creating software solutions to business problems.




=================


First hand experience when solving algorithmic problems




<table border="0" style="border: 1px solid #AAA; margin-bottom:12px; font-size: 60%;">
            <thead>
              <tr class="tablebar" height="25">
                <th id="nth_colspan" align="left" colspan="10" style="padding-left:10px; color:white">
                  <span style="float:right; font-weight:normal">
                  View : [ 
                    <a style="cursor:pointer" ng-class="{'lightgreen-color': show_last=='last', 'white-color': show_last!='last'}" ng-click="set_show_last('last')" class="white-color">last</a> |
                    <a style="cursor:pointer" ng-class="{'lightgreen-color': show_last=='yours', 'white-color': show_last!='yours'}" ng-click="set_show_last('yours')" class="ng-binding lightgreen-color">yours(14)</a>
                  ] &nbsp; &nbsp;
                  Show : [
                    <a class="white" style="cursor:pointer" ng-click="set_max_last_subs(5)">5</a> |
                    <a class="white" style="cursor:pointer" ng-click="set_max_last_subs(10)">10</a> |
                    <a class="white" style="cursor:pointer" ng-click="set_max_last_subs(50)">50</a> |
                    <a class="white" style="cursor:pointer" ng-click="set_max_last_subs(100)">100</a> |
                    <a class="white" style="cursor:pointer" ng-click="set_max_last_subs(500)">500</a> &nbsp; </span>
                  Submissions
                </th>
              </tr>
              <tr class="tablesubar">
                <th width="65" align="left">&nbsp; #</th>
                <th width="50">Rank</th>
                <th width="180" align="left">&nbsp; User (username)</th>
                <th width="110" align="left">&nbsp; Verdict</th>
                <th width="60">Lang</th>
                <th width="50">Time</th>
                <th width="120">Submit Time</th>
              </tr>
            </thead>
            <tbody id="num_gen_subs_tbody" class="alt_colors">
              <!-- ngRepeat: s in last_submissions | limitTo:max_last_subs --><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29424106&nbsp;</td>
                <td align="center" class="ng-binding">25740</td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#00AA00" class="ng-binding">&nbsp;
                  Accepted
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">0.460</td>
                <td align="center" class="ng-binding">1 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29424082&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">1 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29424064&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">1 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29424046&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29424047&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423886&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423869&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423868&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423842&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423839&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">29423828&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">Python</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2 hours ago</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">17327776&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">C++</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2016-05-08 02:40</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">17327761&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">C++</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2016-05-08 02:36</td>
              </tr><tr ng-repeat="s in last_submissions | limitTo:max_last_subs" style="height:18px" class="ng-scope">
                <td align="right" class="ng-binding">17327743&nbsp;</td>
                <td align="center" class="ng-binding"> - </td>
                <td><a class="ellipsis ng-binding" style="margin-left:5px; width:160px" target="_blank" href="/id/undefined">Jeremiah M. Flaga (jboy) (jflaga)</a></td>
                <td style="font-weight:bold; color:#FF0000" class="ng-binding">&nbsp;
                  Wrong answer
                </td>
                <td align="center" class="ng-binding">C++</td>
                <td align="center" class="ng-binding">-</td>
                <td align="center" class="ng-binding">2016-05-08 02:31</td>
              </tr>
            </tbody>
          </table>





