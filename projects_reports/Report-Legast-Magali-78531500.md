#LINGI2401: Open Source contribution project - Tomorrow app

Author: Magali Legast
Noma: 78531500
Date: 15 January 2020
Date of update: 19 janvier 2020 (Addition of update section, no other change)


#Introduction

    This report presents the contribution I have made to the project "Tomorrow app". It is an application that calculates the climate impact of the choices we make by connecting to other apps and services we already use. The idea is to allow the user to be more aware of its carbon footprint very easily since all the necessary information is collected directly through the other applications and the user needs only to put minimal effort into it.

    The application is currently under development and a beta test version has been released. The development is managed by a tech startup based in Denmark. As they develop the app as their job, there are very active and usually pretty responsive to messages and questions. They try to make it easy for new contributors to join the project, for example by opening a large number of issues with representative labels. The presence of "Good first issue" labels and the responsiveness of the team were important factors in my choice of project and contribution, as well as the meaningful impact this app will hopefully have.
    
    I chose to tackle a recently opened issue that was labeled as "Good first issue" and that hadn't received any response yet. The goal of the issue was to improve the carbon model for the impact of hotel stays. There was already a model that gave the carbon equivalent impact of hotel stays according to the hotel class, but the data for that model were coming from only one country. I was asked to improve that by adding a factor per country and was provided with a list of carbon equivalent values for different countries.


#Development of solution

    In order to create a better model, I first had to analyze the different data available and find the best way to use them. This has been the most challenging part of the project. My goal was to provide the highest level of granularity as possible while avoiding flawed extrapolations leading to unreliable results.
    
    The different sets of data available were a list of carbon equivalent values for different hotel classes in Switzerland and another list of values for a one night hotel stay per room for different countries. There was also a website referencing data for different countries, giving lower and higher quartile values and some values per hotel class. I originally wanted to use those data to derive factors according to country or hotel categories that would allow to compute values both depending on the country and the hotel class. However, the values provided by the website were based on too small samples and very scares for hotel classes, so they seemed too biased to be used. We thus only had reliable data for different hotel classes for Switzerland, and deriving a coefficient for hotel classes based on data from only one country would have lead to unreliable results.
    
    After this evaluation of the data, I reached the conclusion that it was best to make a new model depending only on countries instead of mixing countries and hotel classes. That new model was still also going to be more precise than the one based solely on hotel classes since it offered more granularity (48 values vs 4) and a wider range of values (from 6,9 to 142,2 vs 11,6 to 33,1). I presented my conclusions in the comments of the issue and my suggestion of the new model was accepted.


#Implementation of solution
   
    Once I had sorted out the best way to use the data, the implementation of the model in itself was not very complex. It happened in two stages.
    
    I first produced an implementation that was majorly based on the structure of the existing one, using one variable per country and returning the corresponding value using a switch case statement. With the encouragement of the author of the issue, I submitted a pull request with this version of the model. It represented 3 commits and 225 lines of code covering 48 distinct places.

    When my pull request was reviewed, I was asked to make major changes to it. The reviewer wanted the countries to be stored in one object instead of different variables and to be represented by the official ISO2 code (two letters code for countries and territorial areas). This required me to completely change the structure of my code. In the process of implementing that new version of the model, I started by creating a first draft with a few countries so I could validate the structure of my code with the reviewer to avoid having to make major changes a second time. Facing his lack of response, I went ahead and completed the rest of the model. As of today, the pull request is pending its second review.

    That new version of the model involved 6 more commits and 882 lines of code (as of this writing), but it is more standard than the first one and it will be easier to maintain it and make it evolve with new needs. Indeed, as the countries object contains all the existing ISO2 code, it can be used to store other country specific information without needing any adaptation, which is likely to be useful in the future.


#Possible improvement of the model

    Currently, the model provides the carbon equivalent of a one night stay for one room in a hotel. For 77 out of the 249 areas referenced by an ISO2 code, the value provided is specific for that area according to the data set considered. For the other areas, a default value corresponding to the median of the known values is returned.

    An obvious improvement would be to complete the data of the model with other data sets in order to cover a wider range of places. Making such an addition to the model would be extremely simple since it would require to only add a new value for already encoded places. If no additional data can be found, different default values instead of a unique one could be computed, for example a default value per continent.
    
    It would also be interesting to add precision to the model by adding smaller area delimitation to it, for example major cities or different provinces within a country. This can also be done rather easily by adding an "area" key to the countries in order to hold different areas and the corresponding carbon equivalent values. In fact, this is already implemented for the code "UK" since a specific value for London was provided in the data set.
    
    Another way to add more granularity would be to consider the number of people staying together. Indeed, the values given correspond to one room and not one person. Implementing this would require a new variable for the number of people, then a factor could be derived from it and applied to the values before they are returned. The functions and arguments have been designed in such a way that adding a new variable as such would require very little change and have no impact on the functions parameters.


#Conclusion
    
    I had already been regularly working on an Open Source project for the past year and a half, but this contribution is my first one to a preexisting project with an already established community. It has lead me to have different interactions, including interesting feedback from the creator of the project and well thought-out suggestions from my part that were received positively. Other times, I also had to manage a lack of response. Overall, I think I found a good equilibrium between asking for information and confirmation of my correct work process, and going ahead without waiting unnecessarily for answers.

    What I have provided to the project is a functional model for the carbon footprint of a one night stay in a hotel, as well as an easy way to store country related information and ideas on the possible ways to further improve the model I created. I think it is a robust code that will be useful now and possibly in future development. I am satisfied with the work I have accomplished, both on the development (analyses of data) and implementation of the model.

    On the other hand, this project has brought me confidence on approaching an Open Source community and discovering new projects in order to contribute to them, including in the use of the Git tools to do so. It also gave me a new perspective on the way other and wider spread communities can work and on what it is like to be an outsider looking to help in a project with no prior information about it. Both aspects will help me in my future Open Source contributions and in making the current and future projects I participate in more welcoming of new contributors.


#Update after finalization of contribution
    
    After this report was submitted, my pull request received more reviews, I made some changes to the code and the pull request was merged into the project.
    
    The second worth-mentioning review I received requested changes such as deleting the key with the name of the countries and removing the countries for which no value was known. This corresponds to erasing some of my work, but also to making the document relevant only to this precise hotel model with the current values, while I had aimed at a general purpose file that could be used for several models and that could evolve as neatly as possible with minimal work. So I explained the different reasons and advantages I saw in the way I had implemented the model, which convinced the reviewer that a general file for country related information with all country codes already present was useful. However, I deleted all the name variables of the countries since the use they could have was too low compared to the size they were taking. After some other minor changes, my contribution was merged.
    
    My contribution now represents 11 commits and 459 lines of code. It is very different than the first version and doesn't correspond to the original idea of the author of the issue because the different interactions I had allowed me to produce something better than that. Thanks to the utilization of standardize codes and the deletion of the non-fundamental name key, the model is more convenient to use and lighter than what I would have done on my own. Thanks to my concern for facilitating future improvements and diverse uses, it serves more purposes and will be easier to modify than what the main reviewer of my pull request would have probably done. I think this is a good example of the way Open Source helps improve the quality of software by allowing different people to exchange their ideas and work together towards a better solution.


- Note: It is possible that I keep on contributing to this project by improving the model before the end of the exam session, but I will not consider future contributions to be part of the requirement for this project and thus I will not make any new update of this report.


#Useful links
1. Project repository:
    - https://github.com/tmrowco/tmrowapp-contrib
2. Issue tackled:
    - https://github.com/tmrowco/tmrowapp-contrib/issues/247
3. Pull request:
    - https://github.com/tmrowco/tmrowapp-contrib/pull/266
4. Data available:
    - https://shop.southpolecarbon.com/uploads/assets/en/_Overnight%20Stays.pdf (Data per hotel class for Switzerland)
    - https://docs.google.com/spreadsheets/d/1f1j9EeVn9czOZBJKLXvgPwnmldakxuJ7/edit#gid=1584958883 (Data per countries)
    - https://www.hotelfootprints.org/ (website with different data)
    - https://docs.google.com/spreadsheets/d/1IgtL17Z4x7yxovUubWXyWzEeywIYX21gXz8OUk63SY4/edit#gid=0 (Data from the above website)
5. Other Open Source project I contribute to:
    - https://github.com/OpenWeek/app-for-a-KAP
