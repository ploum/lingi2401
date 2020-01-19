# Open Source Contribution report - LINGI2401

Author : Maxime Franco

Date : January 2020

NOMA : 42741700

## Project Presentation

My project was the [swagger-check](https://github.com/adimian/swagger-check) project. 
It's a tool that allows to check if your OpenAPI follows correctly the rules described into your API's schema. The tool will generate random input but consistent with your schema and will check how your OpenAPI will react on it.
This project is a fork of the [swagger-conformance](https://github.com/olipratt/swagger-conformance) where an authentification option was missing.


## My task
I have chosen to do 2 issues, because the first was very small but taught me how the project was made.
The first issue, ["good first issue"](https://github.com/adimian/swagger-check/issues/3), was to indicate if the swagger was running in authenticated mode or in a basic mode. That was a simple if/else condition on a boolean. 
The second issue was too an ["good first issue"](https://github.com/adimian/swagger-check/issues/4). The goal of this issue was to give a report after the execution of the test because reading one by one tests with the input data and the result, is not very useful. So I use a log file to save relevant information during the execution, because it's hard to communicate between hypothesis, pyswagger, and the program. Then after the execution, the program read the log file and print the relevant information. 

### Encountered difficulties
The big problem I get with the first contribution, was to understand why my first ["pull request"](https://github.com/adimian/swagger-check/pull/6) failed the travis test while I have not changed the behavior of the swagger. The problem was an new update of hypothesis on the travis server that made the test inconsistent. I changed the requirements-dev.txt to force travis to use a good configuration and the tests succeded.
To find the error, i must have read all the log file of the travis from the previous pull request and mine to find what has changed between the two pull request.
For the second issue, as my first pull request wasn't accepted yet. I decide to create an other branch and push my work on this branch to open two differents pull request on the github : ["pull request"](https://github.com/adimian/swagger-check/pull/7).

## Conclusion
I find this project useful because it learnt me how to contribute on a project from someone else.
Firstly, the project shows how to write code that could be read and understood by everyone and the structure we have to follow.
Secondly, when I encountered the problem, they give me way to understand the source of the problem but without correcting it. At the first time, I found the answer very cold. But you learn so much more by searching from yourself than when someone else do it.
Finally, I found this project motivating, because the contribution can be useful for people. And if the pull request is accepted, it's a pledge of a good work.
