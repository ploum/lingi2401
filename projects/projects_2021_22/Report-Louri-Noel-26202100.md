# Open Source Contribution Project

*Author:* Louri NOËL

*NOMA:* 26202100

*Year:* 2021-2022

*Selected project:* [Supertux](https://github.com/SuperTux/supertux)

*License:* GPL 3.0

## The Project

**Supertux** is a platformer game which draws its inspiration from the Mario games.
It features Tux (the mascot of Linux) instead of the red mustachioed, going through icy lands to save his girlfriend Penny from the claws of Nolok.

## Motivations

I played SuperTux when I was little, and I have waited for an update since then.
I have missed the 0.6.2 version which was released in May 2020 and there is apparently a lot more to come, so I think choosing this project could be a good idea for a starting point.

## Learning about the community

*16/09/2021 - 26/09/2021*

I thought at first the community was almost dead, because of the low number of commits these past months, the low activity on the forum, and the few recent issues and pull requests. So I decided to observe during a week to see if I could really choose this project.
The [twitter account](https://twitter.com/supertux_team?lang=fr) only retweet fanarts of the game (2 times this summer).
The active part of the [forum](https://forum.freegamedev.net/viewforum.php?f=66) is mostly about creating maps, nothing related to development.
The community is also on LiberaChat and Discord, but I don't dare to go on those for the time being.

## Building the project

*22/09/2021*

I tried building the project on Windows at first, but I must link the dependencies manually with my current environnement, and there are many of them.
I did not manage to build it, so instead I tried building it on a Ubuntu virtual machine, and it worked well!
But the game was lagging, so I built it again in my dual-boot Ubuntu instead.

## Looking for something to do

*27/09/2021 - 01/10/2021*

I didn't find any appealing Issue which would seem simple enough to start, so I played through the game looking for bugs.
I have found some, and one of them was promising (ie. I could take it on with little effort).

When Tux dies, the level's music fades out. Then Tux reappears at the beginning of the level or at a checkpoint, and the music fades in from where it stopped.
But sometimes (seemingly randomly), the music does not play after reappearing: the other sounds are still there, but there is no music. The music starts again when resuming the game from the pause menu, or when changing its volume in the options.

## Investigating the bug

*02/10/2021 - 03/10/2021*

I have noticed that the bug happens more frequently on the virtual machine than on the dual-boot Ubuntu. In fact, I have built the project on my dual-boot because the game was lagging too much in the virtual machine. This made me suspect a race condition issue.

I first looked into the src/audio folder, where the bug likely was. I spent a few hours adding log messages to understand the flow of the program, and I finally found the issue.

When Tux dies, the Player class [calls](# "src/object/player.cpp (line 1949)") SoundManager::[pause_music](# "src/audio/sound_manager.cpp (line 343)") with the argument *fadetime=3.0* . This then [calls](# "src/audio/sound_manager.cpp (line 351)") StreamSoundSource::[set_fading](# "src/audio/stream_sound_source.cpp (line 127)") with the same argument, which changes its state to *FadingPause*.
Then in StreamSoundSource::[update](# "src/audio/stream_sound_source.cpp (line 75)"), because the state is now *FadingPause*, it decreases the gain of the music by [calling](# "src/audio/stream_sound_source.cpp (line 121)") StreamSoundSource::set_gain while the time counter does not reach the fade time.

In most cases, Tux reappears soon enough and GameSession [calls](# "src/supertux/game_session.cpp (line 158)") MusicObject::resume_music, which [calls](# "src/object/music_object.cpp (line 77)") SoundManager::[resume_music](# "src/audio/sound_manager.cpp (line 395)") with the argument *fadetime=3.2*.
It then [calls](# "src/audio/sound_manager.cpp (line 403)") StreamSoundSource::[set_fading](# "src/audio/stream_sound_source.cpp (line 127)") with the same argument, which changes its state to *FadingResume*. Then in StreamSoundSource::update the gain increases and the music plays.

But in some cases (**that is the bug**), Tux reappears after the fade-out effect has completed, and the music is [paused](# "src/audio/stream_sound_source.cpp (line 118)") instead of decreasing its gain. When Tux reappears, the gain is increased but we cannot hear the music because *it is not playing*: it is still paused.

## Fixing the bug

*04/10/2021*

To fix the bug, when the music must fade in, I call StreamSoundSource::[resume](# "src/audio/openal_sound_source.cpp (line 104)") on top of calling StreamSoundSource::set_fading in SoundManager::resume_music (which is called by GameSession).
This additional call will play the music if it is paused, and otherwise do nothing (ie. return immediately if the music is not paused).

... I just added one line.

## Interacting with the community

*05/10/2021 late at night*

Before doing a Pull Request, I wondered if I should do an Issue describing the bug. I decided to ask the community about it, as it will give me the occasion to interact with others.

I went to the community's LiberaChat using KiwiIRC IRC Client, there is about 10 people connected. I asked:
> *(21h45)* Hello, I'm new here! I have found a minor bug and I would like to do a pull request to fix it. Should I do an Issue first to explain the bug, or can I just explain it briefly in the PR?

To which Semphris replied: (he is one of the four members of the official SuperTux Team)
> *(21h46)* Normally I'd be among those who promote doing an issue first

> But honestly, the management is all over the place

> so if you don't want to bother opening an issue, it's fine

> As long as you explain what the issue is/was in the PR description, enough so that we can notice it, and discuss the upsides/downsides of many remedies

(He was the only one to say anything, even unrelated, in the following 2 hours)

Thinking about the objective of this course, I opted to also do an Issue, in order to have more interactions with the community. So I replied:
> *(21h49)* Ok thanks, I think I will do the Issue first.

And so, I made an [Issue (#1833)](https://github.com/SuperTux/supertux/issues/1833) following the guidelines of the *CONTRIBUTING.md* file. I then commited to my fork (by again following the guidelines) and did a [Pull Request (#1834)](https://github.com/SuperTux/supertux/pull/1834)

Later that night, at 23h38, Semphriss approved my PR, commenting:
> I remember running across that bug a few times. Props for finding how to fix it, and big thanks for the PR!

At 00h18, Tobbi said on LiberaChat: (he also is one of the four members of the SuperTux Team)
> Interesting. I thought the issue has long been fixed

To which I replied:
> *(00h58)* Well, I only noticed it because it happened most of the time on my virtual machine:

> The game was lagging so much that Tux took way longer than 3 seconds to die. The music had all the time to be paused (see the Issue for details)

(1h23) I decided to go to the community's Discord server. **What a surprise!** The Discord server is lively! I should have joined sooner, that's where everybody is hiding!

## Actual status

Waiting from others' approval, and hopefully a merge soon.
