# Open Source Contribution Project

*Author :* Dimitri Wauters

*NOMA :* 10152001

*Project :* [K-9 Mail](https://github.com/k9mail/k-9)

*Link of the Issue :* https://github.com/k9mail/k-9/issues/5525

*Link of the PR :* https://github.com/k9mail/k-9/pull/5745

## Finding the project to contribute to

I use many open sources applications in my day-to-day life, so I didn't struggle finding one that I can contribute to.
I've chosen K-9 Mail because I use it for a long time as my main mail application so I thought that it would be good to contribute to it.

## Contribution
### Finding the issue

I've searched the "first good issues" from the project and found one that seemed relatively easy.
It was only writing a try/catch for a line of code that produced a crash when the user hasn't enabled the INTERNET permission on Android.
For a first step of contributing to an open source project, I've decided to correct it.

### Building the app

I have downloaded Android Studio and forked the project. I've then launched the project with gradle.
The build was successful the first time.
As my version of Android does not allow to modify this exact permission, I had to download an emulator.
Fortunately for me, Android Studio has one built-in. I was able to install a rooted emulated phone on my laptop.

### Correcting the issue

I first tried to reproduce the issue to know exactly how to fix the issue.
I successfully reproduced the issue by removing the INTERNET permission of my rooted emulated Android phone and loading a picture of a mail.
!["Found the issue"](https://i.imgur.com/vHUqxcO.png)
As intended, the app crashed when I tried to load the pictures.
The issue was fixed by catching and logging the exception.

### Communication with the community

I first tried to ask how to fix the issue in the post on Github but without any response.
The maintainer seems to be alone in the project management, so I decided to fix it the way I thought was good.
After sending the pull request with my modifications, the maintainer asks me to modify the log message and adding a space between catch and the exception to respect the code guidelines.
After this little modification, the PR was accepted and merged.
My initial log message was not very expressive on the type of error that was thrown but I copied a message that had the same style two methods lower.
I mentioned this to the maintainer and he told me that this method is not used anymore.
I proposed to help again by removing the unused chunk of code in the project, he accepted and thanked me.
After the exam session, when I have more time, I will try to clean the code of unused methods.
