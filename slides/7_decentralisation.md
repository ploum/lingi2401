# LINGI 2401 : Open Source strategy for software development

Lionel Dricot - lionel.dricot@uclouvain.be


---

# Elevator pitch
- What is the project. Why is it good. Why do you use it?
- Why did you choose to contribute to it?
- What's your contribution? What's your story?
- Shorter is better!
- Give enough to generate curiosity but not too much to not kill it.

---

# Is decentralisation a good thing?

---

# What should be decentralised and what should not?


---

# What is interoperability?


---

# Interoperability:
 In time and in space

(example :  Microsoft Works)


---

# Interoperability:
 - Hardware
 - Operating System
 - Client
 - Language



---

*"Be liberal in what you accept, conservative in what you send."* 
(Jon Postel)

https://en.wikipedia.org/wiki/Robustness_principle

---


# Interoperability through reverse-engineering


---


*"Interoperability implies Open standards"*
 (Wikipedia)


---


# Different level of interoperability:

1. Active obfuscation
2. Closed source implementation without obfuscation
3. Documentation of the format
4. Documentation and open source reference implementation
5. A diverse group working to standardise the format.
6. A standard recognised by a standardisation organisation  (ISO, OASIS, …)


---

![](../images/winmail.jpg)

---


# Standardisation is great but usage is more important

???

This is often forgotten in the Open Source community
https://ploum.net/winmail-dat-syndrome/


---

# De-facto standard

either non-standardised format (word 97) or bad implementation of an existing standard (Outlook emails)

---

# Best standards does not always win

???

So don't try to build the best standard. 

---
background-image: url(https://github.com/ploum/lingi2401/raw/master/images/betamax.jpg)

# VHS vs Betamax

???
https://en.wikipedia.org/wiki/Videotape_format_war

---

![image](https://github.com/ploum/lingi2401/raw/master/images/standards.png)

???
Image Caption : Fortunately, the charging one has been solved now that we've all standardized on mini-USB. Or is it micro-USB? Shit.

https://xkcd.com/927/


---

# Open Source & Interoperability

- Open source cannot work with closed format because implementing them is already a form of documentation. 
- Open source is good for interoperability. 
- Interoperability needs open source, at least for a reference implementation.

---


# Some standards:

???
Let's find a few standard together

---

# What is decentralisation?

???

Let's take the time to design a decentralised system.

---

*"Decentralized system: A distributed system in which multiple authorities control different components and no single authority is fully trusted by all others."*

(Carmela Troncoso, Marios Isaakidis, George Danezis, Harry Halpin 2017)

???
  https://arxiv.org/abs/1704.08065


---
background-image: url(https://github.com/ploum/lingi2401/raw/master/images/decentralised.png)

# Centralised, federated, distributed

???

There's no clear consensus about the term "decentralised" which was initially used (baran 64) to describe what is now called "federated". Now, decentralised seems mostly used as an umbrella term for both federated and distributed.

http://networkcultures.org/unlikeus/resources/articles/what-is-a-federated-network/
Baran 64 : www.rand.org/content/dam/rand/pubs/research_memoranda/2006/RM3764.pdf


---

# Decentralisation is a permanently evolving consensus
The consensus is called "protocol"

---

# Why is decentralisation hard?


---

# Why is decentralisation hard?

- because you cannot trust other members of the network.
- because you have to agree with them on the protocol

???
Which means you have to agree on the design

---

# Decentralisation usually means a standardised protocol

---

# How to break a decentralised network
- Disagree with the protocol -> fork
- Pretend to agree but do not respect the protocol
- Respect the protocol but abuse the system (spam)

---

# Benefits of decentralisation?

---


# Benefits of decentralisation?

1. Better resilience of the overal system (survivability)
2. Privacy and security (distributed trust)

---

# Problems of decentralisation?

---

# Problems of decentralisation

1. Agreements on protocol changes
2. Upgrading nodes of the network
3. Spam
4. Complexity (implementation)
5. Complexity (UX)
6. Social acceptance of problems
7. Natural tendency to recentralise (everyone on the same instance)


???
5 is usually overlooked by most technical programmers.
6 is completely forgotten in the free software community (see winmail.dat syndrom)
7 is not understood by free software activists.

---

# The choice problem

- Free software: you should have the choice
- Normal person: but if I have the choice, I could be wrong



---

# Costs vs benefits

???
That's not a lot of advantages. That's make decentralisation even harder. But maybe those advantages worth it.

---


*"Nobody was ever fired for choosing Microsoft"*

---

*"Nobody cares about survivability of others. If it fails for you, you want to be sure it fails for the others too."*

---


Most decentralised network still have centralised parts (like routes, directories (see XMPP))


---

# Example 1: Mail
- spam problem (and no clear line between "true spam" and "valid mails")
- standard problem (winmail.dat)
- not privacy oriented
- no identity mechanism
- non-evolution of the protocol

---

# Example 2: XMPP
- Slow evolution (example of XEP-0084)
- Stabilty of servers
- Confusing UX (Jabber address vs email addresses)
- The great 2013 Google divide

???
It took XMPP years to have user avatars (XEP-0084) and, worst, the most popular XMPP client at the time (Psi) was using something else.

---

# Example 3: Mastodon
- Tendency to centralisation of a few servers
- Already some spam servers
- Hard to mention users from other servers (but good UX)
- Hard to explain that address are @ploum@mamot.fr and you have to choose a server
- Focus on being tolerant but how could it ever be enforced?

???
Mastodon is still young and is a very interesting project to follow.

---

# Example 4: Diaspora
- Developed as a crowdfunded decentralised Facebook
- Development mostly stalled


---


# Some decentralised network widely used:
- Emails
- WWW  (was not always the case, example AOL)
- SMS

and… that's mostly it. Anything else?

---

# Recentralisation

- Emails is now mainly centralised to Gmail, Outlook (hotmail) and Yahoo.
- WWW is now mainly centralised to Google, Facebook, Amazon S3.
- SMS?

???

Example of OVH failing.
SMS is also quite centralised.

---

# The future…

Blockchain

---

…but even bitcoin mining is quite centralised those days








---
# Should we work on decentralisation ?
- Why?
- How?




