# Open Source Contribution Project
*Author :* Jérome Eertmans

*Date :* September-December 2020

*NOMA :* 1355-16-00

## Research and Selection of the Project

[![forthebadge made-with-python](http://ForTheBadge.com/images/badges/made-with-python.svg)](https://www.python.org/)

### Starting with **Pandas**
[![PyPI download month](https://img.shields.io/pypi/dm/pandas.svg)](https://pypi.python.org/pypi/pandas/) [![PyPI license](https://img.shields.io/pypi/l/pandas.svg)](https://pypi.python.org/pypi/pandas/) [![GitHub contributors](https://img.shields.io/github/contributors/pandas-dev/pandas.svg)](https://GitHub.com/pandas-dev/pandas/graphs/contributors/)

As I am a frequent user of numerical libraries in Python, I would like to contribute to one of them. The one which can still grow a lot, in my opinion, is [Pandas](https://github.com/pandas-dev/pandas) and it is why I first wanted to contribute to this great package. After digging in the [Pandas' contribution guide](https://pandas.pydata.org/docs/dev/development/contributing.html#where-to-start) and the various issues, I started becoming less attracted by contributing to issues that I didn't even care about: as Pandas is very popular, most interesting issues to me are closed very quickly and what is left is to build tests. I think that tests are important but it was not how I wanted to contribute to an open source project, at least for now. The Pandas unit tests are a painful way to start contributing as they need very long compilation time, a lot of side packages and trying to build everything came with a lot more issues than it started with.

### Changing to **Numba** 
[![PyPI download month](https://img.shields.io/pypi/dm/numba.svg)](https://pypi.python.org/pypi/numba/) [![PyPI license](https://img.shields.io/pypi/l/numba.svg)](https://pypi.python.org/pypi/numba/) [![GitHub contributors](https://img.shields.io/github/contributors/numba/numba.svg)](https://GitHub.com/numba/numba/graphs/contributors/)


Later, I was coding in Python for an another course and I started using the [Numba](https://numba.pydata.org/) library for performances purposes, which is something I am very interested in. After a few minutes, I encountered a reference bug within the package. Before raising the alarm to the Numba community, I read their documentation, went through multiple issues and even came to find a fix to this issue.

In short, Numba increases Python's performances by compiling function using an optimized compiler, while keeping the code pretty simple:

```python
def some_function(x):  # Any function using pure Python or even Numpy functions
    """
    Some code
    """

import numba

@numba.njit
def some_function(x):  # Same function but Numba will optimize it
    """
    Some code
    """
```

<p align="center">
    <img src="https://i1.wp.com/murillogroupmsu.com/wp-content/uploads/2018/01/plot-3.png?resize=648%2C648&ssl=1">
    </img>
</p>
<p align="center">
    Source: https://murillogroupmsu.com/numba-versus-c/
</p>

## Starting to contribute to the project

Because it was a simple error that I understood quite well, I created an [issue](https://github.com/numba/numba/issues/6276) that I documented as much as possible, while also following their guidelines. Quickly, a contributor replied to me and told me that I could try to fix this issue. After some comments we exchanged, we discovered that it was actually 2 separated issues: he assigned me to the first one and I kept investigating on the second one.

### First contribution to Numba

It turned out that the latter was not an issue related to Numba but more likely to Python's behavior. Anyway, my fix was pretty easy and my [PR](https://github.com/numba/numba/pull/6277) got accepted within the first 24 hours of existence of the [issue](https://github.com/numba/numba/issues/6276). My PR has been now merged and will be released with version [0.52](https://github.com/numba/numba/milestone/40): ![](https://img.shields.io/github/commit-status/numba/numba/master/38ecdf9bfb25017e4e234cc7f7535ebd2c3246d3)

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

Even though fixing the error was quite an easy task, I learned many interesting things on how to contribute and here is a quick summary:

#### 1. Reproducible error

Numba's community asks issues to fulfill two criteria:
- [x] I have tried using the latest released version of Numba (most recent is
 visible in the change log (https://github.com/numba/numba/blob/master/CHANGE_LOG).
- [x] I have included below a minimal working reproducer (if you are unsure how
 to write one see http://matthewrocklin.com/blog/work/2018/02/28/minimal-bug-reports).

Before posting my issue, I made sure to check them and that there was no similar issue already existing.

#### 2. Searching for a fix

I think that, when you post an issue, it is important to at least search for a fix. It will help other people understand what really goes wrong and how to quickly address your problem. I did search a fix and even found one.

So, I also proposed to be the one in charge of fixing the issue.

#### 3. Deciding the field of the fix

It is important to determine what should be fixed and what should not. Even if an error can be very wide, some of the **bad** behavior can be intentional. With the help of the Numba's contributors, we defined the field of what should be done.

#### 4. Making a Pull Request and adapting it

When I got the issue fixed, I made a PR. Quickly after, I received comment on what was good and what could be improved in my fix. The reviewers were super nice to me and helped me understand everything I needed to check before my PR could be considered a valid.

So, even if my fix started with a one line change in the code, I ended up updating
other parts of the code as well as checking that everything was working as expected
with unit tests.

<img src="https://dev.azure.com/numba/numba/_apis/build/status/numba.numba?buildId=6745"></img>

### Second contribution to Numba

Because I still wanted to contribute to Numba, I searched through the proposed implementations listed in this [issue](https://github.com/numba/numba/issues/4074) and decided to implement the [`numpy.allclose`](https://numpy.org/doc/stable/reference/generated/numpy.allclose.html) function. I tried to be as complete as possible so I took other successful [PR](https://github.com/numba/numba/pull/6277) as example.
Once I was quite confident about my implementation, I started a [PR](https://github.com/numba/numba/pull/6286).

Quickly, a reviewer reached me and we started discussing about my implementation. I made several changes to my initial commits because, even if my code was optimized, it was not a perfect copy of the behavior of `numpy.allclose` function. They prefer to have a reliable code, even it is comes with a performance cost.

My PR is for the moment in the *Waiting on reviewer* state and I am actively working on it.

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

# Oral examination content

La programmation open source pour la recherche scientifique : le cas de Anaconda Inc.

## Commentaires

Suite au cours, j'ai :

- vu mon intérêt grandir pour l'open source et j'ai regardé beaucoup de conférences sur des projets open source ainsi que lu énormément sur le sujet
- décidé de postuler pour un doctorat dans lequel je développerai un outil open source (dans un domaine où les boites privées priment)
- continué à contribuer à Numba, mais aussi à Numpy ou ics.py, des outils fortement utilisés dans mes projets
- découvert énormément d'outils utiles à la C.I. et au linting, que j'ai intégré dans de nombreux projets comme [ADE Scheduler](https://github.com/SnaKyEyeS/ADE-Scheduler)
- lancé plusieurs projets avec l'objectif de m'entrainer à fournir du code meilleure de qualité : [le package Strong](https://github.com/jeertmans/strong), [Triangulation Delaunay](https://github.com/jeertmans/DelaunayTriangulation) et récemment [texspell](https://github.com/jeertmans/texspell)

Lien vers quelques contributions :

- [Numba](https://github.com/numba/numba/pull/6286)
- [Numba](https://github.com/numba/numba/pull/6277)
- [Numpy](https://github.com/numpy/numpy/pull/18193)
- [ics.py](https://github.com/C4ptainCrunch/ics.py/pull/260)


## 1- Historique 

    1940-1960 : automatiser des tâches répétitives (calculs) 

    1980 : abstraction de plus en plus présente (OOP) 

    1980 : langages visuels (MATLAB, LabVIEW ou Wolfram) mais propriétaires €€ 

    1990 : internet arrive… Python (licence PSF)  (3ème) et R (licence GNU GPL) (9ème) aussi ! 

## 2- Python (et R) sort du lot 

    Enormément de librairies 

    Peut utiliser du C 

    Langage interprété 

    1995 : Numeric devenu Numpy (BSD) en 2005 

    2000, 2.0 : plein d’ajouts majeurs dont GC et support Unicode 

    2001 : Scipy (BSD) 

    2003 : Matplotlib (Licence MPL ~ BSD ~ PSF) 

    2008 : Pandas (BSD) et Python 3.0 

    2015 : fin de vie initiale de Python 2.7 

## 3 - Petite digression 

- En 2020, un pacte est signé pour arrêter le support de Python 2.7 : https://python3statement.org/. 

- Python utilise plein de noms basés sur les sketchs des Monty Python. 

## 4 - Plein d’outils… mais comment les combiner ? 

    2012 : Création de Anaconda & Conda 

    Vente de serveur Anaconda 

    Création de NumFocus & PyData, Numba, Bokeh & Blaze 

    2015 : investissement à risque de la part de plusieurs groupes 

    2017 : première convention 

    Anaconda lance un solution entreprise 

    2020 : Anaconda lance une solution équipe 

    Clients : American national bank, AT&T, Toyota, ExxonMobil, HSBC, BMW, etc. 

## 5 - Conda 

    Pure-Python est cross-platform 

    Compiler ne l’est pas => installation compliquée 

    Conda résout ce problème 

## 6 - NumFOCUS (& PyData) 

    Fondée en 2012 

    Créateurs de Numpy, IPython, Astropy, Matplotlib et Scipy 

    Organisation à but non lucratif 

    But éducationnel 

    Organise surtout des conférences 

    Sponsorisés par Anaconda, Booking.com, JetBrains, Tesco, Ebay, etc.  

## 7 - Numba 

    Utilise LLVM (BSD-like) 

    Performance de Python proche du C 

    Résout pas mal de problèmes liés à l’abstraction  

## 8 - Bokeh 

    Alternative (BSD) à PlotlyJS (MIT) 

    Pas aussi mature pour la 3D 

    PlotlyJS offre des solutions payantes, pas Bokeh 

## 9 - Blaze  

## 10 - Plein d’autres projets 

    Dask 

    Jupyter 

    Spyder IDE 
    
## Liens

- https://anacondacon.io/peter-wang-bio
- https://www.anaconda.com/about-us
- https://www.anaconda.com/press
- https://www.anaconda.com/press/anaconda-launches-anaconda-dividend-program-to-give-back-to-open-source-community
- https://fr.wikipedia.org/wiki/Anaconda_(Python_distribution)
- https://pydata.org/
- https://numfocus.org/history
- https://python3statement.org/
