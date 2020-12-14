# Open Source Contribution Project

| Author : | Kilian Maes   |
|----------|---------------|
| Date :   | December 2020 |
| NOMA :   | 09461500      |

## Abstract

As many other students, it took me a lot of time to find a project for which I had an idea of PR to submit. Finally, I made a PR for a project already presented by another student (Matthieu Meert), the OpenShot Video Editor. This PR (only 3 lines modified) intends to correct a bug, a window not popping up when clicking on a button. An active contributor to the project confirmed that this was a bug  and he reviewed my PR. I updated the PR according to his remarks and it was merged.

## Looking for a project

I have considered contributing to several different projects. I won't discuss all of them below, only a few that are representative.

At the beginning, I looked for a project that I used on a daily basis. So, I asked myself: *Which open source projects do I use in my daily life?* The answer is that most of these projects are very large projects, with lots of contributors: VS Code, Ubuntu, VLC media player... I took a look at the repositories of these projects but I rapidly concluded that I would probably be easier for me to contribute to a smaller project for these reasons:

* It seems easier to find a bug or a new feature that will be accepted for a project having a small community (e.g. the bugs need more time to be corrected).
* In the case I'd want to propose a PR for an issue posted by someone else, there are less chances that a contributor proposes a PR before I have the time to submit mine.
* By looking at several repositories, I had the impression that small communities were more friendly for new comers (for example, some repositories used the tag "good-first-issue" on some issues).

So, I decided to try to focus on projects not too large.

### RforMassSpectrometry

*RforMassSpectrometry* (https://github.com/rformassspectrometry/RforMassSpectrometry) is a R package used to process data obtained from mass spectrometers. I need to use this package for my master thesis, and I had an idea of feature to implement. Given that this project is related to my master thesis, I wanted to be sure that it would be accepted for my contribution to the LINGI2401 course and I contacted the teacher, Lionel Dricot. He drew my attention on the fact that this project only has a few contributors. So **I decided to look for a project with a larger community I could potentially interact with**.

### igraph

Then, I decided to take a look at igraph, a C library made to manage graphs. I first took a look at the CONTRIBUTING.md file, which was quite complete, a good point. Moreover, several issues had the label *good-first-issue*, which tends to show that new comers are welcome to the project. On their website, I found detailed installation instructions that allowed me to install the library from the repository without too many problems. I selected a feature requested by an active contributor which seemed not too difficult and wanted to take a look to check its feasibility for someone having a bad knowledge of the project structure, me.

According to the information for the developers, I needed to switch to the *develop* branch because the feature was API breaking, it would add an argument to a function. I tried to recompile the source code from the *develop* branch and I didn't manage to do it. Some configuration files available on the master branch were not on the develop branch: I couldn't use the same instructions to compile the library. I hesitated to copy the configuration files from the *master* branch to the *develop* branch but I wasn't sure it was the proper way to proceed. I couldn't find how to compile from the *develop* branch in the documentation.

I was sad this information was missing in the documentation, which is essential for new comers, and I hesitated to request help from the community, but I wasn't sure if I would manage (and really wanted) to implement the feature I had spotted, and I had the feeling that I was going to bother people for nothing. This stage of my research allowed me to realize the importance to **have a very complete documentation**, both for users wanting to use the project but **also for potential developers**.

### memegen

Then, I considered the possibility to add a feature to a meme generator (https://github.com/jacebrowning/memegen). I won't go in the details, but I never managed to make it run on my computer. I think that to avoid discouraging potential contributors, **projects should ideally be easy to run on most distributions**, which is not always the case.

### OpenShot

After the presentation of the PR of Matthieu Meert on OpenShot, a Video Editor, I decided to install the program. I intended to use it for the Seminar course (we need to present a paper in a video). While getting started with OpenShot, I found a bug. I decided to make a PR to solve this bug.

## Proposing a PR

When going in the Toolbar > Help > About OpenShot > Credits, I noticed that clicking on the Credits button had no effect (while clicking on the other buttons had for effect to pop up a new window).

![Screenshot: https://i.ibb.co/mF10kJp/openshot-before.gif](https://i.ibb.co/mF10kJp/openshot-before.gif)

I decided to create an issue (https://github.com/OpenShot/openshot-qt/issues/3908) to ask to the other contributors if they had the same bug, to be sure it was not something specific to my installation/configuration.

Then I took a look to the source code to see what was the origin of the bug. Luckily, an error message was printed in the console each time I clicked on the button which allowed me to know exactly from which file the error came from. I managed to solve the bug by changing two lines. The main reason of the bug was an inversion in a tuple:

```
(var_2, var_1) = function(...)
# Instead of
(var_1, var_2) = function(...)
```

Because I had a solution for the bug, I decided to directly send a PR (https://github.com/OpenShot/openshot-qt/pull/3909), without waiting for other contributors of the community to confirm they had the same bug. I thought that if they reproduced the bug, they would want to take a look at the code and they would solve the bug. Because I intended to do it myself, it was useless to make the same work several times.

![Screenshot: https://i.ibb.co/Sv77QhQ/openshot-after.gif](https://i.ibb.co/Sv77QhQ/openshot-after.gif)

My pull request was quickly reviewed by an active contributor. He confirmed that I had corrected a bug and he mentioned two improvements I should do in the three lines I had changed... I made the changes and the PR was merged after a few days.

## Discussion

My impressions:

* It's difficult to make a PR without having a priori a precise idea of project and feature/bug to implement/solve.
* Many projects seem very friendly for new comers, even if it's not always easy to make them run in local.

In the case of my PR, it was straightforward to solve and it didn't need to interact a lot with the community of the OpenShot project (there was no need to make decisions and I haven't been stuck). However, by opening first an issue and then proposing a pull request as I did, I think that more advanced discussion could have been conducted very easily if needed.



