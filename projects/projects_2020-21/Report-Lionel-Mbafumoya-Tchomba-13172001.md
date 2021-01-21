# Open source contribution project

**Author:** Lionel Mbafumoya Tchomba

**Noma:** 13172001

**Academic year:** 2020-2021

## Summary

- **Project:** [PrimeNG](https://github.com/primefaces/primeng/)
- **Issue:** [Autocomplete: enable multiple selection at once #4016](https://github.com/primefaces/primeng/issues/4016)
- **Pull request:**: 
1. [ #4016 Autocomplete multiple selection #4017](https://github.com/primefaces/primeng/pull/4017)
2. [Autocomplete: enable multiple selection at once #9776](https://github.com/primefaces/primeng/pull/9776)

## Selection of the project

In a professional Angular project designed for a bank. We had, as the front-end team, to select an open source library for our form component. We ended up selecting PrimeNG for the richness of the available components and the notorious users of the library.

Among the components provided by the library, the autocomplete is used to provide suggestions to the user from which he can choose a single or multiple suggestions (See [PrimeNG | AutoComplete](https://www.primefaces.org/primeng/showcase/#/autocomplete)).

I decided to reuse this project since it already had history and could provide another story to tell about open-source projects. Especially since the proposition was rejected and the demand for the feature has grown overtime.

## Contribution to the project

My contribution was mainly to outline a UX issue defined in the section above.

### Issue

Link: [Autocomplete: enable multiple selection at once #4016](https://github.com/primefaces/primeng/issues/4016)

#### Description of the issue

The issue was described in the following terms in the feature request created on the 22nd of September 2017: 
> Given an autocomplete with the multiple attribute set to true, the values have to be selected one at the time with the panel closing each time.

The proposed solution to the issue was:
> It would useful to be able to select multiple values at once similar to the MultiSelect behavior.

Furthermore, additional instructions were provided to reproduce the issue:
1. Go to https://www.primefaces.org/primeng/#/autocomplete
2. Type the letters 'Bel' and try to add 'Belgium' and 'Belarus' at the same time in the Multiple autocomplete component.

The original issue was reported with the following configuration:
- Angular version: 4.0.2
- PrimeNG version: 4.2.1
- Browser: Chrome 60.0.3112.113

But it is still present with the latest versions of those technologies. 

#### Motivation of the proposed solution

The use case for changing the behavior was expressed as follow:

> The goal of an autocomplete that selects multiple values is to not only have real-time suggestions but also to be able to select as many values as needed (Similar to the MultiSelect component).
> It is counter-intuitive to have to type similar queries when they share common letters.

#### Conclusion

The feature request was closed on the 3rd of October 2017. The reason cited was the lack of support for the demand by the author.

### Pull requests to implement the solution

#### First pull request

Link: [ #4016 Autocomplete multiple selection #4017](https://github.com/primefaces/primeng/pull/4017)

The following day, after the creation of the feature request, on the 23rd of September 2017, a contributor (username: **Sumragen**, fullname: Hennadii Varava) proposed a pull request. I saw it as a vindication of the relevance of my proposal.

The solution was simple: if the user clicks on an item of the dropdown and multiple selection is enabled, do not close the dropdown. It was exactly what I proposed and needed.

Unfortunately, the request was closed by the owner of the project on the 3rd of October 2017. He cited the lack of widespread support for the feature.

#### Second pull request

Link: [Autocomplete: enable multiple selection at once #9776](https://github.com/primefaces/primeng/pull/9776)

On the 17th of January 2021, after multiple demands to implement the feature (even though it was closed by the author citing lack of support) with 15 likes and 12 comments, I decided to create an updated pull request. The update is very similar to the changes proposed by the first PR, but it was adapted to the new structure of the component which underwent several changes to adapt to new features proposed by Angular and to improve overall visual performances.

Moreover, the author implemented tests to ensure that everything worked as intented after potential changes. This was useful to boost my confidence in the implementation of the solution since no test failed after my changes.

The second PR has not been reviewed yet but I am hoping that with a higher demand for the feature, it will be accepted this time.

## What I’ve learned

The main thing I have learned are:

### Contributing to familiar projects is easier

The fact that I used the library and discussed it daily gave me relevant suggestions to the author. It was rooted in experience and this was shown by the support gathered from the community.

### Despite the relevance of a proposition, it will not always be integrated

When my feature request was introduced, I was convinced of its relevance. It was compounded by the fact that another contributor was willing to implement my solution the following day. Unfortunately, the refusal of the author to integrate my idea by citing the lack of support made me realise that breaking something that clearly works requires time and support from the community since people migh like how it works as-is.

### Contributing can come in many shapes and forms

You do not always have to implement the solution to the issue that you propose, sometimes the community has a solution and outlining the issue can encourage someone else to propose a solution.

### Change can be slow

To gather the support of the community, it took almost 3 years to gather 15 likes and 12 comments demanding the implementation of my feature request.

### Maintaining a local change can be costly

As a solution to deliver a feature to the client, the team in my company decided to implement the feature by ourselves on top of the PrimeNG component. As I was tasked to implement the change, it was a nightmare to maintain. Angular was instable and changing all the time and PrimeNG was also having a life on its own. Breaking changes were frequent and I even received phone calls to provide some insight when I was no longer working on that particular project.

Today, I would do it differently by gathering community support faster and pushing for change on the project level by making my case more forcefully (I basically gave up when I received a no).

## Conclusion

The change has not yet been accepted or merged to date. In the meantime, the project that the bank worked on was shipped to the client with a custom fix. But I am waiting for my pull request to be looked at by the author of the project. Since I really believe in the relevance of the feature request, I am planning to lobby the users that showed interest in the feature to support the latest PR.

This experience, especially the fact that I had to maintain a local change on my own, instead of relying on the community, made me realise how important contributing to open-source projects can be. Furthermore, if we had to create a comparable library from scratch, we would never have been able to finish the project on time and as a consequence within budget.

# LINGI2401 Exam: Banking and open-source

## Background

The banking sector overwent a major shift in the last decade. With the rise of financial startups and technologies, traditional banking instutions, which were for a long time shielded by strict regulations (barrier to entry), suddently started to face competition from new players in the newly created fintech sector which were raising considerable amounts of money.

Keeping up with those new players required new approaches and paradigms. The market demanded innovation at a quicker pace.

## Resistance

Banks were resistant to adopt open-source technologies that they saw as a security risk factor: the openness and the scrutiny that comes with it were feared. That feared was fueled that the belief that if hackers were able to see the code, would it not be easier for them to hack it.

Furthermore, banks believed that protecting their intellectual property (IP) was a competitive advantage. The potential legal risks were also high as licenses were not very well understood and improper use was feared.

Also, they believed that the clients cherished the human interaction provided in their physical branch.

## Drivers of change

The rise of financial services such as PayPal, Revolut, N26 and cryptocurrencies such as Bitcoin and Ethereum provided the competition that was needed by the banking sector to reconsider their approach. The innovation and new services proposed by those companies were existantial threats to the more established financial institutions.

Cryptocurrencies proved that secured transactions could be carried over an open-source ledger while using cryptography to protect user data. Moreover, the high adoption rate provided a rebutal to the long held belief that customers would never trust open-source technology.

After the financial crisis of 2008, new regulations were put in place to mitigate the risks that a particular default can pose. Additionnally, new regulations such as PSD2 (interoperability of payment framework, payment reglementation), GDPR (framework for user data protection and privacy) and MiFID 2 (legal framework for financial instruments) made banks reconsider their approach since new innovation and automation was needed at a faster pace. It became costly to do it alone.

## Digital transformation

Quicky, all the banking sector had two words in its mind: Digital transformation. But how? The sector was heavily under staffed and constantly coming up with new innovation was costly. Additionnally, the supply of Software Engineers was limited.

The sector had to renew their interest at open-source. Big communities of developer could provide the multiple eyes needed to mitigate the security risks, innovate at a faster pace, provide virtually free components to reduce the costs associated with hiring staff and maintaining proprietary systems. Furthermore, new well-defined license such as MIT and Apache 2.0 provided stable and well-understood frameworks for legal concerns.

However, the use of open-source could only be cost-effective if clear standards were implemented.

A need that arose from the regulations to evaluate risks is the implementation of AI tools to determine a risk score from each individual client, anti-money laundering technologies.

## Move to open-source

The following benefits of the use of open-source are:
**Lower costs**: eliminate costs from software vendors and hiring staff.
**Reduce time-to-market**: reduce development time by integrating existing modules.
**Easily customizable**: provide the mean benefits between buying a proprietary solution and developing one in-house.
**No vendor lock-in**: not bound to any vendor.
**Lower learning curve for new joiners**: a community project is usually on the based on the best practices.

The benefits of contributing to open-source have been identified as:
**Good for corporate image** by giving back to the community.
**Transparency**: the code can be reviewed by anyone.
**Easier hiring of resources**: attracting and identifying resources can be made easier.
**Cultural exchange**: promote collaboration between different communities.
**Gain from testing and extensions** built by outside contributors.
**Facilitates collaboration between different banks** on shared concerns like KYC (Know Your Customer) and AML (Anti-Money Laundering)

The potential inconvenients are:
**Contractual and legal**: keeping up with the various licenses.
**Support**: some open-source project lack the community support expected by large banks.
**Compliance and security**: open-source projects that are not yet mature can pose serious security risks.
**Give away competitive advantage**: banks must identify features that are commodity from the ones that offer a competitive advantage.
**Brand risk**: the fear that open-source might cheapen the brand.

## Popular open-source entities and projects

* **FINOS** (Fintech Open Source Foundation) was created in 2014 to provide an independent setting to deliver software and standards that address common industry challenges and drive innovation. Link: [The Fintech Open Source Foundation (www.finos.org)]. Some of the financial institutions that are collaborating with the foundation are JP Morgan Chase, Morgan Stanley, Citi, Goldman Sachs, UBS, RBC (Royal Bank of Canada), Capital One, HSBC, BNY Mellon, Well Fargo, Deutsche Bank.

* **JP Morgan Chase**, the biggest bank in the world by market capitalisation, has released several open-source projects, Quorum is the most popular. Quorum is an Ethereum-based distributed ledger protocol with transaction/contract privacy and new consensus mechanisms. Quorum has been published under the GNU Lesser General Public License v3.0.

* **Capital One**, one of the biggest credit card bank in the US has made the commitment to make open-source the core element of its digital transformation journey.

* **Goldman Sachs** has published its Alloy algorithm which was proprietary until then. Alloy lets you design, build, and publish data pipelines. It was notably standartised by FINOS to decouple the algorithm and Goldman Sachs under the Apache License 2.0.

* In Europe, **Deutsche Bank** contributed to multiple open-source projects. Notably Plexus Interop (from its electronic trading platform Autobahn) or Waltz (IT estate management). Both projects were published by FINOS under the under the Apache License 2.0.

## Conclusion

The big shift of paradigm from proprietary software to open-source in one of the most conservative sectors is a testament to how important the approach is and will be in the future of innovation in the technology sector.

## References

* [Banks are finally embracing the Open Source movement]
* [Why banking is just now embracing open source technology]
* [The Best 8 Free and Open Source Banking Software Solutions]
* [quorum]
* [Goldman Sachs Open Sources Data Modeling]
* [Fintech Open Source Foundation]
