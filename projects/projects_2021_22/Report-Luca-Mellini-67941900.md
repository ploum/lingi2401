# Open Source Contribution Project

*Author :* Mellini Luca

*NOMA :* 67941900

*Year :* 2021-2022

*Selected project :* [VerbCalc](https://github.com/ErykPiasecki07/VerbCalc)

*Selected issue :* [Issue #30](https://github.com/ErykPiasecki07/VerbCalc/issues/30)

*Pull Request :* [Pull Reaquest #51](https://github.com/ErykPiasecki07/VerbCalc/pull/51)

&nbsp;
# Project Selection

Since I'm very new in the world of Open Source, I kind of struggled finding an interesting project I could bring an usefull contribution to. I indeed spent a lot of time just finding the "sector" I wanted to dive into. 

First of all I wanted to give a contribution to a video game I play a lot since years, which is [Osu!](https://github.com/ppy/osu). The project is in heavy development, has a lot a contributors, a very complete documentation, but requires a programming language and a Framework I don't master at all. Thereby I couldn't end up finding an issue I could give a contribution to while still feeling myself usefull.

I kept thinking about other projects but then I thought about Python, which is the programming language I used the most all along my schooling but also the one I would like to keep improving myself with.

So I looked for a Python project when a friend of mine ([@RosarNicolas](https://github.com/RosarNicolas), also student for that course) told me about the website [Good First Issues](https://goodfirstissues.com/) which includes all the issues having the tag "good first issue", sorted by the most recent ones.

I finally ended up finding an issue about [VerbCalc](https://github.com/ErykPiasecki07/VerbCalc), a Python library created in order to make calculations from natural language. 

The project is quite new so it doesn't have lots of contributors but I found the concept interesting since it reminds me another course where I had to create my own programming language in which I actually wanted to add such a feature.

I think my knowledge in Python can bring something to this project and I therefore can't wait to work on it.

&nbsp;
# Contribution

The issue ( [Issue #30](https://github.com/ErykPiasecki07/VerbCalc/issues/30) ) I asked to be assigned to consists of handling written numbers (make "two" appears as "2" for example).

My first step in the contribution was to make some local tests, see if the main issue (convert a literal number into its integer) can be easily fixed or not (it initally sounded like an easy issue to me). And it was indeed surprisingly easier than I thought since I was able to achieve it in only one day of work.

I was now able to translate any possible sentence containing a literal number (receiving "three thousand six hundred and thirty two" would output "3632"). After asking the project owner some precisions (concerning the use of hyphen, the "and" word and the way I could integrate it), I had to go to the second step, which was the actual integration of my solution in the existing project. I thought that the issue was finished but this is were I started struggling. Indeed, after integrating my solution while respecting the existing structure, format, etc., I found out that I had to fix some other issues resulting from the integration of my code. I had to handle calculations now, since this is the main purpose of the project. This was the hard part because I had to be able to handle sentences such as "five plus nine minus seven to the power of six". And those kind of sentences were not tested in the unitests so it took me time before realizing how far I had to go before making it fully stable and making sure that I could take care of any calculation containing any literal number. 

I'll not explain the code I wrote but I ended up managing this after trying and retrying lots of regex operations techniques. I thought I could finally open the Pull Request but that was still not over. When adding some more unittests, I realized that there was still a point of failure. The handling of the invalid expressions such as "two plus minus" or "five five plus four". After trying to fix it, I thought about the fact that I would need a complete separate issue. After discussing with the repo owner, we indeed concluded ( [in this comment](https://github.com/ErykPiasecki07/VerbCalc/issues/30#issuecomment-981119612) ) that I could open a Pull Request with the solution I created but that it will not be merged since there is still this important point of failure that will be integrated in a new issue ( [Issue #52](https://github.com/ErykPiasecki07/VerbCalc/issues/52) ). 


&nbsp;
# Interaction with the community

The only person I interacted with is the repository owner. It was really pleasant to communicate with him since he's very reactive and very understanding about all the questions I asked him. Those discussions stayed in the comments of the issues so that any contributors can see the historical of the way I managed to solve the issue as well as the different issues I encountered.

My questions mainly concerned some issues I had about the project. I also asked him stuff concerning his feelings about the way I was turning my solution to the issue, the way he was planing to manage some future features of the project (so that I could figure out how to turn my solution the best possible way), about the way I was supposed to integrate my solution (which was the main issue I encountered as said earlier), etc. 

We also discussed about some external libraries called "[word2number](https://pypi.org/project/word2number/)" that could have already fixed the issue I worked on. Unfortunately I found that library after opening my pull request, which was a bit too late but he still asked me to throw an eye on it, test it and come back to him if using it within the project would be something feasible. Which is something I will do for sure. 

I also spent some time writing him in order to keep him informed concerning my progress and how things were evolving. This is something I consider as important to do when you work on such a project where other persons are involved, and I think he appreciated it as well. 

Then I asked him some questions about the project itself, how he started thinking about this project, how it is actually born, etc. I think this is important to know as much possible about a project you put effort in. He then explained me his past in IT and how he ended up launching the project.

&nbsp;
# Conclusion

In conclusion, I would say that my main feeling about Open Source is that I am surprised. Indeed, that's my first experience in the world of Open Source and I am suprised about the fact that it went that well. 

I feel like people contributing for free to some kind of project are necessarily nice since they just do it by pure pleasure. Everyone helps everyone without judgment with the common interest of wanting to improve the same project. 

I'm also suprised to see how fast a project can grow when there are multiple contributors ready to put effort in it. Indeed when I initially asked to be assigned to the issue, there were only 2 issues opened. While writing this conclusion, 10 days later, there are now 8 issues and some other contributors interested in the project and I think this will keep growing.  

I'm glad I was part of such an experience at least once in my IT career because I really felt like being actually useful to a project that will itself be useful in the future. 

Though, as said earlier, I'm kind of frustrated about the fact that I couldn't fully integrate my contribution due to the complications of some extra features of the project. That's why I will for sure keep working on this project (as I said to the project owner) in order to improve it as much as I can with the skills I possess and so having my job completely done. 

To finish, I noticed that my knowledge about git and all its usages are lower than what I thought. Knowing that, I will do my best to fix that in order to be more prepared in the future. 

&nbsp;
# Current State

Waiting for the repo owner to keep me informed about his thoughts concerning the Pull Request review (even if I already know it will not be merged).

Still working on the project since I actually enjoy it. 