# Open Source Contribution Project
*Author :* Nicolas Verbois 

*Date :* September 2021

*NOMA :* 13661600

*Selected project:* [Voyager website](https://github.com/pulkithanda/voyager-hf)

## Research and Selection of the Project

As I had never tried to collaborate on an Open Source project, this course marked my first contact with the Open Source world. Not really knowing in which direction to start my research of a topic to work on, I started by reading the guide provided on GitHub for newcomers, entitled ["How to Contribute to Open Source"](https://opensource.guide/how-to-contribute/). It seemed like a great point to start the adventure.

After thoroughly reading this article, many helpful resources are showcased towards the end such as [GitHub Explore](https://github.com/explore/), [First Contributions](https://firstcontributions.github.io/) and [First Timers Only](https://www.firsttimersonly.com/). The last one, "First Timers Only", was of particular help in my search, allowing me to explore other resources such as [First Contribution](https://github.com/firstcontributions/first-contributions), [Good First issues (.com)](https://goodfirstissues.com/) and [Good First Issue (.dev)](https://goodfirstissue.dev/). 

The first one, First Contribution, is a GitHub repository focused on simplifying and guiding the way beginners make their first contribution on the platform. It allowed me to discover the whole process of the standard "fork -> clone -> edit -> pull request" workflow for the first time.
The two others, on the other hand, have been of real help in discovering several Open Source projects of interest, which I will describe below. Through those resources, I've discovered several repositories such as [Lofi](https://github.com/dvx/lofi), [Harvest](https://github.com/tfukaza/harvest) or [Five Fifths Voter](https://github.com/Call-for-Code-for-Racial-Justice/Five-Fifths-Voter).

Although those projects were really interesting in my opinion, as "Lofi" was very relevant to me since I use Spotify daily and as "Five Fifths Voter" seemed like a great project to empower equality, they seemed in my opinion a bit too challenging for me, considering it was my first time contributing and that I needed to do a "small" contribution. Thus, I kept browsing the resources cited above, providing me with different examples of "beginner-friendly" projects, and that's how I finally encountered the project named [Voyager](https://github.com/pulkithanda/voyager-hf).

As described in the repository, Voyager is a space website that can be used as a template in the future for space-related topics. Once again, it is a topic that is of interest to me, as I am myself quite fond of space observation and space-related content like videos. Plus, developing a website is always something that appeals to me since we did not really do web development through my engineering degree. Finally, the different issues available seemed reasonable to solve given my current skills. That's why I decided to go for that Open Source project.


## Interaction and communication with the community

When contributing to Open Source projects, the interactions with the community constitute a central part of the process. Luckily for me, the owner of the project was "quite obviously" reachable through the GitHub comment section, directly under the issue that a person would be assigned to. But the owner also happened to have a Discord server, which you could join in order to speak more easily about specific points or problems that an assignee might encounter while working on one of the issues. 

In my case, I mainly used the GitHub comments section to communicate at first, but then I also used a bit the Discord server that was available to ask more details to the owner about specific points I was working on, in order to not "pollute" the GitHub comment sections with plenty of messages. 

Since this project was participating in Hacktoberfest 2021, which is a month-long celebration of open source software where open source maintainers give new contributors extra attention as they guide developers through their first pull requests on the platform, I must say that I received a lot of help and guidance from the maintainer. 
Plus, since a considerable amount of other people, including students like me, were also contributing to this project, it made it buzzing with life.


## Contribution

For my contribution, I decided to tackle the issue named ["Adding a Video Gallery section for pictures"](https://github.com/pulkithanda/voyager-hf/issues/6) on the Voyager project repository. As the name of the issue is quite straightforward, the owner of the repository wanted a video gallery to be added below the "About me" page (as a separate "div"). But before starting to work on the issue, I first needed to exchange with the owner to grasp exactly his need, as I found it strange to add a **video** gallery that would contain **pictures** and not videos, as the title is indicating. After discussing, I was now assured that he wanted a gallery containing video thumbnails that could act as a link towards a video player. 

Using some references that he provided me with, I started integrating code into the forked project to build an "Image slider" with a scroll effect for the video gallery. I found it to be a great choice of design, matching the overall "space" theme of the website. The architecture of the website, developed in Flask, wasn't too difficult to take in hand. Flask is a micro web framework written in Python, thus the project consisted of CSS, JavaScript, HTML and Python files. To integrate my video gallery, I simply needed to write some CSS, JavaScript and HTML code. 

At first, I had some difficulties with the [gsap](https://greensock.com/gsap/) library, making me unable to integrate the code properly. Then, I encountered a bit of trouble with some CSS parameters that were conflicting with existing CSS values for the web page. Also, the JavaScript code snippet I was using needed to be adjusted to properly fit the needs of the functionality. Finally, I integrated "iframes" to place Youtube thumbnails in the video gallery, making it fully functional.

The owner of the project seemed pleased with my work and just asked me to fix a few remaining small things. After that, I sent my pull request and the owner accepted it, merging my code into the project. In the end, it was very interesting to contribute for the first time to such an open-source project and I hope it will help people using the Voyager website template in the future.

## What I have learned

In the end, this project has been a great opportunity for me to further improve my knowledge and skills in software development and web design, as it is something that has always piqued my curiosity and as it is not something that is taught at our university. Thus, I can fairly say that I have now a better grasp of :

* Flask "microframework", which can serve as an entry to more complex full-stack frameworks, such as Ruby on Rails or VueJS.

* How to reach project owners and communicate with them to better understand what they exactly want.

* Javascript code, especially to achieve certain functionalities, as in my case, making video thumbnails rotate.
