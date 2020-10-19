# Open Source Contribution Project
*Author :* Romain Hainaut  
*Date :* December 2019  
*NOMA :* 23521500

## Research and Selection of the Project

I didn't know the world of open source so I had no idea what program I could be interested in was an open source one. After a discussion with one of my friend, he told me that [VsCode](https://github.com/microsoft/vscode), a text editor that I use, is open source. So I decided to contribute to it by debugging a small bug. Too much time passed by and I decided to start the project by selecting a bug. I remembered that a few month ago I encountered a bug is the search widget, that when you use the up arrow and have multiple line it didn't go up in the text but show the previous search. So I looked if this issue already exist and found that it already and was recent (30 October). So I decided to work on this [issue](https://github.com/microsoft/vscode/issues/83644)

## Contributions

The first thing I did was to tell the community on github that I will work on it. Then I started working, however I wasn't expecting taking 4 hours to install and run the project. Although it was well documented , the installation take time with my slow internet and the fact that I read in diagonal, thus loosing 1 hour because I didn't see that I needed to restart my computer, make the installation an exhausting experience. 

The next day I want this time to manage to actually do something. But when i open the file system, I have never seen so much file in one project and thus begin the research to find the code link to the bug. After a day and a hafl, I finally found the correct file, I would never have thought that this would take the most time.

Anyways I could finally debug. And after a quick tutorial to TypeScript, I easily manage to find the problem and correct it. However I face a problem, I used a fix value and didn't know if this value was specific to my computer or not. After a day of blocking on it, I ask a question to the comminuty with my problem and explaining everything I was planning to do, in case I didn't manage to have an answer but someone else did so he could fix the bug. The day after I got an illumination and find in the css file that this value was a fix. 

So i commit my change and made a pull [request](https://github.com/microsoft/vscode/pull/86619). After little modification ask by one reviewier, just adding comment, it was successfully merge.


