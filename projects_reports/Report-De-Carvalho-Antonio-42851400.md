# Open Source Contribution Project
Author : Marcio Antonio De Carvalho Borges

Date : December 2019  
NOMA : 4285-14-00

## Research and Selection of the Project
My research started by looking for issues with the "good first issue" label  from open source projects on websites such as https://up-for-grabs.net/#/ , https://codetribute.mozilla.org/ and https://firstcontributions.github.io/. Unfortunately I didn't find any small to medium sized project that interested me while having an active community. A lot of the propositions on the third link was about projects that I considered to be too big for me in order to make my first open source contribution. 

After this first unsuccessful research I thought about looking for open source alternatives to the apps I use. It has leaded me first to ihatemoney project  (which is an open source alternative to Tricount to manage debt between friends). But the feature that I wanted to add after using it, to be able to split the bill by percentage, was already the subject of one of the closed issue where they explained that they didn't need it. (link to the issue : https://github.com/spiral-project/ihatemoney/issues/471). 

The second open source alternative app that I was interested in is NewPipe, a Youtube streaming front-end for Android. (link to the project repository : https://github.com/TeamNewPipe/NewPipe) I already used this app for some of its interesting features but not daily. There is currently an active community on this project and I was used to the technical requirements (Android app developement). I wanted to resolve one of the existing good-first issue and maybe working on a feature later (being able to select and download multiple videos at once, currently we have to select and download one at the time).
## Contributions
The issue that I chosed was proposed by a user, it detailed a confusing behavior about the playlist thumbnail (link to the issue : https://github.com/TeamNewPipe/NewPipe/issues/2759). When the video corresponding to the playlist thumbnail was removed, the playlist thumbnail wasn't updated even if the playlist has become empty or if we added new videos to the playlist. 

Since it wasn't me that opened this issue, I asked if I could work on this issue. The project owner told me that I could and should look to other issues to familiarize with the code. 

Which I did since there wasn't much documentation in the repository nor in the code. This step took me the most time in this project because I never worked in a code that I hadn't wrote myself. The other issues with their corresponding pull requests and the Android Studio debug mode helped me to understand more about the structure of the code. 

Once I reached a point where the problems pointed in the issue was resolved, I decided to propose it through a pull-request. (link to the pull-request : https://github.com/TeamNewPipe/NewPipe/pull/2837) Before making a pull-request, I had to conform myself with the contributions guidelines. 

Changes has been requested for this pull-request because of the usage of an remote Youtube image for the empty playlist and this one wasn't free of use. So I correct this mistake by replacing it with an local drawable as suggested by the community and did again a pull-request. 

Now, I'm waiting for a re-review of this updated pull request by the community.
(This report will be updated when a re-review will be operated on the pull-request)
