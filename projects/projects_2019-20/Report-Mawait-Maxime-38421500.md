# Open Source Contribution Project
*Author :* Maxime Mawait
*Date :* January 2020
*NOMA :* 38421500

## Research and selection of the project

Starting this project, I searched simply to do a fun project different from what we already did. As most of the projects on github in js are about node packages for servers or web use, I searched for a project in python first as I knew this is quite the most used language right now. 

I found a lot of interesting and popular projects but I choosed scapy because we already talked about it and used in it in the security class and I was quite curious on how it worked. Furthermore, it is quite linked to my master thesis, as the finality of it is to be used as plugins for quic and modify the use of that protocol.

Scapy is a python based interactive packed manipulation program and library. It can do a lot of classical and basic network tasks such as network discovery, tcpdump, traceroutes, ...

## Contribution

First, I checked in the repository readme for advices and tools about the project. I found that they wrote a file called `CONTRIBUTING.md` where they put advices on how to begin contributing on their project. That way, I learned the structure of their repository and how they acheived to make this project working in both python 2 and 3. 

Then, I searched in the issues for interesting features to do but either the issue was too complicated or either the issue was already taken care off. As they have a gitter server, I asked on it what I could do as a beginner contributer for their repository and they answered me to check an older issue (#399) where they put a lot of features to be done with the initial issue where the feature was requested or the bug found in order to give the background to contribute on it.

By searching this issue, I found an interesting feature to do thanks to my network background. I decided to impletement a basic tcp server able to answer to the tcp client already existing. By checking the original issue where this feature was requested (#2083), I knew the background and what the server should do. Then, I implemented it and did a pull request when I it was finished.

Now the pull request is still not merged but I hope that thanks to the owners feedbacks and reviews, it will finally be merged after a few improvements.