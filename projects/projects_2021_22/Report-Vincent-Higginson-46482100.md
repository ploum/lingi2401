# Open Source Contribution Project

| **Author:**              | *Vincent Higginson*                                 |
| ------------------------ | --------------------------------------------------- |
| **Date:**                | 28/09/2021                                          |
| **NOMA:**                | 4648-21-00                                          |
| **Academic Year:**       | 2021-2022                                           |
| **Open Source Project:** | [Selfmake](https://github.com/netzwerkz/selfmake) |
| **License:**             | [MIT](https://github.com/netzwerkz/selfmake/blob/main/LICENSE.txt) |

## Finding the project

During two days, I wandered on github trying to find an interesting and not-so-complicated project. My requirements were so precise, someone might think I was shopping. The project had to be useful, not a web-based app, written in C/Rust, ... Suddenly, I found [netzhaut](https://github.com/netzwerkz/netzhaut). A web browser engine, developed as an alternative to webkit and chromium. Such an ambitious project could only attract me.

## Contacting the dev

Sadly, the project seems to be in design phase with just one main contributor. The "official" site is quite complete, but it lacks a roadmap or a list of missing features. So without waiting any longer, I fired an email, and I've got an almost instant answer. We were both on the same wavelength: we need a framework able to become an alternative to webkit and chromium, as they're too omnipresent and influential. Monopoly of a technology is never a great thing. We exchanged a lot and all the information I got from him influenced the following decisions I made.

## Compiling the project

Contributing to a project means helping the project by adding/correcting interesting parts. It's evident you have to compile/run it first before pretending to modify it. Oh! The original developer uses only a GNU/Linux machine (what a great guy), and I use a macOS machine (what a stupid yet classy guy). You know what that means? A wonderful port! Oh wait... The toolchain used to build the project is also a GNU/Linux only utility... Do you see me smiling?

## Porting the toolchain to macOS

Before contributing to the main project (netzhaut), I have to port every single dependency to macOS. It all starts with the toolchain. As it's a rather complex project divided into multiple parts, a custom set of build tools was implemented. During two days, I had the honor to dive into the documentation of macOS-only methods replacing GNU/Linux-only one in the source code of selfmake. Some `#if defined(__APPLE__)` here and there, and it was working like a charm!

You can consult my pull request https://github.com/netzwerkz/selfmake/pull/2.

## Communication

As you can see with the commits history, it was a work done by two guys talking to each others, and not the result of a wild pull request coming from nowhere. A lot of e-mails and discord messages were written to help me understand the whole project and the wishes of the original dev.

