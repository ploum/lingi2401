# Open Source Contribution Project
*Author :* Jérome Eertmans

*Date :* September-December 2020

*NOMA :* 1355-16-00

## Research and Selection of the Project

### Starting with **Pandas**

As I am a frequent user of numerical libraries in Python, I would like to contribute to one of them. The one which can still grow a lot, in my opinion, is [Pandas](https://github.com/pandas-dev/pandas) and it is why I first wanted to contribute to this great package. After digging in the [Pandas' contribution guide](https://pandas.pydata.org/docs/dev/development/contributing.html#where-to-start) and the various issues, I started becoming less attracted by contributing to issues that I didn't even care about: as Pandas is very popular, most interesting issues to me are closed very quickly and what is left is to build tests. I think that tests are important but it was not how I wanted to contribute to an open source project, at least for now. The Pandas unit tests are a painful way to start contributing as they need very long compilation time, a lot of side packages and trying to build everything came with a lot more issues than it started with.

### Changing to **Numba**

Later, I was coding in Python for an another course and I started using the [Numba](https://numba.pydata.org/) library for performances purposes, which is something I am very interested in. After a few minutes, I encountered a reference bug within the package. Before raising the alarm to the Numba community, I read their documentation, went through multiple issues and even came to find a fix to my issue.

## Starting to contribute to the project

Because it was an easy issue that I understand quite well, I created an [issue](https://github.com/numba/numba/issues/6276) that I documented as much as possible, while also following their guidelines. Quickly, a contributor replied to me and told me that I could try to fix this issue. After some comments we exchanged, we discover that it was actually 2 separated issues: he assigned me to the first one and I'm still investigating on the second one.

### First contribution to Numba

It turned out that the latter was not an issue related to Numba but more likely to Python's behavior. Anyway, my fix was pretty easy and my [PR](https://github.com/numba/numba/pull/6277) got accepted within the first 24 hours of existence of the [issue](https://github.com/numba/numba/issues/6276). My PR has been now merged and will be released with version [0.52](https://github.com/numba/numba/milestone/40).

```diff
diff --git numba/numba/np/arraymath.py jeertmans/numba/np/arraymath.py
@@ -4395,7 +4395,7 @@ def impl(a, b):
            raise ValueError((
                "Dimensions for both inputs is 2.\n"
                "Please replace your numpy.cross(a, b) call with "
-               "numba.numpy_extensions.cross2d(a, b)."
+               "a call to `cross2d(a, b)` from `numba.np.extensions`."
            ))
    return impl
```

Even though fixing the error was quite an easy task, I learn many interesting things on how to contribute and here is a quick summary:

#### 1. Reproducible error

Numba's community asks issues to fullfill two criterions:
- [x] I have tried using the latest released version of Numba (most recent is
 visible in the change log (https://github.com/numba/numba/blob/master/CHANGE_LOG).
- [x] I have included below a minimal working reproducer (if you are unsure how
 to write one see http://matthewrocklin.com/blog/work/2018/02/28/minimal-bug-reports).

Before posting my issue, I made sure to check them and that there was no similar issue already existing.

#### 2. Searching for a fix

I think that, when you post an issue, it is important to at least search for a fix. It will help other people understand what really goes wrong and how to quickyl adress your problem. I did search a fix and even found one.

So, I also proposed to be the one in charge of fixing the issue.

#### 3. Discuting the field of the fix

It is important to determine what should be fixed and what should not. Even if an error can be very wide, some of the **bad** behavior can be intentional. With the help of the Numba's contributors, we defined the field of what should be done.

#### 4. Making a Pull Request and adapting it

When I got the issue fixed, I made a PR. Quickly after, I received comment on what was good and what could be improved in my fix. The reviewers were super nice to me and helped me understand everything I needed to check before my PR could be considered a valid.

So, even if my fix started with a one line change in the code, I ended up updating
other parts of the code as well as checking that everything was working as expected
with unit tests.

### Second contribution to Numba

Because I still wanted to contribute to Numba, I searched through the proposed implementations listed in this [issue](https://github.com/numba/numba/issues/4074) and decided to implement the [`numpy.allclose`](https://github.com/numba/numba/issues/4074) function. I tried to be as complete as possible so I took other successful PR as example.
Once I was quite confident about my implementation, I started a [PR](https://github.com/numba/numba/pull/6286).

My PR is for the moment in the *ready for review* state.

Because Numba's main purpose is to accelerate execution time, it is interesting to see how my implementation compares with the original function (almost 6 times faster !).
 ```python
import numba as nb
import numpy as np

@nb.njit  # What I implemented (code is hidden behind the `njit` wrapper)
def allclose(a, b):
    return np.allclose(a, b)

a = np.random.rand(100, 100)

np.allclose(a, a)
>>> True
allclose(a, a)
>>> True
%timeit allclose(a, a)  # My implementation
>>> 10.9 µs ± 31.4 ns per loop (mean ± std. dev. of 7 runs, 100000 loops each)
%timeit np.allclose(a, a)  # Reference function
>>> 59.4 µs ± 221 ns per loop (mean ± std. dev. of 7 runs, 10000 loops each)
```
