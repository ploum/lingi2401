# Open Source Contribution Project
*Author :* Jérome Eertmans

*Date :* September-December 2020
*NOMA :* 1355-16-00

## Research and Selection of the Project

### Starting with **pandas**

As I am a frequent user of numerical libraries in Python, I would like to contribute to one of them. The one which can still grow a lot, in my opinion, is [pandas](https://github.com/pandas-dev/pandas) and it is why I would like to contribute to this great package. After digging in the [pandas contribution guide](https://pandas.pydata.org/docs/dev/development/contributing.html#where-to-start) and the various issues, I started becoming less attracted by contributing the issues that I don't even care about: as pandas is very popular, most interesting issues to myself are closed very quickly and what is left is to build tests. I think that tests are important but it not the way I want to contribute to open source project, at least for now. The pandas unit tests are a painful way to start contributing as they need very long compilation time, a lot of side package and it trying to build everything came with a lot more issues than it started with.

### Changing to **numba**

Later, I was coding in Python for an another course and I started using the [numba](https://numba.pydata.org/) library for performances purposes, which is something I am very interested in. After a few minutes, I encountered a reference bug with the package. Before raising the alarm to the numba community, I read their documentation, went through multiple issues and even came to find a fix to my issue.

## Starting to contribute to the project

Because it was an easy issue that I understand quite well, I created an [issue](https://github.com/numba/numba/issues/6276) that I documented as much as possible, while also following their guidelines. Quickly, a contributor replied to me and told me that I could try to fix this issue. After some comments we exchanged, we discover that it was actually 2 separated issues: he assigned me to the first one and I'm still investigating on the second one.

https://github.com/numba/numba/issues/6276

https://github.com/numba/numba/pull/6277/files

```diff
            raise ValueError((
                "Dimensions for both inputs is 2.\n"
                "Please replace your numpy.cross(a, b) call with "
-               "numba.numpy_extensions.cross2d(a, b)."
+               "a call to `cross2d(a, b)` from `numba.np.extensions`."
            ))
    return impl


```
