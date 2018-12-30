---
layout: post
title:      "Rails w/ JS Project: Swapping Out Master Branch"
date:       2018-12-30 08:24:33 +0000
permalink:  rails_w_js_project_swapping_out_master_branch
---


Especially due to a four month hiatus from the Learn curriculum, this project was exceedingly more difficult for me than the previous ones. I was nearly dumbfounded in the beginning, overwhelmed by the list of tasks and my lack of immediate confidence regarding how to tackle them. I admit to feeling frustrated in the beginning. An entire day's hardwork would render only an inch of tanglible progress. During the first few days, the vast majority of my time spent working was actually time spent reviewing and researching. But my progress accelerated at a more rapid pace with each day, and now I'm on the other side! 

There is one pesty bug experience I'd like to share about. I'm not sure my resolution can actually be considered debugging, more like a workaround. After reverting to an old commit on my active javascript branch, I was unable to merge my successfully edited branch with my master. The javascript branch was all up-to-date, but I was being hit with a merge conflict in log/development.log. The issue seemed more complex than it’s worth, and after a quick google, I learned that it didn't really matter which branch is your master branch. I wanted to get rid of this program by simply making my current up-to-date branch my new master and getting rid of my old master branch altogether. Here's how:

1. Rename master branch. For example rename it to 'dont-need-me.' (**git branch –m master don’t-need-me**) 
     
2. Push to Github (**git push origin don’t-need-me**)

3. Delete master branch on Github

4. Delete old master on local repo (**git don’t-need-me -D**)

5. Rename working branch to master, (**git branch –m javascript master**)

6. Push to Github (**git push origin master**)

7. Make sure the new master branch is set as the default branch on Github

8. Delete old working branch on Github





