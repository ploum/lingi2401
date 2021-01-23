# Open Source Contribution Project
*Author :* Sambon Jean-François

*Date :* 2020

*NOMA :* 5817-14-00

*Selected project :* [RUNELITE](https://github.com/runelite)


## Motivation to follow the course

Last summer I did an intership at Odoo and I have been intrested to the open-source world by seeing that being part of huge open-source community is pretty cool ! I wanted to have more informations on how to create an open source project and to see the history of it.

## Project Selection

I could decide to stay in the Odoo world and to base my project on one contribution to it but I decided to discover other horizon. I wanted to find a project that I am currently using so the time I invest in it will be rewarding in the future. My first idea was to contribute to Ivy : it is a microsoft project around formal verification that I use for my thesis. After some time, I realised that there were almost only one person that was maintaining it so I decided to find something else.

I wanted to find a project that I would enjoy contributing so I chose runelite. It is a game client for a game named runescape. 

## Project history

There is an official client maintained by the game developpers but it is quite crappy so a group of player decided to create RuneLite. Most of the players moved on Runelite. It became a security problem for the game developers when some people used the runelite client source code in order to harm the game. Indeed, runelite was deobfuscating some part of the game code and some malicious users used this code to harm the game.

The history gives one example of the importance of security in open source projects The intresting part was when the game developers took the decision to  ban every player that was using it and to do their best to close the runelite project. The open source community that was around the runelite client had enough people to pressure the game developer to change their mind and to collaborate with the runelite project to fix the security issues. 

### Getting in touch with the community

Having a first contact with the community was quite easy : there was a direct link on a Discord server that allowed me to talk with some people from the project and to see if there was a contribution I could do. I could notice that the developers were not the only one to contribute : there were many people that didn't know how to code but helped to select the more important bugs to fix and so on.


### Contribution process 

First, I needed to setup my environment to be able to contribute. The community answered nicely to me when I had some problems. I noticed that part of the documentation was in the discord and it was helpful to be in contact with some contributors to see which ressources I could use.

Then, I needed to find something to do. In this project, the users of the client are raising some issues in the project and developers pick those issues. Unfortunatly I noticed that every time there was an issue that didn't need deep knowledge of the developer were took fast by an army of newcomers to the project like me. So, I decided to raise my own issue, talked with the community to see if it had a sence to implement this and did my contribution directly.

### The contribution

The contribution I did  was to update the client with a new location that was added in the game recently. There was a bot on the discord that anounced my [pull request](https://github.com/runelite/runelite/pull/12865) directly and I could receive direct feedback on it. Then, the maintener reviewed my code and put it into production. I was surprised of the tactlessness of the reviewer (the review was mainly done on discord) that looked so friendly before but he explained me after that he had many reviews to do and that he had to directly go to the point.

### Conclusion 

During my experience, I learned that starting to contribute to an open source project is not that easy. There are two barriers that need to be crossed. The first one is the technical one. You need to understand the technology around the project but not only : you have to learn how the contribution process works, what are the conventions that are used and if your contribution makes sence. This is not always easy at first. The second barrier and perhaps the most difficult one is being able to collaborate with the people that are already in the project. A lot of information is written nowhere and you the only reasonable to understand quickly how things work is to ask this information to the people that are already contributing. Thus, I realised that my social skills were more important than my technical one in order to make a good contribution.

#### Compte rendu certains discussion discord (brut)


... 

Hydrox 10/11/2020

Well, we have an entire issue board to look through
there are a few things tagged as good-for-first-contribution that you should look at, but most of them will probably be taken
also, feel free to chat in #development. See the channel description for how to chat in there

Jefrasa 10/11/2020
Thanks for your help :slight_smile: I didn't see the tag, I will check that out !

...

Jefrasa 30/11/2020

Hello, when I try to build and run the project I have this error :

Type de fichier joint : document
message.txt
3.01 KB
Does someone has an idea on how I can solve this ?
sorry if i'm not in the good channel :p

Hydrox30/11/2020
probably need more maven

...

Jefrasa 01/12/2020

Small question I have : how can you find the quest id of a quest ? I though I found a way but I think I took the wrong value
I didn't find a way using the dev tools

Adam 01/12/2020

the only way i know of is to read the questlist cs2 script
I guess this spec thing is okay though
maybe also could color the infobox text since thats fairly straight forward

...

GitHub
BOT
01/12/2020

Adam-
[runelite:master] 1 new commit
912847c worldmap: add Getting Ahead quest start location - Adam

Discord channel : https://discord.com/invite/mePCs8U


# Plan oral exam (Subject : runescape and runelite)
## Runescape presentation
### History of runescape.
### Link between runescape and open source
## Runescape and runelite community
### Horizontal power vs vertical power
### Push to open source solutions 
## Business model
### Runescape business model and economy
### Emergence of opensource bot
## Runelite.
### History of runelite
### BSD licence
### Decentralization power
### Advantages of runelite as an opensource solution
## Security.
### More trust in runelite because it is open source
### Not absolute security
## Conclusion