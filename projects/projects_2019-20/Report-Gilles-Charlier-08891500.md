# Open Source Contribution Project
*Author :* Gilles Charlier

*Date :* November 2019 

*NOMA :* 0889-15-00

Projet presentation
----------------------

The OpenAge project consists of implementing a game engine dedicated to 2D strategy games such as Age of Empires 1, Age of Empires 2, or even Star Wars: Galactic Battlegrounds.
For the moment, the project is mainly focused on the implementation of the Age of Empires 2 engine. The engine reuses the textures of the base game.
It is therefore necessary to have a copy of the game to be able to run OpenAge. Openage is compiled in Python and C/C++. The engine runs mainly in Python, and is sometimes accompanied by Cython modules (Python compiled with C/C++). Cython allows you to execute code up to 10x faster, according to some online tests.

My contribution
---------------

I contributed to the issue [#985](https://github.com/SFTtech/openage/issues/985) and submitted two drafts on [#1204](https://github.com/SFTtech/openage/pull/1204#issue-350499940). As I said above, the project is reusing the base assests of Age of Empires II. It is therefore needed to convert the files contained in this assests if they are not manipulable (in order to add some functions to Open Age that were not present in AoE II, complex terrain relief for example).
My main task is as follows: Optimizing the conversion of game textures of AoE II into a more suitable format. (several versions of the game exist, depending on the DLC and the remastered versions).
Basically, a first script (independent of the project) was produced by one of the main contributors to the project: [heinezen](https://github.com/heinezen), but this script was not integrated into OpenAge, and not optimal at all.

Some details about my contribution
----------------------------------

I followed the instructions of Heinezen, which were not very clear on the issue post itself, but as I asked questions, I gradually understood the optimizations that were necessary. Concretely, what was done in the script provided is that each file was converted by manipulating PIL Images which is not optimal at all. They therefore asked me to directly use the format of the project OpenAge by manipulating RGBA pixel arrays.  
In addition, the author of the issue also asked to translate the code from Python to Cython, to speed up the texture conversion process.

At this time, I've submitted two times a Draft versions, the first one that was not good at all, and the second one that was close to their expectations, but one step of the process was not optimal. The draft requests are not yet fully translated into Cython, but as I understood, that doesn't require a lot of work. I'm still working on it.


The challenges encountered during my contribution
-------------------------------------------------

My first difficulty was not to compile the project, because the documentation is complete and accessible, and the members are ready to help as soon as there is a problem.
I did not encounter any compatibility or compilation problem. The only concern was to get a working version of the game on Linux (via wine).
My first difficulty was mainly to understand the structure of the project, and the interaction between the different parts of the project, especially between Python and C/C++.
Fortunately, I didn't have to get too involved in the main part of the project because my main task was to focus on a script to integrate into a conversion that is not currently running when compiling the game.

Most of my time was spent understanding the files in the **convert** folder. Indeed, the SLP files (basic textures of the game) are relatively complex to use, and are not only represented by simple images. They have complete structures, and are very hard to convert.
Consequently, the API already present in the **convert** folder is relatively complex to understand, since several formats represent the same texture, but each format has its own specificities and its own uses.

The OpenAge's community
-------------------

I have only been in contact with two people, both of whom have been very friendly. These didn't hesitate to help me when I had certain misunderstandings concerning the API of the project. They were very reactive when I had some questions, and when I posted some draft submissions. They reviewed almost each line of my code at each draft.

Conclusion
----------

This project made me want to continue contributing to open source projects, and especially this one. The community is so friendly that I can't leave them with my code without improving it until it reach their standards.

