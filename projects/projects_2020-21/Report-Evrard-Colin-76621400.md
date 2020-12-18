# Open Source Project


***Author:*** Evrard Colin  

***NOMA:*** 76621400

***Open Source Project:*** [Evobot](https://github.com/eritislami/evobot)

***Academic year*** 2020-2021

# Project proposal
## Introduction
In the context of this course, our assignment was to make a significant contribution to an open source project. So naturally I went on the hunt for the perfect project.
## The project hunt 
There were a few projects on my list of candidates for my but my main criteria was for it to be software that I use or have used personally. In the end there were 3 projects that seemed interesting.
 1. [Newpipe](https://newpipe.schabi.org/) an open source youtube client for android.
 2. [Libgdx](https://libgdx.badlogicgames.com/) a game library in java that I had used for a game or two.
 3. [Evobot](https://github.com/eritislami/evobot) a music bot for discord that can stream from various sources.

## Work intents
I am confident that I will be able to make a significant contribution to [Evobot](https://github.com/eritislami/evobot). My confidence rests on 2 factors.

1. That project is built upon technologies I have used before (Node.js, REST APIs).
2. The project is relatively young and quite active (e.g. some commits have been made last week).

All that being said, I have two goals for my contributions to this project.
My first one is to fix a [bug](https://github.com/eritislami/evobot/issues/328) which prevents URLs from soundcloud's mobile app to be used. 
The second is to add a commonly requested [feature](https://github.com/eritislami/evobot/issues/358): the ability to specify permissions on a per discord-role basis. 

I contacted the owner of the repository but didn't wait for his answer to start working.
# Final report

## Introduction.
In this first part, I will detail the technologies involved as well as my methods. Then, I will discuss the project's relevant events. Finally, I will conclude with my thoughts on my first approach to open source contributions.
Let's dive in. 
### Technologies 
The project is designed to be used with the discord bot API, the youtube web API and the soundcloud web API. Those are the only non-free pieces of this project. The rest is simply nodejs and [youtube-dl](https://youtube-dl.org/).
### Methodology
My method for working on this project is the following: I analyzed the pull requests made by previous devs, whether they were accepted or not and why. I also built myself an accurate image of the community. I noticed that the repo's community was mostly composed of users with basic knowledge of the programming world and much fewer contributors. The maintainer and creator of the project seemed to be the most active contributor and had a very tidy and regular workflow which made things even easier for new contributors like me to get started. Once I got a grasp of the people I was working with, I was ready to get my hands dirty, so I tried to focus on the most requested features and bugfixes. This part wasn't particularily easy since most of the bug reports were about problems with the youtube-dl dependency and not evobot itself. In the end, I managed to find the two objectives I discussed in the work intents part.
### Project adoption and first PR
With these new objectives now in mind I ran the latest version on my computer and went out my way to test it. I listened to some music with my friends. Some of them then started to play atrocius meme-y music and I naturally commanded the bot to play it louder even though the volume was already at 100%. So I tried the following commands.
~~~ 
/volume 1000 #was refused
/volume 1000.0 #was refused
/volume 10e32 #was accepted
~~~ 
Chaos ensued. The walls started to crumble and the birds flew away while I was lying on the floor trying to hold back in my head the blood that was dripping out of my ears. Fortunately, I had lowered the sound to a near minimum so none of that actually happened. It turned out that the bot was parsing integer numbers for bounds checking while the audio engine accepted any string representing a real number. JavaScript being javaScript, instead of failing to parse "10e32" as an integer, assumed it represented 10 so the bound check passed anyway. Same thing with "0xFFFF" or "0b01100100". I started to work on a fix immediatly because it was a health hasard in some discord server, there can be dozens of people who don't really know each other and someone somewhere might have their volume cranked up to the max.
Once the fix was ready and tested, I made a pull request and then reported the issue, to avoid having an unfixed safety bug known out there for too long. The pull request was accepted a few hours later by the maintainer. I believe that this clean and usefull first pull request helped build the trust that the maintainer now has in me.

### A new feature

Days went by as I watched my github feed come to a stale, but no so long after, a user made a very good suggestion: he wanted to add a default volume to the bot. I thought it was a welcome idea so I started implementing it. This time it was a little thougher, it wasn't simply fixing some bad code in one file, I needed to actually add new code and bend myself to the project's architecture as well as some coding habits that weren't mine.  That pull request was accepted much more quickly than I anticipated. It seems like the time I spent trying to make my code blend in the project ended up saving me from arguing over something as meaningless as tab VS spaces for example.

### Finishing the project

At this point I thought I had been lucky to have such a nice experience with this bot's community, but I had said in the proposal that I would do more than I actually did so I got back to work. I started again with the [fix](https://github.com/eritislami/evobot/issues/328). The problem was that soundcloud's mobile app made shortened links instead of full links. And that was incompatible with the bot. Someone suggested that it might be a regex issue. I had the hunch that it wasn't the case, the mobile links were completely different from the full ones so it must have been a redirection and I was right. The fix was not as simple as I thought but after some time, I found a way to make it. Unfortunately, a few hours before, some other person (who forgot to mention was working on it too) made a pull request to fix the same bug. His code was much cleaner than mine even though he implemented the same workaround but for some reason, the maintainer actually merged mine (after making me push it on a dedicated branch) instead of the other one's. To this day, I still don't understand why.
I have implemented the last [feature](https://github.com/eritislami/evobot/pull/449), but it wasn't reviewed yet except for a user who's asked me to add much more things which are outside the scope of the PR.

### Conclusion and final thoughts.
Choosing to contribute to a very active project ended up helping me a lot. I feared that my code would be under a very strict scrutiny, but actually the people leading the project were very happy that someone was helping. They accepted my code as it was. 
I think that a lot of the people who use the project are newcomers to the programming world, so it was a bit difficult to work with the few details they were giving in their feature proposal or their bug report. However the community was never disrespectful and even kind at times. Someone even made an [issue](https://github.com/eritislami/evobot/issues/448) to thank us for our work. 
To conclude, even though I had heard stories of people being obnoxious about insignificant details in the open source community, it was a very pleasant  experience and I am pretty sure it will drive me to go deeper in the open source world. See you in another pull request :wink:


