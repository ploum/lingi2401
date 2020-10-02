# Report for LINGI2401 project
> _Nicolas Rybowski - 17001500_

## GOAL : Adding `--ignore` option to the upgrade command of [APK](https://wiki.alpinelinux.org/wiki/Alpine_Linux_package_management) (Alpine Package Keeper)

## Background
APK is the package manager from the [Alpine Linux distribution](https://alpinelinux.org/). I'm using this distribution for years for lightweight containers/VM's and as bare-metal OS for Raspberry Pi's so I was
very interested to collaborate on this project.

With the project chosen, I looked through open issues and I picked [this one](https://gitlab.alpinelinux.org/alpine/apk-tools/issues/8792) due to 2 main reasons : 
- As mentioned into the issue, `pacman` gives a similar command and as an Arch Linux user myself, I know at which point this command is useful.
- As an Alpine Linux user myself too, I also missed this command in some cases.

## Roadmap

### 2019-09-27
- choosing project + planned contribution
- [project proposal merged into the course's repo](https://github.com/ploum/lingi2401/pull/76)

### 2019-09-28
- reading source code

### 2019-10-01
- reading source code
- searching doc on internal behavior of APK
  - found this : https://wiki.alpinelinux.org/wiki/Apk_internals (last edited on 19 September 2017, at 00:32)
  - beginning documenting my understanding of the APK internals
- searching communication channels
  - found : 
    - IRC : #alpine-devel, #alpine-docs on freenode
    - mailing list : https://lists.alpinelinux.org/~alpine/devel
  - planning to ask if ["developer handbook"](https://docs.alpinelinux.org/developer-handbook/0.1a/index.html) still under [dev](https://gitlab.alpinelinux.org/alpine/docs/developer-handbook)
    - I want to contribute with my "personal documentation" but I dont know which is the best support between the official wiki and the (inactive) dev handbook.
- detecting some memoryleak (still reachable in valgrind)

### 2019-10-03
- reading source code
- adding `--ignore PACKAGE` option to `upgrade` applet and getting argument into `upgrade.c: upgrade_main`
- defining changes to perform into `solver.c` and `apk_solver_data.h`

### 2019-10-04/05 (night work is funny)
- working code + [first commit](https://github.com/nrybowski/apk-tools/commit/4202a198b8b852a51793a2614745d2ea6f0c490b)
  - the new code still pass all the previous test cases
  - not yet added new test cases for the new option
> UPDATE 2019-12-10
> Since I force pushed a new version of the code, the previous link might be lost. [Here is a link](https://github.com/nrybowski/apk-tools/commit/4202a198b8b852a51793a2614745d2ea6f0c490b) toward a backup of this commit.

### 2019-10-12/13 (still night work)
- [adding test case](https://github.com/nrybowski/apk-tools/commit/8e507211342ff6f0bc02d3cafc63d7a1371e6c23) for the implemented feature (2nd commit)
- opened [PR](https://github.com/alpinelinux/apk-tools/pull/24) on the github project repository
- signaling the PR on [the original issue discussion](https://gitlab.alpinelinux.org/alpine/apk-tools/issues/8792)
- contacting the community via IRC #alpine-docs (cfr 2019-10-01)
  - the maintainer of the developer handbook advised me to collaborate on this project
  - signaling that the SSL certificates of the doc websites expired on september 2019
- working on the documentation
- working on fixing the travis build script

### 2019-10-15
- [working on fixing the travis build script](https://github.com/alpinelinux/alpine-chroot-install/issues/17#issuecomment-542309154) of apk-tools repo.
- opened PR on [alpine-chroot-install](https://github.com/alpinelinux/alpine-chroot-install/pull/18) to fix travis build failure.

### 2019-10-17
- PR on [alpine-chroot-install](https://github.com/alpinelinux/alpine-chroot-install/pull/18) merged.
- discussing with the maintainer of alpine-chroot-install on [the future of the script](https://github.com/alpinelinux/alpine-chroot-install/issues/17)
- opened issue on [alpine-chroot-install](https://github.com/alpinelinux/alpine-chroot-install/issues/19)
- adding some reviews and asking for feedback on the [PR of apk-tools](https://github.com/alpinelinux/apk-tools/pull/24#discussion_r336157432) since the PR is opened since 
5 days and there is no reaction from the maintainers of the repo.

### 2019-10-18
- debugging alpine-chroot-install v0.11.0 and [updating related issue](https://github.com/alpinelinux/alpine-chroot-install/issues/19#issuecomment-543594869).
- working on integration of `nix` into `alpine-chroot-install` script as mentioned [here](https://github.com/alpinelinux/alpine-chroot-install/issues/17#issuecomment-543184139)

### 2019-10-19
- working on integration of `nix` into `alpine-chroot-install` script as mentioned [here](https://github.com/alpinelinux/alpine-chroot-install/issues/17#issuecomment-543184139)
  - not yet sucessful result so I'm not pushing any code on my fork.

> **Long break due to other courses**

### 2019-11-13
- asking for feedback on the [PR](https://github.com/alpinelinux/apk-tools/pull/24#issuecomment-553361130)
- issue on [alpine-chroot-install](https://github.com/alpinelinux/alpine-chroot-install/issues/19) closed by maintainer

### 2019-11-27
- writing conclusion in the report

### 2019-12-04
- asking for feedback on the [issue](https://gitlab.alpinelinux.org/alpine/apk-tools/issues/8792)
- got a response on the same thread, the maintainer propose another method to implement the feature

### 2019-12-09/10 (did i said you that i like night work ?)
- working on the new implementation of the feature + [new commits to the PR](https://github.com/alpinelinux/apk-tools/pull/24/commits/e7b589e01b6a1a0a4c3c2c5f6184503577336206)
- got a direct review from the project's maintainer (5 hours after the commit) which [requested some (very) minor changes and proposed a new feature](https://github.com/alpinelinux/apk-tools/pull/24#pullrequestreview-329632226) related to the one I implemented
- [signaling a new bug in the testing procedure](https://gitlab.alpinelinux.org/alpine/apk-tools/issues/8792#note_57156). The project's maintainers are invastigating the issue.
- updating report conclusion

### 2019-12-11/12
- [applying the requested changes](https://github.com/nrybowski/apk-tools/commit/f38eea3ba9aee901b6a675ea6a3f2e018e78490f)
- [fixing indent as requested](https://github.com/nrybowski/apk-tools/commit/d76c3a5015fa43fba2bd94b9c235eee18800ff34)
- [opening new issue on gitlab](https://gitlab.alpinelinux.org/alpine/apk-tools/issues/10667) in order to track the new feature proposed during the PR review
- [PR merged](https://github.com/alpinelinux/apk-tools/pull/24#issuecomment-564974060)

## Conclusion

From a technical point of vue, this project was very interesting. Since there is no documentation and almost no comments into the code, it was a funny challenge to understand the logic of 
the code and to find the points where code addition or modification were required in order to add the feature. After I added the feature, I also worked on another part of the Alpine Linux project, that is `alpine-chroot-install`, which is a script used in order to quickly install Alpine Linux into a chroot. This script is used to provide a testing environment for the `apk-tools` project in Travis. When I opened my PR, I saw that this script was broken and this made all the tests of all the PR fail without any good reason. So I worked on this in order to make the tests usefull again.

From a community point of vue, this project was a bit disappointing. At the time I write these lines, that is end of novembre, I still do not have any reviews nor explicit reactions from 
the maintainers of the project so I have no idea if the code I wrote comply with the project's guidelines nor if my pull request will be merged or refused. I feel like my work is a little bit
 like wasted time since it won't profit to anyone. Since I hesitated between multiples projects to collaborate on, this time could have been allocated to another project with a faster feedback.

On the other hand, when I asked advice on the `#alpine-doc` IRC channel I received an immediate response which is great. So, despite this experience, I'm still interested into contributing to this project. 

> **Conclusion update**. I let the previous comments here since this report is a log of my project and that it was my mind at this time. Fortunatly, the situation evolved a lot since then so I add here some points to my conclusion.

As you can see in the logs of december, there is by far more interaction with the community. I think my main error was to work on the github mirror of the project rather than directly working on the specific gitlab. Once I moved back on the gitlab, I had quite fast interactions with the community about my PR.

My PR was finally merged thanks to the multiple reviews of the project maintainer. Furthermore, he proposed me a new feature related to the implementation I provided for the current one. This incite me to continue to collaborate to this project. Since Alpine Linux is a distribution I really like, I hope that I will be able to become a more regular contributor to the different aspects of the project.

I'm also very thankful toward the course because I'm not sure I would have had the courage to try to integrate an Open Source community without it. Although this might be a diffcult step, it's also rewarding when we see that our work is appreciated. This project was globally a great experience !
