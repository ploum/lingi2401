# Contribution to an Open source Project : Battle for Wesnoth
*Author :* François Schellekens

*Date :* December 2020

*Noma :* 42571400


## Battle for what ?
[Battle for Wesnoth](https://wesnoth.org/) is a turn by turn strategy war-game in a fantasy world that comes under the GPLv2 License. 
Wesnoth is the name of the main human country where most of the campaigns stories happen.
In short the game's objective is to kill your opponent's king with your units and preventing that the opponent does the same. 
The way units fight each other in the game is dependent on luck but relies even more on careful strategy with a lot of aspects that will change the power 
or the chances of an attack.

The main reason i chose this project is because i played this game since i was young and i have lots of good memories playing it. 
It has entertaining campaigns that i played alone but i also played scenarios with friends and family on the same computer, 
and i even played online sometimes with strangers.

The game has a lot of extensions available made by the community, more campaigns, mods that would change the way the game works or looks, 
more factions, and even a lot of new ways to play the game with maps that will abandon completely the way the game was supposed to be played.

Wich leads to the second reason i chose this project : it relies a lot on community particpation, so they certainly do their best to make it easy to contribute. 

## Getting started

I started by going to the Wesnoth forum and found a "getting started" post in the "coder's corner" section : https://forums.wesnoth.org/viewtopic.php?f=10&t=42911

There i found 3 important informations 
+ a link to easy coding issues 
+ a link to the general Battle for Wesnoth discord
+ a link to the github repository

So next i cloned the repository, i joined the discord, and took a look at the easy issues.

## First try

After deciding what issue i wanted to do, i asked on discord if anyone was on it, and someone responded by "i don't think so". 
So i started looking into it, but it was harder than i expected and i didn't really understood how i was supposed to do it, 
because this was such a huge project i was lost but didnt asked for help.
Then suddenly the github bot on discord announces that there is a pull request that fixes the issue i was working on.

## Second try

Learning from my mistake, i decided i will ask on discord for a issue that would be a good first contribution. 
After some discussion with multiple people, i finally got an issue that i could work with : https://github.com/wesnoth/wesnoth/issues/5314 
The first thing i did was to comment the issue so that it won't be taken from me like last time.

A campaing has several parts called scenarios, in a scenario of a campaign you usually have a turn limit to complete the objective. 
In one of the main campaigns "Northern Rebirth"  in the second scenario when you lose by the "clock" you lose without any explications why. 
The issue asked for some message to display to explain to the player why they lost.

While working on this issue i also discovered that there was the same issue for the first scenario of this campaign. So i fixed it for the first scenario too.
After asking for feedback i made a pull request https://github.com/wesnoth/wesnoth/pull/5357.
There are some automated checks on pull requests, and my first commit didnt pass all the tests, 
but when i asked on discord, i was explained that my indentation wasn't good and what command to run to reindent the code.
I pushed my code again after reindenting and correcting a grammar mistake in the dialogue i wrote, and it passed all checks.

After making the corrections to the text that the responsable of dialogues suggested, my PR was accepted and merged.

## Conclusion

While working on this project i was amazed by the people working on Battle for Wesnoth, they are really active and helped me a lot, to build the project, 
answered my questions in minutes and gave me nice feedback when i asked for also in minutes.
I don't think i will look for more issues to solve on Battle For Wesnoth but i learned some knowledge to create my own Battle for Wesnoth Campaign, 
something i always found interesting to do. So now when i get the time and the inspiration, i think i will start creating my own campaign.



