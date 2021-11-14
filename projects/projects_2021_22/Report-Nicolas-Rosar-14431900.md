# Open Source Contribution Project

*Author:* Rosar Nicolas

*NOMA:* 14431900

*Year:* 2021-2022

*Selected project:* [coding-space](https://github.com/rishipurwar1/coding-space)

# Project selection

Since the number of open-source application that i'm using is really low i decided to browse the internet and ended up finding an issue about Coding-Space.
The project in itself seems quite young and thus only beginning but I find the concept interesting. When i need to learn a language or another
technology, I always find myself in difficulty to create exercice to practice by myself and end up in tutorials videos and so on...

I did my bachelor in High School and had some courses about web development. I think i could bring something to this project and would therefore like to contribute to it.

# Contribution
The issue I choose is the following-one [Fix skeleton loading card](https://github.com/rishipurwar1/coding-space/issues/25).
The description of the issue was quite short and mentionned a problem in the size of the skeleton that take place as loading animation before retrieving the date from a Firebase Database.

I started by analysing the code and the behavior of the UI during the loading state to find a way to solve the issue and improve the user experience. After this I proposed an example of design for the skeleton card and asked for an access to the current database of the project to ensure consistency between the two state of the web pages (before loading data and after loading data). I didn't have to wait long to get a positive response.

As I was in regular contact with the owner of the repository through Github (pull request) and Discord (a server for the community of Coding Space) I was able to respond more precisly to his need. My work has been done over two pull request.

First Pull request :<br>
The website is divided in five mains pages in which four of them require loading skeleton for cards that represents challenges, solutions to challenges and ressources. For each of them I add to create new React component and adapt some code that was previously used to match the new design. I also used this as an occasion to correct some inconsistencies in the code. Some parts of the cards were the same but implemented in different way. I also noticed the use of two different modules (grid and flex) for the organization of the cards before and after loading. This topic has been left out for the moment.

This task was longer than difficult and went smoothly. I did strugle a little to make the pull request due to some conflicts but I managed to do it. The pull request has been accepted and merged into the project.

Second Pull request :<br>
Later on I created a second pull request to implement some minor modifications requested by the owner in order to finally have the final result. This pull request was also accepted and merged into the main branche. 

# Conclusion
Working on an open source project was completly new to me. By working on this issue I noticed that it would be a good thing to learn more about the git tool to avoid wasting time in the future. I may not have made huge modifications to the project but I'm still proud of what I did.
