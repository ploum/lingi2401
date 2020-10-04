# Open Source Contribution Project

*Author :* Sébastien Kalbusch

*Date :* September 2020

*NOMA :* 22701600


## My motivation to follow a course on open source software

My main motivation to follow this course is to become a contributor to an open source software.
Through the years I have been an enthusiast user of free open source software.
Most of the time I ended up choosing them because they were free alternatives and because I could then use them very quickly.
After so many use I feel like I want to contribute to this system mostly because all of this was "given to me" for nothing in exchange.


## Research and Selection of the Project

### First attempt: GNU Octave

During my first year at the university the software MATLAB was required for a course.
At that time, I was told that GNU Octave, a free alternative, was available but it was not advised.
Still, I gave it a try and I was not disappointed.
I was so happy with it that I kept it for other courses as well.
This is the reason why GNU Octave is the project I am most interested in.

For a first contribution I wanted something small and easy, just to get started so I looked in their "bug page" and found a recent one that seemed just like that.
https://savannah.gnu.org/bugs/index.php?59103
I took a look at it and I shared my ideas on the matter, but the problem was more complicated that I thought and quickly I could not follow the conversation.
Unfortunately for me, the issue was solved in under a day and I was not the one who made that contribution.
I feel like I missed an opportunity because in the end they were happy with a small fix which was not what they initially started talking about.

For now, I still want to bring a contribution to the project, but maybe I should take my time and come back to it later.

### Second attempt: Erlang for Visual Studio Code

Recently I have been learning Erlang/OTP and I am using Visual Studio Code with an extension for erlang.
So I went on the github to see if there was anything I could do and found an interesting feature request.
https://github.com/pgourlain/vscode_erlang/issues/167

OTP is all about genericity and it provides modules which have implemented the generic part of some behaviours.
As a developper, you can then just use that behaviour and the only thing left to do is to write the specific part.
But there is still some redundancy because we need to write callback functions.
Those functions have specific names, signatures and return values and thus we also need to read and follow the documentation.
This is a tedious process and that's why the extension vscode_erlang provides two snippets of code for generic behaviours.

I think this feature request is interesting because gen\_fsm is a specialised version of gen\_server and sometimes one may use the latter for things that could be handled better by the former.
Because this extension has snippets for gen\_server and not for gen\_fsm it would be tempting to do just that.
The repository owner has responded positively to the request and suggested that the one who asked for it proposes something, but after a few weeks there is still nothing.
I decided to do it by following the style of the other snippets and made a pull request.
https://github.com/pgourlain/vscode_erlang/pull/171
The pull request was merged a few days later.
It was my first contribution to an open source project and even though it was not the project I initially planned to contribute to, this is where I begin.
