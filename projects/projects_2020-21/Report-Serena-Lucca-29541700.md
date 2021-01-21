# Open source contribution project

**Author:** Serena Lucca \
**Noma:** 29541700 \
**Academic year:** 2020-2021

# Summary

- **Project:** [Exercism](https://github.com/exercism/v3)
- **Issue:** [https://github.com/exercism/v3/issues/2880](https://github.com/exercism/v3/issues/2880)
- **Pull request:** [https://github.com/exercism/v3/pull/2898](https://github.com/exercism/v3/pull/2898)

# Selection of the project

- At first, I wanted to contribute to one of python's big libraries. The problem here is that it is very hard to find an issue that is interesting and good for beginners. 
- I kept looking for a project in python but most of them seemed uninteresting to me.
- I searched for projects in other programming languages such as C and Java.
- I looked up the libraries in javascript and typescript that I was using for another project but as a mather of fact I did not have enough skills to contribute to one of those.
- After the deprecation of "Google Play Music", I decided to use an open source multimedia player and I found a thing that was bothering me so I posted an [issue](https://github.com/timusus/Shuttle/issues/523). Unfortunately, this project is dead, no one ever replied to me.
- I was looking for a project for 10 weeks so I decided to check out the Exercism repo because it seemed that each year, a few students of this course contributed to this project. I know that the project is kind of generic and it is not something that I use much but I had to find someting to work on. And there it was, the perfect [issue](https://github.com/exercism/v3/issues/2880). 

# Contribution to the project

*06-12-20*

Here we are, I found *the* issue, it was asked to improve a concept exercise in my all time favourite language (Python) about my all time favourite data structure (`lists`).
I posted a comment to ask if I could implement it. No reply from anybody. I got bored and impatient so I decided to start working on it. All I had to do was to create and implement a few files:

- .docs/hints.md
- .docs/introduction.md
- .meta/design.md
- .concepts/lists/links.json 

I could also improve some other files but they really just seemed fine to me so I didn't. \
I had some questions about the way I was implementing the files so I asked them under the issue. No reply from anybody for a while so I decided to do it my way. \
That night I still had no replies on the issue so I decided to create the [PR](https://github.com/exercism/v3/pull/2898). The first commit didn't pass because I forgot to apply prettier on my files. The second commit passed all the mandatory checks.

*07-12-20*

I still don't have any reply under the issue or the PR. I'm waiting for reviews and for some discussion because this journey feels pretty lonely so far.

*07-12-20 Later*

Around 8pm, the incredibly nice and wholesome maintainer [BethanyG](https://github.com/BethanyG) replied to me. She made a very kind and complete review of my commit and she even replied in details to the questions I asked on the issue. \
I commited all the changes she proposed and I modified the introduction and about documents to add explanations on the slice notation. \
There will be a discussion about the hint file because I might have given too many details or examples, we are waiting on the input from the person who posted the issue.

*08-12-20*

During the night, I received more replies from [BethanyG](https://github.com/BethanyG) and a review from the user who posted the issue [valentin-p](https://github.com/valentin-p). \ 
I modified the files according to their comments and commited. I am now once again waiting for their replies.

*08-12-20 Later*

After some more changes and some more code review, I ran prettier one last time and then my PR was merged in the night. \
[BethanyG](https://github.com/BethanyG) and [valentin-p](https://github.com/valentin-p) were incredibly nice and supportive the whole time, I will keep a very good memory of my first contribution to an open source project and I hope that I will have the time to do it again soon.

# What I’ve learned

- how to make markdown files
- how to use prettier to respect a certain format
- it's never too late to start a project
- some people on github are very very nice
- it is very easy to contribute to exercism

# Oral exam: Tor

## Why I chose Tor *(this was added post exam)*
For some reason (watching mr robot actually) I became fascinated with cybersecurity and cryptography a few years back and at that time, I decided to install kali linux and use tor browser. I soon came to realization that those were quite useless to me for the use I made of my computer and the internet (Facebook and Youtube basically). I stopped using them because it was to complicated and unnecessary but I learned a few things thanks to that experience.
I still am very interested in cybersecurity and cryptography so I wanted my presentation to be on a subject linked to that. I don't use Tor nowadays but I see the great importance of tools like this one in the matter of privacy, anonymity, online freedom and anti-censorship hence why I decided to choose to present Tor

## History
Tor (The onion router) is free and open-source software for enabling anonymous communication by directing Internet traffic through a free, worldwide, volunteer overlay network consisting of more than seven thousand relays in order to conceal a user's location and usage from anyone conducting network surveillance or traffic analysis.

Each relay decrypts a layer of encryption to reveal the next relay in the circuit to pass the remaining encrypted data on to it.

The final relay decrypts the innermost layer of encryption and sends the original data to its destination without revealing or knowing the source IP address. (importance of Exit node!!!)

Onion routing develloped in 1995 by US gov with the purpose of protecting U.S. intelligence communications online.
Further developed by DARPA in 1997.
Tor launched in 2002.
Code released under free license in 2004. 
Tor project founded in 2006.

*added post exam* FYI: DARPA is an R&D agency of the US dept of defense responsible for the development of emerging technologies for use by the military. DARPA is known for supporting a precursor of the intenet during the cold war because they were scared that if a nuclear attack happened, communication would be lost between east and west coast of the us.

## License
Modified BSD license
This version allows unlimited redistribution for any purpose as long as its copyright notices and the license's disclaimers of warranty are maintained. The license also contains a clause restricting use of the names of contributors for endorsement of a derived work without specific permission.

## Business model
- funding and sponsorship
    - Research funding (fundamental research on privacy and censorship)
    - R&D funding (DARPA) build safer tools
    - Deployment and teaching funding (US gov) teach activists how to be safe online
    - Core organizational support (donations)
- membership

Finding funds: It's not "I'll pay you $X to do Y." but "We want to do X it will cost Y$, would you be interested to fund us?"

## Community
- donate
- volunteer
    - training
    - translating
- user research
- running a relay

"We will continue to work on improving our tools based on feedback from users"

## Importance of Tor
- anonymity and online freedom
    - Tor's anonymity function is a method for whistleblowers and human rights workers to communicate with journalists
    - The Tor Project states that Tor users include "normal people" who wish to keep their Internet activities private from websites and advertisers, people concerned about cyber-spying, users who are evading censorship such as activists, journalists, and military professionals.
    - Tor is increasingly used by victims of domestic violence and the social workers and agencies that assist them, even though shelter workers may or may not have had professional training on cybersecurity matters.
    - its usage by the Internet Watch Foundation, the utility of its onion services for whistleblowers, and its circumvention of the Great Firewall of China were touted.
    - Tor has enabled roughly 36 million people around the world to experience freedom of access and expression on the Internet while keeping them in control of their privacy and anonymity. Its network has proved pivotal in dissident movements in both Iran and more recently Egypt.
    - Tor has been praised for providing privacy and anonymity to vulnerable Internet users such as political activists fearing surveillance and arrest, ordinary web users seeking to circumvent censorship, and people who have been threatened with violence or abuse by stalkers.
- anti-censorship
    - Tor supports freedom of expression, including in countries where the Internet is censored, by protecting the privacy and anonymity of users.
    - people in "Internet-censoring countries" as its second-largest user base
    - by keeping some of the entry relays (bridge relays) secret, users can evade Internet censorship that relies upon blocking public Tor relays.
    - aid democracy advocates in authoritarian states
    - "Librarians have always cared deeply about protecting privacy, intellectual freedom, and access to information (the freedom to read). Surveillance has a very well-documented chilling effect on intellectual freedom. It is the job of librarians to remove barriers to information." (about relays being installed in lbraries)
- decentralized
    - Tor is decentralized by design; there is no direct readable list of all onion services, although a number of onion services catalog publicly known onion addresses.
- transparency and openness
    - Remember that transparency for a privacy project is not a contradiction: privacy is about choice, and we choose to publish all of these aspects of our work in order to build a stronger community. Transparency is about where the money comes from, but it's also about what we do with it: we show you all of our projects, in source code, and in periodic project and team reports, and in collaborations with researchers who help assess and improve Tor. Transparency also means being clear about our values, promises, and priorities as laid out in our social contract.

## Operation Onymous
Operation Onymous was formed as a joint law enforcement operation between the Federal Bureau of Investigation (FBI) and the European Union Intelligence Agency Europol. The international effort also included the United States Department of Homeland Security, Immigration and Customs Enforcement (ICE), and Eurojust. The operation was part of the international strategies that address the problems of malware, botnet schemes, and illicit markets or darknets. It was also linked with the war on drugs effort with the participation of the U.S. Drug Enforcement Administration (DEA).

"It would be great if there were more people reviewing our designs and code. For example, we would really appreciate feedback on the upcoming hidden service revamp or help with the research on guard discovery attacks" (Tor relying on community)

"Tor currently doesn't have funding for improving the security of hidden services. If you are interested in funding hidden services research and development, please get in touch with us." (Tor business model)

"One of our priorities remains to continue working to reduce our reliance on US government sources." (US gov founded 80% of Tor project in 2012, in 2019 it was 42%)

Agents of the NSA and the GCHQ have anonymously provided Tor with bug reports.
So you can imagine one part of GCHQ is trying to break Tor, the other part is trying to make sure it's not broken because they're relying on it to do their work.
So it's typical within governments, or even within large agencies, that you have two halves of the same coin going after different parts of Tor. Some protect it, some to try to attack it.

## Sources

https://www.bbc.com/news/technology-28886462

https://en.wikipedia.org/wiki/Tor_(anonymity_network)

https://www.torproject.org/

https://en.wikipedia.org/wiki/BSD_licenses

https://blog.torproject.org/

https://en.wikipedia.org/wiki/DARPA
