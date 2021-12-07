# Open Source Contribution Project

*Author* : Clément NONNET

*Year* : 2021-2022

*Noma* : 21632100

*Selected project* : [Desktop Shop](https://github.com/rbaltrusch/desktop_shop)

*Pull request* : [Pull Request](https://github.com/rbaltrusch/desktop_shop/pull/12)

## First approach

Since I was new to the open source software development I did not really know what to look for. 
I decided to search for something I enjoy : video games. 
It was fairly easy to find on GitHub. 
One caught my attention, it was an open source project aiming at recreating the game RollerCoaster Tycoon 2, which is a game I know and like.

This project is massive, it has around 500 contributors and over 20.000 commits.
In the README, it was indicated that "Chat takes place on Discord" so I joined the Discord server to see what was happening there.
It was even bigger, there are about 4.000 members in the server, and it was really active. 
Without really knowing to whom I could ask my questions, I contacted a member labelled as a Developer and 
I asked him if there were issues with which I could help as a beginner.

He told me to look to the issues on the GitHub. 
Indeed, there are about 1.200 issues listed. Unfortunately none of them was labelled as "easy" or "good first issue". 
The developer told me that easy issues do not stay very long because they are quickly solved.
So the only issues left are long and complex ones. 
I looked closely to some of them by investigating the code, but it honestly seemed out of reach, mainly because the code is written in C++
(and I barely know this language) but also because these issues require a good understanding of the global context to be solved, and 
obviously I do not have this understanding.

I asked the developer is there was any other way I could help with this project, and he told me that I could maybe help to translate the game to my language. 
Unluckily, the work was already done, a complete French translation of the game was already done, so there was nothing I could do.

## Making a Contribution 

Even though, I was glad that I found such a cool project with a very active community, it was still an unsuccessful attempt 
since I did not really help on this project.

So I went back to GitHub, but this time I directly looked for issues, I filtered the result using the "good first issue" label, 
and I found an issue that seemed solvable by a beginner like me.
The project is a shop application working offline on a desktop, it uses Python and SQL which are 2 languages I know very well.
I contacted the project owner, and I asked to solve the issue.
At first glances, the issue seemed trivial : whenever a customer registers or updates his personal information, 
his first name and last name need to be standardized by applying an uppercase to the first letter and a lowercase to all other letters.

It was a fairly quick fix requiring only 6 lines of codes. 
To be convinced that my solution was good, I downloaded the project to see if the problem was solved.
After running the application on my computer, I tried to register as a new customer, and it was fixed, the first name and last name
were standardized and saved in a database as wished by the owner. 
However, when it comes to updating, another problem appeared.
The updated names were correctly saved in the database but the displaying on the User Interface was still using the previous names.

![image](https://user-images.githubusercontent.com/75025185/144954178-28849af2-d7d2-4910-b7ac-61b22523b8cd.png)

I investigated on this bug, and I found the mistake :
The function responsible for displaying the user information is called before the one updating the names of the user, 
so the display remained the same even if the user information in the database had changed.
To solve this problem, I simply applied the standardisation of the names before the displaying and the trick was done.
It was not very hard, but I spent some time finding where the problem was.
Obviously, it is not easy when you are not the one who wrote the code.

I wrote an explanation to the project owner, and I made a pull request.

I am still waiting for an answer, and I hope I will be merged (should be granted as my fix is working just fine).

## Conclusion

It was a lot of fun discovering these two projects, I am still frustrated I could not help on the first one since it was really
what I wanted to do initially. However, it helped me to realise that contributing to this kind of huge projects require 
at least a small experience on working in such an environment and is very time-consuming.
Still, seeing a massive community working on an open source game was really cool.

Regarding the shop application, it was a much more humble project, but it was really satisfying to feel that I am able
to fix some minor issues and be helpful to someone.

I was not aware of this "issues" thing on GitHub and I find this feature of solving other people problems really awesome.
Maybe I will keep looking for some of them in the future.
