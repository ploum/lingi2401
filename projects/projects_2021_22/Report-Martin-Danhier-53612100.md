# Open Source Contribution Project

- **Author**: Martin Danhier
- **NOMA**: 53612100
- **Year**: 2021
- **Selected project**: [MuseScore](https://github.com/musescore/MuseScore)

## Context

### About the project

MuseScore is a free and open source software for creating and editing music scores, and is used by thousands of musicians worldwide. It allows them to write music using a WYSIWYG editor similar to Microsoft Word, and to export the score to a variety of formats.

Currently, the community is working on the fourth major release, which aims to improve MuseScore's user experience and make it more intuitive for users coming from other programs, like Sibelius.

MuseScore is licensed under the GNU General Public License version 3.

It was developed using C++ and Qt.

Like the famous audio editing software [Audacity](https://github.com/audacity), the development of MuseScore is supported by the [Muse Group](https://mu.se/), which provides the project with full-time developers to help the community. 

### Choice of the project

As a pianist, I sometimes find myself in the need to write scores. Being free and open source, MuseScore is a great choice for me. However, the project always lacked a lot of UI polish and important quality of life features required to be as efficient with it as with other software, like Sibelius.

However, after having elected a new head designer, the MuseScore community decided to start working on the next major release, MuseScore 4, which will completely rework the user interface in a clean and modern way, as well as introducing new features and improvements.
In the long term, the software also aims to become a complete [digital audio workstation](https://en.wikipedia.org/wiki/Digital_audio_workstation) that would not only allow musicians to write scores, but also to render them into high quality audio files, removing the need for other dedicated proprietary softwares like [FL Studio](https://www.image-line.com/fl-studio/). This would make MuseScore much more intuitive and powerful than the proprietary alternatives.

Needless to say, I am particularly interested in the project, and I can't wait to see what the future holds. This is why I decided to join the community, and I hope my contribution will help the project reach its goal sooner.

## Contribution

### Building the project

Before starting to work on the project, I wanted to make sure to be able to build it and configure my IDE to support it.

This process is thankfully well documented on the repository's wiki.

However, since I wanted to use VSCode instead of QTCreator, I had to create the configuration files myself, since the provided ones were outdated. I still didn't submit them, since I am still improving them from time to time. I eventually will, once they are ready.

### Finding an issue

To welcome new contributors, the MuseScore community labelled several issues as "good-first-issue". I chose one of them to start with: [MuseScore#9201](https://github.com/musescore/MuseScore/issues/9201).

The problem was that when zooming in the editor without the mouse wheel (e.g with ``CTRL +``), the anchor point (focus point) of the zoom was always located at the top left corner of the editor, instead of the center point or the active user selection, if there is any.

### The fix

To fix this issue, I had to implement the following changes:

- Add a method to get the position of the canvas (in other words, the value by which the page was dragged around in the editor) because it was not accessible from the outside.
- Add a method to compute the focus point of the zoom (the center of the selection if there is any, or the center of the view otherwise).
- Use this method in the zoom ones in order to determine the focus point.

In order to do this, I had to understand the inner workings of the notation system. This knowledge will be helpful if I want to contribute to more complicated issues in the future.

I also had to respect the code style guidelines of the project, which are documented on the wiki.

I opened a pull request for my changes: [MuseScore#9365](https://github.com/musescore/MuseScore/pull/9365).

Quickly, reviewers suggested changes in order to improve the quality of the fix (there still were code style issues, and I used Qt built-in classes where the internal format was preferred.)

After several iterations of fixes, the changes were finally approved and the PR was merged in the master branch !🎉

## Conclusion

### What I learned

This contribution not only taught me the structure of the code base, but also how the community works and what kind of answers I can expect from it.

In my later contributions, I also learned what kind of issues are the best to focus on (e.g try to focus on the issues that were approved by the maintainers with specific labels).

It also taught me things I didn't know about Git and GitHub, for example that if you include `Fix <issue-id>` in the commit name, the issue will be closed automatically when the commit is merged into the master branch. It also taught me about Git rebases, and how to "squash" several commits into a single one.

### Future contributions

Since everything went well for this first contribution, I decided to continue working on the project. I already managed to have several other pull requests merged (such as [MuseScore#9486](https://github.com/musescore/MuseScore/pull/9486) or [MuseScore#9532](https://github.com/musescore/MuseScore/pull/9532)), but I plan on doing more in the future.

In a later future, I'd like to have the opportunity to work on issues with a larger scale instead of tiny fixes. For now, most of these issues are directly assigned to the core team. I will try to contact the maintainers about it on their Discord server.
