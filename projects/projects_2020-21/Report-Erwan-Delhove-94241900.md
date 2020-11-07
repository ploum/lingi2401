# Open Source Contribution Project
*Author :* Erwan Delhove

*Date :* September-December 2020  
*NOMA :* 9424-19-00

## Project Research and selection
I never really participate in any open source project before. So I was kinda lost when I had to choose one.
I didn't know which one I will work on but I was sure on one thing: "I want to collaborate on open source application that I was currently using so that I could already have an idea about the goal of the project. But also because I want to contribute to tools that help me as a way of thanking their creators for their work."

### Libre Office
The first project that came directly to my mind, since I already use it a lot was Libre Office. It's a great tool for making different types of documents as PowerPoint, excel, normal text file, ... and has a large use in the open source world.
More information here: [repository](https://git.libreoffice.org/?format=HTML) and [source code](https://www.libreoffice.org/about-us/source-code/)

The only big problem with this kind of project is that it's way to big for an open source beginner like me. I will probably waste a lot of my time in understanding how to contribute to it and I will certainly have a high chance to be lost. So I decided to pass my way on this one.

### Notepad++
Another great tool that I have  kinda always used for my studies in computer science is Notepad++. For those who don't know, Notepad++ is a text or source code editor which supports a lot languages. We can say that it's a Notepad improvement as C++ for C.
The source code is available at [github](https://github.com/notepad-plus-plus/notepad-plus-plus)

More information on their [website](https://notepad-plus-plus.org/)

### Decision
After a few thoughts, I decided to pick Notepad++ as my open source project. 

## Project Contribution

### Integration of the community
29/09:
Since it's a big project and that I've never participated in any open source project, I decided to send an email to the project creator ["Don Ho"](https://github.com/donho) (email: <don.h@free.fr> ) in order to know what I can do to help. In that way, I'm pretty sure to have the best informations about what to do since hes probably the one who decide of everything.

03/10:
I still haven't received any answer from Don Ho. He's probably too busy or maybe I didn't choose the best approach to enter into the community. I will try at least to install the project on my computer with the given guidelines and think about how to enter the community later.


9/10:
There is two way that I could use in order to enter the community of notepad++ :
* Uses their dedicate [website](https://community.notepad-plus-plus.org/) which act like a forum.
* Users their [gitter](https://gitter.im/notepad-plus-plus/notepad-plus-plus) which allows a direct conversation between different people like Discord but for developpers and users of gitHub/gitLab.

Since I'm a shy guy, I decided to ask one of the maintainer ([sasumner](https://github.com/sasumner)) on gitter to know what I can do to help them. I choose this type of chat because it's easier since it allows direct interaction and will probably avoid me to lose too much time. Also, the maintainer seems very active on it, so I've a high chance to be taken into account!

### Building phase
04/10:
I'm encountering some problem with the building of the project. No matter what I do, It seems that I can't launch any build (release or debug). The release needs a sign SciLexer.dll version and the debug version fails due to a missing cpp class? Maybe I'm doing something wrong? I should ask the community on their dedicated [website](https://community.notepad-plus-plus.org/) to have more information.
Here is my [bug](https://community.notepad-plus-plus.org/topic/20100/troubles-building-and-executing-npp?_=1601977550761)

06/10:
I finally succeed to make the debug build working. The problem was due to SciLexer.dll which was generated for the x32bit version when the one I needed was x64bit. Thanks to the community, I successfully make it work!

### Issue(s) Collaboration

09/10: 
After a few discussion with [sasumner](https://github.com/sasumner), I finally found an issue to collaborate to which is [issue#8781](https://github.com/notepad-plus-plus/notepad-plus-plus/issues/8781).
The issue seems pretty easy to reproduce and seems simple to correct. The reason why I choose it is since the project is pretty big and that I don't where to begin, I need sometimes to adapt myself to the project and it will be easier if I start with an easy one.

10/09: 
The issue has a really strange behaviour and doesn't trigger each time. In addition, it seems that my computer suffers from visual studio 2017's debugger.
I need to investigate on these two problems to know where they come from and maybe redirect my choice.

12/10:
After a few investigations, it seems that the issue depends on the rapidity of the execution making it harder to solve.
For the other problem, it doesn't improve either!
The fact is that the issue is only triggered thanks to the shortcut (Ctrl + tab) which, when is executed, make my computer acting really slow and make the debug harder to follow. I've tried to see for solution online, but it doesn't seem to have a fix.
I ask the maintainer and two of my colleagues to know if they already encountered this behaviour, but they all answer me that they didn't.
I think I will stop with this issue for a while and going for another one. 
After a few times, I've already found another one to work on ([issue#8783](https://github.com/notepad-plus-plus/notepad-plus-plus/issues/8783))

22/10:
After a few code changes, the issue seems to be fixed! After checking the PR step to reproduce, I directly made one ([pull#9046](https://github.com/notepad-plus-plus/notepad-plus-plus/pull/9046)). It seems it has a problem with the building check but I remember that the commit on which  base myself wasn't the last one since it has building trouble. I'm awaiting comments about it and meanwhile I will go look for another issue to correct. After a small discussion with [sasumner](https://github.com/sasumner), I had to make a rebase to take the master fix into account. That will be my first rebase, I hope I won't break anything!

23/10 -> 26/10:
I got a review on my pull request from ["Don Ho"](https://github.com/donho). It seems I made a mistake in the code I first submit. Since it's an easy fix, I ask him if I should add an enumeration. He didn't answer so I deduct that this change wasn't necessary. I pushed my changes and wait for his feedback. A few hours after my PR was accepted. Even if the change is minor, I feel happy to have made it. Since this was a small issue, I decided to pick another one([issue#7750](https://github.com/notepad-plus-plus/notepad-plus-plus/issues/7750)).

27/10:
After adding two lines to the code it seems that the error was already resolved so I directly create a PR for it.

03/11:
Even if my PR was correct and easy, I found strange to see so much time passes between my correction and the merge. Maybe this fix wasn't really important that it was decided to merge it later?


### Issue(s) discovered
15/10
I have just launched my notepad++ application and it seems to have a strange error. I try with a fresh version to be sure of its presence and it was the case.
I tell the maintainer about my discovery and it seems to be an error that has never been there before.
Here is the [issue#9011](https://github.com/notepad-plus-plus/notepad-plus-plus/issues/9011). I will maybe try to fix when I'm done with the current one.

## Conclusion
After having contributed to this open source project, my vision about this "universe" change a lot. At the beginning I was afraid to not be really useful or to write code not sufficiently good enough to be accepted. But after a few tries, I managed to do it and I think that I will probably contribute again to the open source world in the near future!