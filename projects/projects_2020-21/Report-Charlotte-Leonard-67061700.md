# Open Source Contribution Project
*Author :* Charlotte Leonard

*Date :* July 2021

*NOMA :* 67061700

# Project

*Selected project :* [JuliaPolyhedra](https://github.com/JuliaPolyhedra/Polyhedra.jl)
*Issue :* https://github.com/JuliaPolyhedra/Polyhedra.jl/issues/263

# Project Selection

I wanted to contribute to a project that a use a lot. So at first, I choose a library python I use a lot in my studies in applied mathematics : scipy. 
But I was very hard to find an issue that was easy to work on as a first time contributer. So I choose a very easy contribution that was just about some notes in documentation.

I wasn't very proud of my work so I decided to find another project to work on. For some of my classes we had to use the language Julia and more specifically JUmp an optimisation program so I decided to see if I could do something there.
I contacted a major contributer to JuMP that happenned to be a former student a UCLouavin. He suggested me a good first issue.


# Contribution

The contribution was about Polyhedra, it was about adding a function that would more easily creat 1D polyhedra wich are trivial, they are just intervals so they don't need complidated function to be created.
During my contribution I reaslised that some files were unused, they were recently added and were called nowhere. So I did 2 differents pull request, one about the issue and one about the unused files.

The first contribution was just deleting files, after asking the repository commandant in chief first.

For the second contribution I rearranged a little the code to create helper function from the existing functions and then I used those helper to create the function sethrep 

One of my issue was improving the codecov repport and one was bad. After some research I learn that it was a report about the quality of the code. 
Deleting unused file, that were'nt covered by the codecov, was good for the code because it increased the pourcentage of the code covered, as the code wasn't used nor tested. The first request was quickly approved. 
But adding some code that wasn't covered, and that wasn't tested was considered bad for the codecov. Indeed in that moment the repository commandant in chief asked me to add some tests.

For the tests, I used the existing test as a model for mine and I designed a test that would easily make sure that the functions worked.

After the commit of the version with the tests, the codecov was happier after that, *blegat* approved my second pull request.
