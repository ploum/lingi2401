Open Source Contribution Project

*Author:* Alberto Samele

*NOMA:* 16952100

*Year:* 2021

*Selected project:* [SwiftMessages](https://github.com/SwiftKickMobile/SwiftMessages)

# Chapter 1 - Scavenger hunting

Everything must start from something, and so does my journey in the Open Source world.
It all began with my search for an exciting project to work on. I knew that I wanted to dwell deep into something iOS related, being an iOS Software Engineer myself, but the main question still laid unanswered: *what should I contribute to?*

*What should I contribute to*... such a broad question. By typing "Swift" in the GitHub search bar, over 200000 repositories are found. That's right, those are 5 zeros right there.
Well, let's start off by saying what I *don't* want to contribute to (or at least, not right now):

- Official Apple maintained projects like the Swift language. Although it would undoubtedly be impressive to work on them, it looks like the vast majority of the projects have been written using C++, or heavily rely on C++ code, which I'm not too familiar with. Chances of me slipping into those chunks of code seem pretty high... *Skip*
- Networking/Parsing libraries. Are they useful? Yes. Are they used daily by tons of companies for different scale projects? Sure. Is my definition of "fun Friday night" trying to figure out why some rarely reproducible downcast fails 10% of the times? Not in my books. *Skip*
- Some rad-looking UI component with thousands of stars that almost any iOS Software Engineer has heard of? *DING DING DING* that's where the sugar's at.

After looking at a bunch of libraries, I finally had my candidate: [SwiftMessages](https://github.com/SwiftKickMobile/SwiftMessages) . With over 6500 stars and 640 forks, the relevancy of this library was undisputed. On top of it all, I also had the chance to work with it in one of my past jobs, so my familiarity with the project would for sure give me an edge.

In particular, I decided to take care of [this](https://github.com/SwiftKickMobile/SwiftMessages/issues/207) "issue", which is technically a feature request. It seems manageable enough to get my feet wet in the Open Source world, but it's also something handy that I could picture people using in their day-to-day coding lives.


# Chapter 2 - Getting started

With over 20000 lines of code, getting started was definitely not an easy task. Luckily, [SwiftKickMobile](https://github.com/SwiftKickMobile), the creator of SwiftMessages, included a Demo project to showcase all the project's functionalities.
Demo.xcodeprojc>Double-click>Run-on-Simulator and... perfect! We're already up and running!

![Alt Text](https://i.makeagif.com/media/10-03-2021/PecyWo.gif)

Now, let's fresh up our memory on *what* exactly I'm supposed to be doing

> Maybe it would be a good idea to add some optional haptic feedback to certain alerts. [...] There's three levels of feedback for notifications: success, warning and error. At the moment it can be added using event listeners, but adding default support for it on specific configurations would be helpful

Although pretty clear, let's try to extrapolate some additional informations from this generic request:

- *What should I be doing?* 
Adding haptic feedback to alerts. The ticket specifically says *some* alerts, and by that they mean the pre-configured / pre-themed success, warning and error alerts (in the gif, the green, yellow and red pop-ups). The ticket goes on about mentioning *"Three levels of feedback for notifications"*. The "three levels" and "notifications" keywords  narrow down the object that needs to be used for this task to one and one choice only: ```UINotificationFeedbackGenerator```.

- *When should I be doing it?*
As per [Apple's Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/ios/user-interaction/feedback/), haptic feedback notifications are linked to specific events: success, warning or error. Given that the ticket specifically mentions *default* support for the corresponding pre-themed views, it is fair to assume that each haptic feedback notification should be triggered as soon as the pop-up is displayed. By proceeding this way, a reasonable library's use-case for the out-of-the-box popups would be: User receives some sort of error/warning/success message, a popup appears to notify the user and the phone vibrates alongside the popup presentation.
- *Where should I be doing it?*
Where in the codebase should I exactly be acting? Which files should I edit or add? Now, that's a good question...

# Chapter 3 - Sailor's job

In the darkest nights and with the highest tides, facing waves thousand of lines of code tall, it is a good programmer's job to never lose his route and know how to navigate the project's structure.
I've clearly defined *what* I need to do and *when* I need to do it (see Chapter 2), so I'm not intimidated.
Here below, some excerpts from the [Captain](https://github.com/AlbertoSamele)'s logbook detailing his adventure.

![Alt Text](https://c.tenor.com/gBm8n_pn5fQAAAAC/are-you-ready-kids-captain.gif)
1. Identified from the demo project how the default popups (error, warning, success) are instantiated and styled.
2. Pinpointed the three files in which I would act: 
-*`MessageView`*, to add default haptic feedback values which changes based on the used preset; 
-*`Presenter`*, to allow default behaviour overrides, to give the possibility of quickly adding haptic feedback to custom views and to actually trigger the haptic feedback based on the popup lifecycle (willAppear, didAppear, etc.);
-*`SwiftMessages`*, as a link between the independent MessageView and Config files.

3. Added possible haptic feedback options through an enum, with a self-contained *trigger* function
4. Identified the methods used to present the various popups in *`SwiftMessages`*, linking the `SwiftMessages.Config` struct with the `UIView` object passed along as parameters.
5. Identified the exact instant in which the popups `.willDisplay` thanks to pre-existing observers in *`Presenter`* , then triggering haptic feedback.

[Captain](https://github.com/AlbertoSamele)'s notes:

> Success!! After a long journey, I finally made it... the feature is now working! Ahhh, the sweet vibration that pervades my phone on each popup will bring me joy till my very end, remembrance of a long lived adventure.
> To this day, one thing only still troubles my mind... *`MessageView`* and *`Presenter`* were initially so *beautifully* independent, so much so that adding a *`Presenter`* -specific behaviour to a property related to a *`MessageView`* instance seemed impossible. Luckily, the *`SwiftMessages`* class was there to bridge the two and with some trickery I was able to propagate *`MessageView`* notification type onto *`Presenter`* while still maintaining a very good amount of reusability, independence and as little cross-dependency as possible. Could I have done better? Time will only tell..

# Chapter 4 - The end?

Repo? Forked. Changes? Committed. Pull request? [Created.](https://github.com/SwiftKickMobile/SwiftMessages/pull/484)
Merge? *...not yet*
