# Open Source Contribution Project
*Author :* Guillaume Everarts de Velp    
*Date :* November 2019    
*NOMA :* 50561500


## Research and Selection of the Project
To choose on which project I was going to work, I went as suggested on GitHub, on the page [Great for new contributors](https://github.com/showcases/great-for-new-contributors).  I found there a bunch of project that interested me.  Before choosing any, I looked a bit closer at the project to verify that it was still alive and well.  Then I looked the documentation they add, trying to guess how hard it would be for me to join this already running community.  This second part made me forget all the projects I had initially selected.  
Going back to GitHub, my attention got captured by a project that I know quite well but that I didn't consider contributing to at first because of its lack of originality (or so I thought), [Atom](https://atom.io), a simple text editor based on Electron, that you can extend with basically as much packages as you need.  Atom has a huge open source community, that hack has much in the core of the application as in the collection of packages they propose.  This is clearly a project that is not close to die.

## Communication with the community
After having sent a simple mail to [atom@github.com](mailto:atom@github.com) requesting the access to the Slack workspace of Atom and Electron I could finally properly join it.

The community is quite developed and well organized.  They use the Issues of GitHub to report problems and suggest improvements.  The contributions are made through Pull Request if it is related to a previously posted Issue.  The documentation about the product, the installation and the community can be found in their [Atom Flight Manual](https://flight-manual.atom.io/).  Most of the interesting information can be found in those two last things.  The Slack workspace isn't that much active and discussion over there are not always directly related to the project.  My only interaction with someone over there was in the  Electron channel and about technologies that allow to deploy web apps on mobile the same way as Electron does with desktops.

## Contribution
When I decided to pick Atom as project to contribute to, one of the element that made me decide was the presence of a [Beginner section](https://github.com/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+label%3Abeginner+label%3Ahelp-wanted+user%3Aatom+sort%3Acomments-desc) on GitHub for Issues for starters.  Unfortunately, what I didn't noticed back then was that they all already where kind off solved, just waiting for approbation.

For a long time I have been quite lost in this project, I couldn't find any contribution meaningful that interested me.  My interaction with the community was very limited and not very encouraging.  After having seen that other student had chosen this same project in the previous years, I decided to contact them, hopping to have some feedback of their experience and maybe some advices.  Unfortunately, from the three that made the project, I only found two valid email address, and none of those two responded to my desperate call.

It took me some times to come with my own idea.  It emerged after my 4th installation of the project from sources (I had to change multiple times of laptop this semester).  The installation is quite long, and you can easily miss one step, having a final result that doesn't work as expected.  And it can take some times to identify the step missed.  I then made a first move toward an even more automatic installation (on Linux at least).  The Issue I posted with this idea can be found here : https://github.com/atom/atom/issues/20204 .  

*03-12-2019* : It is currently waiting for a feedback from the community.  I already made an [implementation](https://github.com/geverartsdev/atom/commit/106eefe5105dc8650f6e7f44cb29f06fd7f0dc41), but I need to wait for approval of the need of this new feature before posting my Pull Request.

*09-12-2019* : Still no news from the community, the only activity that occurred under my issue was a mention that someone has made of my issue in another older one, but I can't even understand why.

*17-12-2019* : Still no news from the community, and my issue is buried under newer ones.  I sent a message calling for review on Slack to try to bring some attention to it.

*22-12-2019* : The message on Slack paid off, quite fast actually.  The feedback I received was not really supportive regarding my amelioration. But the people I have been speaking with seemed more enthusiastic for me to make a documentation upgrade about the same matter (making the installation easier).  So did I, my new pull request (on the [Atom flight manual repository](https://github.com/atom/flight-manual.atom.io) this time) is currently pending : [#583](https://github.com/atom/flight-manual.atom.io/pull/583).
