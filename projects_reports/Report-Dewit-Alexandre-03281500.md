# Open Source Contribution Project
*Author :* Alexandre Dewit

*Date :* November 2019  
*NOMA :* 0328-15-00

## Research and Selection of the Project

As a freelance developer for crafting hand made websites, I looked around projects that I like to use during the development. One of my favorite technology for the frontend part is [Vue.js](https://github.com/vuejs/vue) (a framework like Angular and React JS) so I added this project to the contributions table of the open source course. 
Unfortunately I was too ambitious to help this big community, I felt not competent enough to resolve an issue...

Back to the starting point, I looked for the same type of project but less complicated and always with libraries that I usually use. I fell on the [Vee Validate](https://github.com/logaretm/vee-validate) project that is built with Vue JS.
This project consists on validating components like form inputs and text areas on the front-end part (Template Driven Validation Framework for Vue.js).

## Contributions

I read the available issues on this repo and I found the [issue #2358](https://github.com/logaretm/vee-validate/issues/2358).
In short, there was a strange bug in the docs when navigating through some pages. [this snippet of validation](https://logaretm.github.io/vee-validate/guide/advanced-validation.html#cross-field-validation) was not working anymore by traversing specific pages and finally the page about [advanced validation](https://logaretm.github.io/vee-validate/guide/advanced-validation.html), so I tried investigating on this issue.

It appears that the bug was a problem of reference and initialization of data when navigating between pages. I proposed a [pull request](https://github.com/logaretm/vee-validate/pull/2468) to fix this issue and fortunately, the creator of this repo validated my changes and merged it into the project.

In addition of my interaction with the community, my contribution learned me how to use a github pages documentation with [Vuepress](https://github.com/vuejs/vuepress) and that it is possible to inject code into a markdown file to make samples of code (like it is the case in this repo).
