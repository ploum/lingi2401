# Open Source Contribution Project

***Author :*** Jeremie Bogaert

***NOMA :*** 5287 1500

***Date :*** 2020  

***Open-source project :*** [networkx](https://github.com/networkx/networkx)

## Introduction

For the Lingi2401 course, open source project, we were asked to work on an open source project of our choice. This little report will explain the different steps that were taken in order to do so.

## Selection of the project

The first step was obviously to select the project I wanted to work on. It was asked to be a big enough project so that it has a real community, but also a project that I had interacted with in the past. Because I am not using open source projects in my daily life, I started by looking in the different github project suggested for new contributors. For practical reasons, I also looked at the response time from the community for these projects, in order to not loose too much time waiting for answers without having the possibility to go forward. I chose a python package (that I didn't even knew was open source actually) called networkx. The reason why I chose this project is that first of all I already worked with in the past for diverse courses, but also because it is about my favorite part of mathematics, that is, graph theory. This project selection was done around the middle of October.

## How to start ?

Now that I had chosen the project I wanted to contribute on, i had to know what I could do. Since the code is pretty big, and I haven't seen any bugs while using it, I started by reviewing the issues. A lot of them were about really specific parts, or were just questions by users addressed to the developers. I finally found one about some old functions that had to be depreciated in the "/utils" directory.

## And so start the troubles.

Before reading any further, one has to know that one of my most hated things is to bother peoples and spent their time. So it took me quite a while to go from the selection part to the implementation and actually touch the code. To avoid bother the community with useless questions, and after a lot of thinking, I started to read the code and I traveled to a so called "heaps.py" file. Because I am pretty smart (or at least I thought I was), I saw some classes with "unimplemented exception" so i thought "let's implement it, how bad could it be ?". And i began to code, something like a 100 lines. It took me some time, to do something clean and readable. Moreover, I also changed some other things because they were clearly (at least for me) useless so why would someone wants to keep them ? Proud of what I had done I went to github to submit my pull request but then, I saw they had to run some tests. And a lot of tests were not getting though because of what I had changed... What I feared the most happened, the developers came to me just asking what I was trying to do with my pull request. After a few exchanges, i understood that not only what i was wanting to do was useless, not only i lost time implementing it, not only I bother them doing it, but even worse, I didn't understand what was the code doing ! And all of that could have been avoid if I just asked what was this part of the code supposed to do. They refused my pull request and they redirected me to a "How to contribute" page.

## Starting again, but the right way.

After reading the "How to contribute" web page, and with the will of doing the things in the right way, I started to look in the issues again to find something I could do to help. I found and issue referring to a bug implying a missing else clause and a misplaced try/except so I decided to fix it. After running all the tests (in local this time, because I discovered in the "How to contribute" that it was the proper way to do), I submitted my pull request and hurray, it was accepted ! Here is the link of the [accepted pull request](https://github.com/networkx/networkx/pull/4365).

## Conclusion

By wanting not to bother anyone, I actually lost time for nothing, and ended up bother the developers anyway. If I have to keep something in mind from this (traumatic) experience, I would say that a useless question will always be better for everybody than a useless pull request. Moreover, the community was really kind and helped me a lot to achieve this project so there is no fear to have in bothering the developers. I'm glad that I've done this open source contribution, because I couldn't have learned better how to contribute otherwise and because it satisfies me a lot to think I helped (even if it was a minor bug fix). Maybe I will comeback in the future to contribute again to this very useful package.  
