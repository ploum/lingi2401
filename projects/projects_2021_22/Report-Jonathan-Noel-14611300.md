# Open Source Contribution Project

Author: Jonathan Noël

NOMA: 14611300

Year: 2021

Selected project: [~~Ansible~~](https://github.com/ansible/ansible) [Matomo](https://github.com/matomo-org/matomo)

# Why this project ? <span style='font-size:8pt;'>*(2021/09/19)*</span>

## ~~Ansible~~ <span style='font-size:8pt;'>*Update 2021/11/14 - New project Matomo*</span>

~~According to [Ansible](https://github.com/ansible/ansible) Github repository README, Ansible is :~~

<cite>~~"Ansible is a radically simple IT automation system. It handles configuration management, application deployment, cloud provisioning, ad-hoc task execution, network automation, and multi-node orchestration. Ansible makes complex changes like zero-downtime rolling updates with load balancers easy.".~~ </cite>

~~A GPL-3.0 License is applied to this project.~~

## Matomo <span style='font-size:8pt;'>*2021/11/14*</span>

After many attempts to resolve issues on Ansible, I decided to go to another repository in which I am interested and which also contains many issues.

Matomo is a web solution - based on PHP, MySQL and angularJS in frontend - allowing activity analysis on a website. It is said to be a very good alternative to Google Analytics, and all in a Free / Libre context.

A GPL-3.0 License is applied to this project.

## ~~Motivation~~ <span style='font-size:8pt;'>*Ansible motivation*</span>

~~Python is a programming language that I find very interesting and practical on a daily basis. It was therefore logical that I headed for a project using this language.~~

~~I went to Github and started looking for this Python project that I would like to contribute to. In the search list, Ansible showed up and that's when I knew I needed to contribute.~~
~~Today, the automation of deployment and maintenance tasks are in full expansion and I find it important to contribute to these DevOps focused projects knowing that they represent, from my point of view, the near future of IT.~~

## Motivation <span style='font-size:8pt;'>*2021/11/14*</span>

I have always had a particular affinity with the world of web activity and performance analysis.
This project being an alternative version to Google Analytics - which I use daily - immediately appealed to me.
It is important today to keep an eye on these metrics in order to improve our websites on a daily basis and, therefore, the user experience.

Moreover, the programming languages present in this project are, for me, familiar languages.

# ~~Issue~~

[~~Issue #73410~~](https://github.com/ansible/ansible/issues/73410)

~~Adding an argument to vars_prompt component.~~
~~This enhancement allows you to automatically decide whether a value is truthy or falsy and return the associated bool value.~~
~~In addition, to go further in development, it would be good to adapt this functionality to various types of data.~~


# Issue Matomo <span style='font-size:8pt;'>*2021/11/14*</span>

[Issue #18162](https://github.com/matomo-org/matomo/issues/18162)

Tooltip not close when redirect to another page.

The issue regarding this bug concerns an information popup that does not act as desired in a specific case. In the software, it is possible to open an information popup when you click on the information icon present for each of the subcategories of the navigation bar. In normal operation, the popup disappears when changing the subcategory. The problem was that when clicking on a category (and not a subcategory), the popup did not disappear and remained frozen.

# Pull Request - Merged <span style='font-size:8pt;'>*2021/11/14*</span>

[Pull Request #18304](https://github.com/matomo-org/matomo/pull/18304)

To resolve this issue, I started by analyzing the behavior of the software and tracing the root of the problem. Then, after some code manipulation and good performance tests, the problem was solved and, from then on, I could offer my solution to the maintainers of the repository via a pull request.
The mainteners were very responsive and my pull request was approved and merged shortly after my proposal.