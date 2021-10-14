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

To set up a development environment before contributing to the project, I just [I just read the developer documentation](https://freshrss.github.io/FreshRSS/en/developers/02_First_steps.html) (it sets up a Docker container that runs a local instance of FreshRSS on http://localhost:8080). The next step is to understand how the source code is structured. There is almost no documentation to explain it (except [this file](https://github.com/FreshRSS/FreshRSS/blob/edge/docs/en/developers/03_Backend/05_Extensions.md), which gives insight about Minz library). Thus, an useful contribution to this project would be to populate it.