# Open Source Contribution Project

*Author:* Alisson Carvalho

*NOMA:* 54661900

*Year:* 2021

*Selected project:* [nevergrad](https://github.com/facebookresearch/nevergrad)

# Project Research and Selection

I discovered nevergrad while doing my Master's thesis, looking for libraries in python that offered different optimization methods, specially Evolutionary Algorithms. Nevergrad is a optimization library that offers severall different optimization techniques. None of these techniques depend on calculating the gradient of the objective functions, hence the name NeverGrad was chosen.

Nevergrad offered the biggest selection of optimization algorithms, mostly (but not limited to) Evolutionary Algorithms. Using a single library for many optimization techniques saves a lot of time, as it would take me the need to change just a single line of code to experiment a whole different optimization technique.

Nevergrad is an awesome library with several optimization techniques, but there are some improvements possible.

## Possible Contributions

When dealing with Evolutionary Algorithms, most of these algorithms use a population of individuals to perform optimization. Each of these individuals represent a set of values that are going to be tested, in order to perform the optimization.

But in nevergrad the numbers of individuals in each population cannot be set by the developer. The default number of individuals is kept the same, for anyone using an optimization technique, like PSO (Particle Swam Optimization) and DE (Differential Evoluation). The number of individuals in each population may affect the result of the optimization, as it will define how many evaluations of the objective function will be performed.

It is important that the developer is able to change features of the optimization techniques based on their needs, as some optimization problems may require different configurations of the optimization technique, some configurations that are different than the default configuration.

Also, there are some optimization techniques used in Hyperparameter optimization that are widely used, but not available in nevergrad. For example, SMAC (Sequential Model-based Algorithm Configuration) is a great optimization method for hyperparameter optimization, but it is not available in nevergrad.

In Conclusion, I would like to extend the customization of some optimization techniques, that only use default values for individuals in a population, and enable the developer to choose how many individuals they will use in their optimization. In case there is still time and the task is feasible, I would like to add SMAC to nevergrad.

## The Actual Contribution
After looking through the issues (and getting in contact with the admin's) of the project, I decided to move from the possible contributions described above to a more practical contribution, as these improvements wre less needed than improving what was already implemented.

One of the admins of the project gently listed a few issues happening at the moment and that were feasible for first-time contributors. The problem consisted in some libraries that were required to run the Nevergrad library, but there were many dependencies, which made the library itself slower than it could be. (For example, installing it on developer's mode would take more than a day...)

I fixed some of the dependencies, making it optional to the user, only importing it when really needed, to make the library faster and more reliable for its user.

# Pull Request
The PR was done, and its available [here](https://github.com/facebookresearch/nevergrad/pull/1308). Waiting for it to be approved and merged.