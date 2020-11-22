# Open Source Contribution Project
*Author :* Matthieu Meert

*Date :* November 2020

*NOMA :* 50171500

*Project :* [OpenShot Video Editor](https://github.com/OpenShot/openshot-qt)

## Finding a project to contribute to

So, we are in November and I haven't really looked for a project to contribute to yet. *Maybe I should have started earlier*. Let's go, easy peasy, I just need to find a project to contribute to, make something that is not too difficult or too long and it's in the pocket. I first think about contributing to software that I regularly use, which is more exciting, more rewarding and saves time as I already know the functionalities. My first thought is [Inkscape](https://inkscape.org/), a vectorial image editing software that I personnaly find amazing (go check it out, especially [this guy]( https://www.youtube.com/channel/UCEQXp_fcqwPcqrzNtWJ1w9w) if interested or if you hesitate to buy Adobe Illustrator)! So I go on their website (they don't seem active on github which is weird as the software is regularly updated), trying to find out how I can contribute. I am quickly redirected to other pages of the site and, a few clicks later (and a few new tabs opened), I finally discover that it is maintained on gitlab and that the base code is mainly written in C++ (which I'm not particularly comfortable with). Good news though, it is possible to write extensions using any language. Digging this possibility redirects me to some other pages. Finally, having about 8 tabs opened just to have a quick look on how to contribute, not any idea of an extension to make, the feeling that contributing to the main codebase will be too hard for me, it seems quite complicated and I am a bit discouraged about contributing to Inkscape. No problem, there are many fishes in the ocean, right?

Let's try to find something more suited for a first contribution. What could be best than the [github page](https://firstcontributions.github.io/#project-list) dedicated to firt contributions? So I am looking through the porposed projects, but every project either seems complicated or not really exciting for me to work on. *I should have started earlier*.

Back to square one. Which open-source softwares do I use, that could be good to make a first contribution? What about a game? A game is exciting, a game is fun, let's try to find a game. I remeber the old days, playing with my brother all the night on his computer, and this game "TuxKart", which is an open-source mariokart-like game using Tux (linux mascot) and other open-source mascots as main characters. I find out the original game is not maintained anymore but a fork named [SuperTuxKart](https://supertuxkart.net/Main_Page) is still active. So I install it, play a few hours, discover the new super cool "soccer" game mode, and then try to find out what I could do. It seems complicated as I am completely new to game development. Maybe I could create a new map or a new kart, but this would be really time-consuming. Looking at the issues on github is not encouraging as I have no idea what they are talking about, and it seems like it would take me days to do a 10 minutes job for someone who already knows the code. Maybe not worth it for a small contribution. Let's find another idea. *I should definitively have started earlier*.

Okay, keep calm, there must be something well suited for my first contribution. Why not combining this work and my master thesis? Indeed, I will implement a chatbot using an open-source framework, [Rasa](https://rasa.com/). This one is intersting, and surely well maintained, as I know that is has raised some money recently (13M in 2019 and 26M in 2020, as we can read in [source](https://voicebot.ai/2020/06/23/open-source-conversational-ai-startup-rasa-raises-26m-in-funding-round-led-by-andreessen-horowitz/)). I however decide not to contribute to this one for two main reasons: 
* It probably has very few easy to fix bugs, as many developers are hired to work on this
* I don't know much about language processing (yet), so it would take a lot of time for me just to understand the purpose of the library. *Not a single doubt about it, I should have started earlier*.

Despite the fact that I have not chosen this project to contribute to, I think it's an interesting example of how an open source project can evolve (in this case in an actual company), and even end up employing many full time developers, and still providing open source software. For more information about their business model, see this [page](https://rasa.com/how-we-make-money/) (which I advise you to read, truly interesting and perfect example of what we have seen in class).

Finally (yes, there is an end to this section), I think about this program I installed very recently to make a silly video montage for my "rallye chambre" activity. I opted for an open-source quick and easy to use program, [OpenShot Video Editor](https://www.openshot.org/). I remember being annoyed by the fact that SHIFT+scroll to scroll horizontally (which is particulatly useful in this kind of situation with a long horizontal timeline you have to scroll through all the time) was not implemented. This feature is widely used in other programs and is, in my opinion, a must have in that kind of program. This is perfect!

## Contact with the community

Next step is to follow the [instructions](https://github.com/OpenShot/openshot-qt/wiki/Become-a-Developer) to setup the project locally. This page is really clear and staightforward. As they ask for at the end of the instructions, I send an email to introduce myself. I am quickly added to the developer's chatroom in [Zulip](https://zulip.com/), an open-source alternative to Slack. The guy guides me with great care and support, and insists that I should create a PR as soon as I have questions or when I am stuck, even if it doesn't work yet. And so I start looking at the code to add this new feature.

## Getting into the code

It is not easy to get into the code of some huge progam that was written by others. My first idea is to look for a file that would give some explaination about the general structure of the code and the purppose of each part of it, which I don't find. Fortunately, some logs are appearing while doing things on the program, which quickly guides me to the part of the program I will have to change. CTRL+scroll was already implemented for zooming in/out, which is quite helpful to get the program to recognize SHIFT+scroll input! Based on that, I can easily implement the modification. Finally, at least for this enhancement, it is not needed for me to understand the whole program. Based on what is already implemented, it isn't very difficult to add this new feature.

## My contribution

Here is my [PR](https://github.com/OpenShot/openshot-qt/pull/3857). I took care that the correspondance of scrolling down/up resulting in moving right/left was consistent with what I have experienced in other programs. I also took care that the scroll speed is not proportional to time units but to the window, so that it doesn't scroll very fast when zommed in and very slow when zommed out. I am quite satisfied with the results. Even if it is simple, I think it can add a lot to the ease of use of the program. I look forward for the opinions/questions of the community on this!

