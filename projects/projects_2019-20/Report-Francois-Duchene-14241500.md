# Open Source Contribution report - LINGI2401

Author : François Duchêne

Date : January 2020

NOMA : 14241500

## Project Presentation

My project was the [CyberChef](https://github.com/gchq/CyberChef) project. It is a webapp carrying various cyber tools, mostly about security, among many other ones. I describe it as a "Swiss-knife" for anyone needing a common place to gather these tools together.
It is coded with NodeJS using TypeScript and other web ressources. The project is maintened by a gouvernemental organization, a cybersecurity team of the Secret Services of UK (no joke).

In the webapp, there are fourth main parts : there are "recipes" that contains actions, there's the "baking" part where we place every recipes, an input part where we can insert our data and a output part. We can place as many recipes as we want, and we can use text, files or images as input.

## My task
I have choosen a ["good first issue"](https://github.com/gchq/CyberChef/issues/875) in the *issues* part of the github repository. The input part of the app can hold multiple tabs as the same time, and the user can switch between tabs. When a long text was inserted, a scroll bar makes possible to go thought the whole area. But when an user switch between tabs with long texts, the scroll bar is always coming back top, instead of remembering the position where the user was. My task was to add this feature.

Unfortunately, i didn't suceeded on doing a correct PR, my attempts of correcting the problem went nowhere. I did succeded to get some results, i don't think i need much more to make it works, but the project itself make it hard for someone new to modify the webapp. I have to admit that despite that the project was quite appealing to me, as i love that subject and that i already knew nodejs for having worked with it on several projects before, it was a bad idea from my part. In the absence of a PR, there is my [fork](https://github.com/FrancoisDuchene/CyberChef).

### Encountered difficulties
I started to have some problem to build the project. It is an old project that use an old version of nodejs, while i have a newer version installed for my own use. So to not downgrade my version, i used an [open-source script](https://github.com/nvm-sh/nvm) which emulate old nodejs versions on the fly. After used this tools, i still had some problems, which took me some time to solve.

I also had some problems to understand the structure of the project itself. There's a huge amount of files in a lot of different places, i needed first to understand where do i needed to make the changes. There's a huge documentation, but only to add operations or new themes, not to actually change the website. In estimation, i'd say the documentation cover ~30% of the total project. The website itself is structured in a weird way, i would call it spaghtetti code. The input is managed by two huges files with functions calling back and forth between those two files, with similar function names and with useless functions. This is a mess to work with. 
For instance about my task, i needed to change the datastructure stored during a session to remember the scrollbar position. The flow of events is chaotic, you have to go to the end of the file to the start, then switch file and go at the end, then again back to the first file at the start.

I tried to contact the developers twice, one by commenting on a existing issue and a second time by directly mailing one of the main mainteners, to which i didn't received any answer so far. The community doesnt seem very active, perhaps it's because they are only starting and the community is small, but there's not much interaction. As it's a gouvernemental project, i suspect that the main developers talk to each other in a closed chat. It's hard to get their attention.

## Conclusion
As i already said, i have chosen this project a bit to fast, and worked on it late in the quadrimester else i would have certainly changed of project due to it's non-apparent difficulties. Despite this fact, i learnt a few things about managing a project, and about what not do. For example, the project seems very structured, with visible guidelines about coding, writing comments or issues/PR. The issues themsleves are organized per thematic and are made noob-friendly (hence how i found the project). There's a big lack of communicating, i have seen PR dating from 2018 yet not merged or even commented. The documentation is lacking, but for the existing part, it is very well written. To bad they didn't extended it for the other parts of the project. 

I will take care of these lessons about managing a project in the future, as i am myself managing an Open-source project with a few other students from UCL. This experience was for me kind of a failure since i didn't succeeded in the given task, but in another way it was a chance for me to see how it works in a real project, in order to take the good parts and not repeat the same mistakes. 
