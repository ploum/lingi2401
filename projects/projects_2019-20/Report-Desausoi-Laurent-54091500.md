# Open Source Contribution Project 2019

*Author :* Desausoi Laurent<br/>
*Date :* December 2019<br/>
*NOMA :* 5409-15-00


## Research and Selection of Project
In order to find the repository that I wanted to contribute to, I first looked at [firstcontributions.github.io](https://firstcontributions.github.io/#project-list). Sadly, I was not interested in any of them. I also looked on Internet for recommended repositories. I also looked at previous year contributions to have some inspirations.

In the end, I preferred to chose an open-source software that I had already used in my personal projects in the past. I first started to look at [youtube-dl](https://github.com/ytdl-org/youtube-dl) but found it too cumbersome and I couldn't understand anything to the code as I was not familiar with the language. The next one was [spaCy](https://github.com/explosion/spaCy/) a Natural Language Processing utility that I used on a summer job and for a project. It is written in Python and Cython which I am very familiar with. Furthermore, I already knew how to use the utility avoiding me the burden to learn how to use it. Also, I found the project interesting and it is funny to implement a feature that I could used in some future projects.

I found the [issue](https://github.com/explosion/spaCy/issues/3637) pretty easily as they were not many. It was well described and the author explained very clearly how to implement the feature (what files to change and to what I should be careful about). I had found my project !


## Contribution
So for the [contribution](https://github.com/explosion/spaCy/issues/3637), the goal was to implement a new property to an object. As an equivalent property was already implemented I checked how it was used and how it was implemented. It took me quite some times to understand how everything was connected and linked together. They were indeed using a code architecture that I had never seen before.

After quite some time and debugging I figure it out on how to implement the property and the test going with it. However on my first [pull request](https://github.com/explosion/spaCy/pull/4697), I had included in the object structure the new property. It was a mistake that highlighted the owner of the repository. As the new property can be deduced from other ones, it was redundant to add it to the object structure size. As he suggested, I changed this part and pushed everything. To my opinion everything was fine (compilation was OK, tests OK). But for some reason, the owner did not respond to my updated pull request even though I wrote him a message.

In the end, it was very interesting to contribute for the first time to an open-source project and understand how a program that I have used in the past is working. However it ends up on a sad note as I have no clue from the owner on how to go any further. What reassure me is that other pull requests have not been merge even though they are finished. So I guess if merge everything once in a while.
