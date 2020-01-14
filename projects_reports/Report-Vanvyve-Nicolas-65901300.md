# LINGI2401 : Open Source Contribution

### *ihatemoney* : Add a way to import previously exported json data


> **Author**: Nicolas Vanvyve<br>
> **NOMA**: 6590-1300

Issue : [#417 Add a way to import previously exported json data](https://github.com/spiral-project/ihatemoney/issues/417)  
Pull request : [#518 Import previously exported json data](https://github.com/spiral-project/ihatemoney/pull/518)

## Project

*ihatemoney* is a website that allows you to make the account between friends, a bit like Tricount.
Once a project is created by the "manager", it is shared with others and everyone can add the different expenses.
You can see a list of all the expenses ( bills ) that have been added to the project.  There is also a Settle tab that automatically calculates who has to pay back how much to whom. In the Statistics tab, you can see how much each person has paid and how much each person has spent, so you can see the difference. Finally, there is an Settings tab that allows you to edit the project and download the project data. It is possible to export the settles as JSON or CSV but you can also download the complete list of bills, also as JSON or CSV, so you can have a complete history of the project.

The project is written in Python/HTML and the database is in SQL.

## Contribution

I chose this project because I found it interesting even though I'm a Tricount user myself. Also, I mastered, according to me, the python well enough to start the adventure. The more difficult part was announced from the beginning and concerned all the HTML part.

I looked at the issues and I found a tagged "good first issue" that seemed not too complicated and above all that would bring a real plus.

This issue is the [#417](https://github.com/spiral-project/ihatemoney/issues/417) : Add a way to import previously exported json data.

Indeed, as I explained in the previous section, it's possible to export the data in JSON to save the project, but it is impossible to reimport them. The only solution is to dive into JSON and transcribe all the data by hand.

So my contribution was as follows:
* Create a field for importing a file
* Read the JSON file and extract the data from it.
* Compare the data with the data already present in the project and add the missing data to the database.

## Road map

* After I managed to launch the project locally and take a look at the code, I was asked on the issue, how they saw the data import. Should we add this to an existing project or create a new one?

* Since several people had expressed interest, the project maintainer, who had opened the issue, proposed that the first person who expressed interest should work on it. I accepted the decision and looked into the possibility of finding another contribution to the same project. But due to the lack of action, he started the conversation again and I started working on the code.

* I first tried to add a form to import a JSON in the options section of the page but, my rather weak mastery of HTML not helping, I remained without result. I managed to create a new tab with a small form to do what I had to do, so I limited to that and concentrated on the python part and the JSON processing.

* Once I was able to read the json file, extract the data. I also had to extract the one that was already in the project in order not to add a user or an bill already present. After that, I had a user list and an bill list to add to the project.

* Since the additions to the database are only done via forms that the user fills in, I didn't know how to do it without going through the same system. The only thing I knew was that I had to add the users before the bill, so I wouldn't end up with a bill for a non-existing user. So to not waste time I asked if he had a solution to my problem.

* I got a reply pretty quickly, and he gave me a sample code for the users, and said it should be the same for the bills.

* It worked perfectly for the users but it was impossible to do the same for the invoices. So I exposed my problem, and another contributor suggested I make a kind of fake form to make it look like someone was typing them in by hand.

* Once that was done I made a first [pull request](https://github.com/spiral-project/ihatemoney/pull/518) which was refused by default because I had not used the code reformatting tool properly. After modification, another maintainer asked me to write tests for the function I had written, which was asked for in the contribution instructions and which I had misread. So I did that and resubmitted a pull request.

* My tests were not complete, I checked that for each imported bill was exactly the same as the one in the json, but I did not check the number of imported bills. This was indeed a problem because I realized that my test was not able to import the file. Which was frustrating because during the real tests, everything worked fine. So I slightly modified my code to make a test that worked. I also modified my code to stop creating temporary files.

* Two maintainers looked at my pull request, the first one approved my changes after the modifications explained above, the second one asked me to change one or two more things in the file upload in order not to consume memory for nothing. At this point I thought of a check of the json content, so that the user can't import anything and cause a crash. I also implemented the corresponding test.

* After that my pull request has been merged

## What I've learned:

* The work you imagine is far below what you'll have to do in the end.
* ***At least*** half of the work is represented by interaction, negotiation etc. and not by code.
* You have to pay more attention to the contribution guidelines. Typically, in my case, test implementation and code formatting.
* Some improvements are not listed in the issues but just mentioned by *FIXMEs* in the code.
