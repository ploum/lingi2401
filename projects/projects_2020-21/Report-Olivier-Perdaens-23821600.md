# Open Source Project
___
***Author***: Olivier Perdaens \
***NOMA***: 23821600 \
***DATE***: 2020 \
***Open Source Project***: [NextCloud](https://github.com/nextcloud/server)
___

## Project
### Domoticz
At first, my choice was to work on the [Domoticz](https://github.com/domoticz/domoticz) open source project, since I use it for personal project home. \
I spotted a bug in the configuration of the "AccuWeather" daemon, but after setting the developpement environement up, I realised that this bug was already fixed, but simply the fix was still not merged to the stable version of the software. I had to find another project ...

### NextCloud
It took me a while to find a project in which I'm interested in since I was looking for a project useful to me and where "simple" issues where "available".

NextCloud is an open source plateforme to handle file storage on a dedicated host (raspberry pi, own server, ...). The software propose a lot of functionalities such as rights management, shared folder, third party applications, ...

#### Issue
After read lot of issues, I found [this issue](https://github.com/nextcloud/server/issues/23849). The explanation of the issue let me understand that it was a small issue in the css configuration and I'm quite confortable with it since I create website in my free-time.

Some icons in the navigation-bar of the setting's page were vanishing when the "nav-item" text overflows.

#### Submitting my contribution
After modifying slightly the source code (3 lines changed), I introduced a [pull request](https://github.com/nextcloud/server/pull/24378). The modifications I made were solving the issue but changes slightly the visual aspect of the setting's navigation-bar.

#### Reviews of my contribution
1. The little change in the visual aspect of the navigation-bar was mentioned by one of the reviewers of my pull request.
So I shortly explained why I had to make this changes and promise to dig deeper to keep the fix of the icon's problem and still keep the initial visual aspect.
2. Some hours later, I found a way to fix the initial issue without touching to the initial visual alignement of the navigation column by creating a new css class in the main css file of the projet.
3. Some days later, a third review from another developper that "refuse" my fix since he found that the fix was too general and that I had to play with html existing classes instead of creating a class to solve this specific issue.

#### What I'll remember of this first expercience in Open Source Project
The main thing I'll remember of this project is the fact that in this kind of project where many developper's are working on, it's not all about fixing an issue or developing a feature. You have to do it in the same "idea" that the other developers and 'fit' into what they are expecting while following "rules" to keep the source code sustainable and maintainable.

#### To Be continue
My pull request is still not merged (since it has been rejected by the third review). I'll try to keep working on this since I think I'm not so far from a suitable solution.
[Update] - After working on a new solution that would fit the requirements of the main developers of the project, I proposed a new way to fix the bug at the end of december. Unfortunatly, I'm still waiting for a review to have my PR merged.

___

## Examen Oral Plan

### NextCloud
#### Intro
- Why I choose this Project
- Self-hosted, open-source file system
- License AGPL v3
- Fonder of NextCloud is Frank Karlischeck

#### History
- First, OwnCloud (2010)
- 2016, Frank left Owncloud and forked the project to create Nextcloud.
  - Community was left behind the company financial interest
  - Balance between community and company has tipped
  - Decisions were blocked by investors, who were afraid of new features unknown, that dropbox didn’t implement at this time
  - Many core developers left with the CEO to create NextCloud
-	This is not a new phenomenon, OpenOffice -> Libre Office, Nokia -> Jolla, …
(Linus Torvalds: “Forks are the strength of the open-source world”)
-	With creation of NextCloud, Frank showed that it was possible the create a viable business model without being held hostage by investors since he and the co-founders of NextCloud are funding the project themselves.

#### Business Model
-	NextCloud chooses to follow an open and transparent development process and focus on the needs of users and customers.
-	Role inside de company (developers) are mixed. Testers are users, developers, … No pre-defined role for testing, developing, responding to users, …
-	Product is an open-source and free end product
-	Strong work on security and privacy of our data (becomes more and more relevant) -> product propose to self-host your data, in your “data center” managed by you. (to assure and proof safety to the users, Nextcloud payed for security audit from other companies – NCC Group - to get “certificates” about the security of their solution)
-	Entire free unlimited software! The company only propose a payed industry version, but the added value is only a professional support.

#### NextCloud & Governments
-	Multiple European Governments are now preparing or have already tried to change their data management and storage platform for Nextcloud’s solutions.
  - French government has evaluated and is now preparing the migration of a production ready Nextcloud solution for the French administration (±300.000 users)
  - German government has advised its citizen to use nextcloud solution on German hosting provider (server physically in Germany) and has deploy its own solution on premise. This solution is now used by the ±300.000 employees of the government and is not accessible from the outside since, like for the French government, these hosting are kept on government’s private network. All connection / work has to be done on premise and is a key element for the security of the data.
  - Swedish government is working on a solution (like Nextcloud) to centralize its data, “protecting” them from the control of foreign countries over their data.
- More and more concern (in a political way) of cloud solutions from large centralized foreign firms, owning sensitive and necessary data for the good functioning of our political systems. Governments have to trust blindly (only based on a few – now growing – rules, changing from a country to another) – example July 2019, when France propose a special tax for huge foreign tech companies making money with French citizen. US response was to propose also to make France pay much for all tech services that US provides them (storage, cloud hosting, trades, …)
-	Open source to prevent from ‘only giving trust’ to external cloud storage entity -> prefer open source, to know how data are processed and self-hosting to keep hands on your data
