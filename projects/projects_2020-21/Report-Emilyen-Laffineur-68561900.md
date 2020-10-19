# Open Source Contribution Project
*Author :* Emilyen Laffineur

*Date :* September-December 2020  
*NOMA :* 6856-19-00

## Research and Selection of the Project
### Exercism

Exercism is a platform where everyone can learn about programming. At the moment, Exercism is developping is version 3 and need a lot of help
in order to make this third version available. A lot of programming langages are available especially Java and Python that are my go to langage
when I have/want to do something. Passionnated by teaching make my first exercice available would be a great first step in this way.
More information: [here](https://github.com/exercism/v3).

![GitHub contributors](https://img.shields.io/github/contributors/exercism/v3?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/exercism/v3?style=for-the-badge)
![GitHub top language](https://img.shields.io/github/languages/top/exercism/v3?style=for-the-badge)

### Fedora

An other solution (less likely) would be to make a contribution to Fedora which is my day to day OS. However, after viewing the size of this software
it may be too large for a first contribution.
More information: [here](https://github.com/topics/fedora-project) and [here](https://github.com/fedora-infra).


## Selection

22/09

After some reflection it seems that Fedora is a too big project to begin with. I decided to go with Exercism.

## Getting into the project

### 22/09

First of all, I look for the way they use to have someone on the project.
Following the readme I choose the language for the one I want to develop something (Java).
Once you have selected a language you access the list of exercices that need to be developped at the moment.
One of the opened Java exercise at that moment is an exercise about case-statement. (You can find it [here](https://github.com/exercism/v3/issues/1963))

Everything that need to be develop is well documented with the things we need to know before starting to contribute, the goal of the exercise, etc.

In order to work on this exercise I just had to write a comment saying that I'm interested in doing that.

Some hours later I had an answer from [mirkoperillo](https://github.com/mirkoperillo) saying that they assigned me the issue.
The same exercice already exists for C#. As Java and C# are very close langage I was just ask to "translate" the C# code into Java.

### 23/09

I first started by setting up my work IDE and create the architecture required by the project.
Here is the required structure : 

```
case-statement
├── build.gradle
├── .docs
│   ├── after.md
│   ├── hints.md
│   ├── instructions.md
│   └── introduction.md
├── .meta
│   ├── config.json
│   ├── design.md
│   └── src
│       └── reference
│           └── java
│               └── PlayAnalyzer.java
└── src
    ├── main
    │   └── java
    │       └── PlayAnalyzer.java
    └── test
        └── java
            └── PlayAnalyzerTest.java
```

The ```.docs``` folder contains all the text explaination, hints and instructions for the exercise.
The ```.meta``` folder contains an exemple of implemantion that solve the problem.
The ```src``` folder contains the base file for the "student" and some Junit test.

After that I started by making all the .md files that are required for the explaination, instructions and hints for the exercise.
I started translating the code in Java and ran into a problem. 
In C# it exists the `Case-when` statement ([doc](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/when)). 
However, nothing like that exists in Java, a workaround is possible using an enumeration but it's kinda dirty. 
So, I asked on the issue, what was I supposed to do. I was not sure if the workaround was a good thing or not as it's clearly not obvious for someone who start coding.

### 24/09

The answer I got was to delete that part of the problem.
So I continued writing the code and the tests, made all the check on my machine then I created the [pull request](https://github.com/exercism/v3/pull/2270).
When the pull request is created five tests are run in order to have a basic verification (check that [Prettier](https://prettier.io/) was run, files names, etc.).
If and only if all the five tests are passed a reviewer is asked to check the PR in order to merge it.

### 25/09

My PR received a review from [ErikSchierboom](https://github.com/ErikSchierboom) who asked me to do some changes in the docs files and java files.
Most of them was coding style issues.

### 5/10

By this date, I had solve all the issues and was waiting for the review. It arrives the 5/10. This review was easy to solve as it was mostly some coding style issue or rephrase some docs.

### 6/10

I solved all the issues and had an approval from [ErikSchierboom](https://github.com/ErikSchierboom).
They are some things that are left to do : add the exercise entry in some file in order to bring life to this exercise.

### 7/10

[mirkoperillo](https://github.com/mirkoperillo) left some comments in the PR regarding `gradle`, telling me that I should solve some issues that `gradle` is returning.

### 13/10

I tried to work on the `gradle` issue which is really weird as the issues are with files generated by `gradle` during the `gradle test` command.
I asked for help in the PR because I have really no clues on how to solve that.
Also, I made a big mistake at this moment. The original project received some update and my forked one needed to be updated. What was the problem?
The last time I worked on my forked I directly worked on the `master` branch... (A really bad idea...). When I tried to update from forked repo it was a real mess with the conflicts... it took me almost two hours to solve all those issues.

### 15/10

With the help of [mirkoperillo](https://github.com/mirkoperillo) we found the error. It was a typo in the name of a class.
By correcting this typo all the `gradle` stuff is now passing! After pushing it to my project and successfully passed the test it was time to be merged...

## Conclusion

This participation has marked my first contribution to an Open Source project. It was a bit scarry at the beginning as the project is huge and getting reworked now (version 3). However the differents contributor I collaborate with, where very helpfull and caring. Thanks to them I could end up the contribution and learned things!
