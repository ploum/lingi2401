# Open Source Contribution Project
*Author :* Arthur van Stratum
*Date :* January 2020
*NOMA :* 37511500

## Research and selection of the project

Starting the hunt for my project, I decided to look at the tools I was using, and wether I could improve them,  because I was thinking that working on them would be more engaging than choosing some random projects.  This proved to be true, altough with some unexpected delays.

I first settled upon correcting the implementation of the OAUTHBEARER authentication for msmtp, a smtp client.  It however turned out that I misunderstood the documentation and that the specification was correctly implemented.

My second choice fell on the spksrc project.  It is a cross-compilation and packaging framework that allows to package projects for Synology NASes, who lacks a build-in compiler.  This interessed me, because I had long wanted to run imapfilter, a mail filtering utility, on my NAS but couldn't do it due to the absence of a compiler.

I had already looked a this project in the past, but never gotted around to actually use it, due to the arcane nature of cross-compiling.


## Contribution

The next installment of my contributing journey began by checking the past pull requests of the repository to check whether someone had already tried to achieve my goal.  It turned out to be the case, but because the state of the repository changed significantly after these attempts (mainly packaged dependecies), I decided to start my pull request from a clean sheet.

I then delved deeper in the project and started to read the documentation, wich could be best described as wide, but shallow.  Following the instructions, I installed the developping environment (a docker), and started compiling.

The packaging of a program is divided in two steps: cross-compilation and packaging.

The cross compilation step necessitated some error-code digging through the project's pull request and issue list, to finally lead to a simple Makefile patch.  I still had issue compiling for some specific architectures, but those issue where later solved with the help from the volunteers.

The packaging leaded too to a lot of search, because the framework wasn't able to find the compiled files due to the peculiar organisation of the imapfilter repository, but finally, as it is always the case with these kind of problems, a simple variable solved the problem.  I however still had issue with symlinking during the installation of the packet.

At this point, I decided to open the pull request, to get approval from the project maintainers and some help for the remaining issues.  One maintainer responded very quickly to my questions, and requested some others changes, the bigger one being to add the program to one metapacket of network-related cli tools.

I implemented the changes (after an exam-induced delay), but while expanding the metapackage, I noticed that the changelog and version number of the packaged didn't seem consistent with the history of the package, so I asked some clarifications.

I am now waiting for the final approval and the merge of the pull request.


## Links
[spksrc github repository](https://github.com/SynoCommunity/spksrc)
[imapfilter github repository](https://github.com/SynoCommunity/spksrc/pull/3836)
[My pull request](https://github.com/SynoCommunity/spksrc/pull/3836)
