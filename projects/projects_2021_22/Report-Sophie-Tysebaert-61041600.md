# Open Source Contribution Project

- Author: Sophie Tysebaert
- NOMA: 61041600
- Academic year: 2021-2022
- Summary: The aim of this report is to document my whole process of contributing to an open source project, **FreshRSS**, a self-hostable RSS aggregator.

## Personal Background

Since several years, I am interested in the free software movement because of its awareness of our increasingly dependence on digital tools and the consequences that these latter ones may have on people. Free software movement takes ethical considerations into account (e.g.: how to debate with others on a subject if the information we can find on it is "personalized"? How to consider the truth in this case? Who may contribute to knowledge? Why? Why not? Think about the epistemological consequences projects such as Wikipedia may have). It contrasts with a large part of tech organizations, where these philosophical considerations are simply ignored.

This movement is also driven by a large community dedicated to the cause of freedom, sharing and popular education. These values are aimed to empower people.

For these reasons, I am supporting this movement, especially the French community/French initiatives around the free culture (by using myself free open source softwares/apps, by promoting them and by donating).

## Project Selection

In this context, finding an open source project was easy for me. One year ago, I have heard about [FreshRSS](https://freshrss.org), a lightweight self-hostable RSS aggregator. I installed it on my home server and I am using this web app (in combination with [RSS-Bridge](https://github.com/RSS-Bridge/rss-bridge)) in order to have a centralized view on the web contents that I am interested in, while keeping my data for myself.

I would like to work on this project. FreshRSS is also known for its empathic community. This project was created by [Marien Fressinaud](https://marienfressinaud.fr/), a French software engineer (working currently on [Flus](https://flus.fr/)) and is still actively maintained by himself and 3 other people ([Alexandre Alapetite](https://github.com/Alkarex), [Alexis Degrugillier](https://github.com/aledeg) and [Frans de Jonge](https://github.com/Frenzie)), along other "sporadic" contributors. They are using GitHub as the main platform to interact with the community, but they also have a Mattermost instance (hosted on Framateam), although it seems not very active.

## Setting up a Development Environment

Before contributing to the project, we need to set up a development environment. For that, the [developer documentation](https://freshrss.github.io/FreshRSS/en/developers/02_First_steps.html) is useful. The next step is to understand how the source code is structured. However, there is almost no documentation to explain it (except [this file](https://github.com/FreshRSS/FreshRSS/blob/edge/docs/en/developers/03_Backend/05_Extensions.md), which gives insight about Minz library). Thus, an useful contribution to this project would be to populate it.

## Contributing to the Project

[Contributing guidelines](https://github.com/FreshRSS/FreshRSS/blob/master/CONTRIBUTING.md) are also present on GitHub. As I am a first-time contributor, I am primarily focused on issues that are tagged `good first issue`. In [this list](https://github.com/FreshRSS/FreshRSS/contribute), I also filtered issues to select the ones that should be ideally implemented for the next version of the web app (milestone `1.19.0`). [Here](https://github.com/FreshRSS/FreshRSS/issues?q=is%3Aopen+is%3Aissue+milestone%3A1.19.0+label%3A%22good+first+issue%22) are such issues.

### New Keyboard Shortcut "Next Unread Article"

There are some predefined keyboard shortcuts on FreshRSS, such as "Open the next article", "Open the previous article", etc. However, there was no keyboard shortcut to jump directly to the next *unread* article, as suggested by an user ([issue #3393](https://github.com/FreshRSS/FreshRSS/issues/3393)). I implemented it (here is my [PR](https://github.com/FreshRSS/FreshRSS/pull/3891)).

This contribution was merged into `FreshRSS:edge` a few days later. Thanks to the discussion around this PR, I also learned the existence of the project [EditorConfig](https://editorconfig.org/) to maintain consistent coding styles (I added unintentionally coding style inconsistencies, by using spaces instead of tabs in some files).

### Bug: Using `Space` as Keyboard Shortcut Triggers Additional Scrolling with Google Chrome

After the aforementioned contribution was merged, there was a discussion with another contributor (the author of the issue #3393 actually) about the potential introduction of a bug by my PR: with Google Chrome, using `Space` as a keyboard shortcut (for "Jump to next article", "Jump to the next unread article", ...) leads to an erratic behavior, triggering either additional scrolling or the assigned action for `Space` keyboard.

I was not sure whether I introduced (unvoluntarily) this bug or not: I did not test myself all keyboard shortcuts combinations. We have discussed it [here](https://github.com/FreshRSS/FreshRSS/pull/3891#issuecomment-952015867), before a [new issue was opened for this bug](https://github.com/FreshRSS/FreshRSS/issues/3946), as it was not introduced by my contribution, but appeared somewhere between the latest stable version (1.18.1) and the latest commit before my changes have been accepted and merged.

This issue #3946 is on my todo list, as I now would like to be a detective and to find first when this bug was introduced, in order to understand more precisely how this erratic behavior could appear (and how to tackle it).