# Open Source Contribution Project
*Author :* Piquard Thibaut
*Date :* January 2020 
*NOMA :* 4634-13-00

## Research and Selection of the Project

For my project, I first wondered what Open Source programs I was using regularly. My criteria being that I use it for personal use and not only for my studies/work and of course it's a project that interests me.

Among the candidates, I picked VLC. I took this software because it is a software I have been using for many years now. Big consumer of movies, VLC is a must have as a video playback software. Its many possibilities and customizations interested me and I was curious to know how a small Open Source project could compete if not surpass the players of huge competitors like Microsoft or Apple.

## Functioning of the project

The software and its community has a wiki (https://wiki.videolan.org/Getting_Started_At_Coding/) where new contributors can learn how the code works, see current projects and bugs (https://trac.videolan.org/vlc/) as well as code conventions so that it keeps a certain homogeneity.

In addition, it is possible to subscribe to a mailing list to keep up to date with new developments in the project and possible new contributions.

They have also a forum and an IRC channel to be able to ask questions and communicate with each other. (https://forum.videolan.org/)


## Contributions

For my contribution, I have focused here on the convention codes we mentioned above. Indeed, I have noticed while going through the code that some modules do not fully comply with these conventions. 

So I modified two video filters (adjust and rotate) to better respect the given conventions.

As a complement to this work, I noticed that the documentation inside the project was not up to date (contrary to the one on the wiki). I therefore undertook to update all the documentation concerning the strings in the application. The goal of this documentation is to ensure that all configuration and interface strings will be consistent, well-written and well-translated, providing a better user experience.

Since the VLC community ignore all pull requests on Github (https://wiki.videolan.org/Sending_Patches_VLC/), i didn't make one.
So you can see my latest commit here : https://github.com/ThibautPi/vlc/commit/1305fb76f83a9146b9942a33b29f17d3693a0bce
