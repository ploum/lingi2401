# Open Source Project


***Author:*** Martin Vivian

***NOMA:*** 0101-15-00

***Open Source Project:*** [Flym](https://github.com/FredJul/Flym)

***Academic year*** 2020-2021


## Introduction
Finding an open-source project worried me a lot. Indeed to be able to help people who are already familiar with their project seemed quite hard. I was even more worried about the random side of not being able to immediately understand the complexity of a project before, the interactions with communities, etc. In this report, I will explain how I did my project research, my selection, and finally how I contributed to the project that I selected.

## Project research
Since I didn't know the open-source world, during September and October, I mostly spent my time observing dozens of projects, understanding how the communities interacted, go to their chat, etc. To know enough to start a selection in November.

### First attempt

I found a python library used in scientific research to model the movement of stars, planets, satellites, etc. 
Having studied physics and still being passionate about astronomy I was tempted to participate in it.
Especially since I noticed that this project was welcoming to newcomers. 
I see a " [good first issue](https://github.com/poliastro/poliastro/issues/1042) " and try to do it locally. 
In the beginning, I was thinking that I had something working because of all the tests of the library pass. 
Then I tell the communities that I want to try this issue. But after some check, I discover by myself that the tests
 were running directly on the library and not on my code. 
 So, my code was false, and I discover that what I must implement was more difficult than I think. 
 Then I rapidly say to the community that I abort the issue the time to start to find something and to avoid wasting their time. 
I was trying to finish it but the more I was trying to work on it, the more I discover how it will be complex, and what I must do was a few documented.
 Then after some days, I was trying to search for another project. because I was almost not advanced, and I felt that I would take far too much time.
   
### Second attempt
After my first experience, I was trying to find something easier.I found the Android application [NewPipe](https://github.com/TeamNewPipe/NewPipe).
But when I was trying to compile it, my antivirus says that there was maybe ransomware. Then it was impossible to compile the project then I rapidly forget this project.
After I understand that it was because I compile the project in my "Documents" file and the antivirus didn't like it.

### Last attempt
In the meantime 
I remembered that I had an application [Flym](https://github.com/FredJul/Flym) that I use from time to time on my smartphone that was open-source. 
And I found a bug in it a few months ago (before I took the open-source course). So I became interested in this project, and this is finally the final project where I made my contribution.

## Project description
[Flym](https://github.com/FredJul/Flym) is a news reader where we can follow multiple sources (websites, forums, etc.), sort these sources by topic, save articles for future reading...

## Project choice justification
* It's an application that I use on my smartphone mostly because open-source, no ads, no account, nothing to pay, and the app evolve a lot.
* I had already in the past discover some bugs by myself.
* I have already done android programming.
* The project was not dead and since it evolve rapidly, it was easier to find a bug.

## Starting to contribute

### How I found something to do ?
I see that some people speak about a bug with the "Favorite articles" in this [issue](https://github.com/FredJul/Flym/issues/723). 
At first, I thought there were wrong or it had already been corrected. But while searching the bug 
I realized that we couldn't add or remove an article from the favorites after reading them. This issue wasn't very detailed and there was a bug.

### What I have done
First, I was trying to understand the structure of the project. After I discover that it use the disable/enable method to change the colors to know if an articleis already read or not. Then the problem is that this method also deactivates the button and does not change only the colors.
For the fix, I remove the line that deactivate the button. And for the changing color, I replace it with a "set color" who will only change the color and not disable. After testing, I push the fix in this [PR](https://github.com/FredJul/Flym/pull/725).


```diff
  import android.annotation.SuppressLint
+ import android.graphics.Color
  import android.text.TextUtils
  import android.view.LayoutInflater
  import android.view.View
  @@ -84,7 +85,13 @@ class EntryAdapter(var displayThumbnails: Boolean,private val globalClickListen
                      date.isEnabled = !entryWithFeed.entry.read
                      date.text = entryWithFeed.entry.  getReadablePublicationDate(context)

-                      favorite_icon.isEnabled = !entryWithFeed.entry.read
+                      if (entryWithFeed.entry.read) {
+                          favorite_icon.setColorFilter(Color.GRAY)
+                      }
+                      else {
+                         favorite_icon.setColorFilter(Color.WHITE)
+                     }
+
                      if (entryWithFeed.entry.favorite) {
                          favorite_icon.setImageResource(R.drawable.ic_star_24dp)
                      } else {

```

Some hours later my [PR](https://github.com/FredJul/Flym/pull/725) was accepted. But last month Google added [new restriction](https://support.google.com/googleplay/android-developer/answer/10177647?visit_id=637410766788299017-71528281&rd=2#news) about news app and there is a risk that now the Google Play Store refused to update this type of application.

## Conclusion
Despite the time I spent looking for an open-source project, observing the organisation of the different communities, and the two failed attempts, I finally managed to have a [PR](https://github.com/FredJul/Flym/pull/725) accepted in an open-source application that I was using.