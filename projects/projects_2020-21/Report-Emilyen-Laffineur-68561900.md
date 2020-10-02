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

### Fedora

An other solution (less likely) would be to make a contribution to Fedora which is my day to day OS. However, viewing the size of this software
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

Everything that need to be develop is well documented with the things we need to know before starting contribute, the goal of the project, etc.

In order to work on this exercice I just had to write a comment saying that I'm interested in doing that.

Some hours later I had an answer from [mirko](https://github.com/mirkoperillo) saying that they assigned me the issue.
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
In C# it exists the "Case-when" statement ([doc](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/when)). 
However, nothing like that exists in Java, a workaround is possible using an enumeration but it's kinda dirty. 
So, I asked on the issue, what was I supposed to do. I was not sure if the workaround was a good thing or not as it's clearly not obvious for someone who start coding.

### 24/09

The answer I got was to delete that part of the problem.
So I continued writing the code and the tests, made all the check on my machine then I created the [pull request](https://github.com/exercism/v3/pull/2270).
When the pull request is created five tests are run in order to have a basic verification (check that [Prettier](https://prettier.io/) was run, files names, etc.).
If and only if all the five tests are passed a reviewer is asked to check the PR in order to merge it.
