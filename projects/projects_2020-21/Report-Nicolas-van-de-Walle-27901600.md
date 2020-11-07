# Open Source Contribution Project

**Author:** Nicolas van de Walle

**Academic year:** 2020-2021

**NOMA**: 2790 1600

**Open-source project:** [Argo Workflows](https://github.com/argoproj/argo)

## What is Argo?

Argo workflows is an open-source workflow engine supported by the [Cloud Native Computing Foundation](https://www.cncf.io/). This tool controls and schedules the execution of workflows using kubernetes.

My interest for this project came from the fact that during a previous internship (summer 2020), I've had to evaluate and use this engine. After interacting with the big (3000+ people) slack community, I decided to start improving the project too. 

## What might be a great contribution?
After working with Argo for over a month, I encountered a bunch of problems with the engine. Some of them were huge and needed a lot of refactoring/rethinking of the project. (*Note: for your information, the issue here was implementing some versioning of the workflows*). I discussed about it with the community which had the same feedback: "Would be great but way too hard". 

Some other issues were easy to solve and this is one of them I decided to work on. The issue here is a UI/UX issue. Argo workflows supports scheduled workflows that run every X time. It is possible to put them on hold (suspend them) in order for them not to get executed until it is reactivated again. The issue here is that seeing if a scheduled workflow is suspended is not user friendly at all. The user needs to open each workflow of the list to see its suspended state (pretty inconvenient... isn't it?)

My contribution will thus allow the user to get a quick overview of which workflows are suspended and which are not.

## The contribution process

* First, I had to create an issue which you can find here https://github.com/argoproj/argo/issues/4264 
* Then, I got started with the development and made a first pull request https://github.com/argoproj/argo/pull/4446 
* That's where the trouble started...

As it is a very big project with around 300 contributors and 3000 community members, everything is well defined and scripted. After submitting my pull request, some tests were run. Some of them failed because I did not sign the CLA or did not sign my commit. Fortunately, those were well documented and fixing that was very easy. 

After some more time, the UI tests failed because "Some changes were made to the files". Pretty unexpected as the goal of a contribution is to contribute and edit files. After asking for help, I discovered the issue was only regarding the format of the code. Using a linter fixed everything and all the tests passed. 

Few hours later, the pull request was reviewed, accepted and merged into the project.

![Happy](https://i.pinimg.com/originals/91/f5/ce/91f5ce6e7be20ac41c088ef8fac9a776.gif)


