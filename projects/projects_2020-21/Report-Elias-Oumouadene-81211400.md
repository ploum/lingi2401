# Open source strategy project
---
***Author***: Elias Oumouadene\
***NOMA***: 8121-14-00\
***Project***: [ASK](https://github.com/Buscedv/Ask)\
***PR link***: [turn 033 syntax into a styling string method](https://github.com/Buscedv/Ask/pull/44)\
***License***: [GPL-3.0 license](https://github.com/Buscedv/Ask/blob/master/LICENSE)

---

## Research of this project
My first idea was to brainstorm on the technology I like to use and specific point I would like to explore : DevOps / TechOps / Scripting / API / Python / Golang. \
I found then that cloud project would be too difficult for me to contribute as I would have need an instance to use. I never used Golang so it would have give me a not needed difficulty. I then focused on projects that use Python.

### Kalibri
The first project I wanted to contribute, I found the concept and the purpose of the non-profit that run it very inspiring. There is a lot of documentation available on the platform so I started by installing the project. Their open issues are either bugs ( with some ' beginner issues' and some harder ones ) or things to implement for their next milestone.
I followed all the installing process until having my one instance of kolibri running in my computer. I then started to look more deeper in the open issues and in the code and I had difficulty to start any of the open issues available at that point so I put that project to the fridge.

### Crypto
My next idea was to find open-source project linked to cryptocurrencies, I've found three interesting projects : 
[Arbitrader](https://github.com/scionaltera/arbitrader), [an arbitrage detector](https://github.com/wardbradt/peregrine), [a framework to build trading strategies on cryptocurrencies](https://github.com/garethdmm/gryphon) & [a framework for creating blockchain application](https://github.com/exonum/exonum). When investigating I found that this would maybe be too difficult for me to test the code and a lot of the open issues where problems to solve.

### Ask
After those two failed attemps I then looked at database of open issue on Google. It allows the user to search for projects that have good first issue that can be filtered ( I used a filter on the python language ) and that are really new ( this is a safety to not work on a project that has no maintenance and to receive a rapid feebdack on my pull-request ).
I found that [someone](https://github.com/Buscedv) was developing a new language to enhance the development of REST APIs. This is a subject I'm really interested (alongside flask that I already use for a client of mine) so I decided to contribute to this project.

> A backend programming language. Ask makes it incredibly easy to create REST APIs. Ask directly transpiles to Flask so no new deployment procedures are needed. Ask focuses on clear readable code and reduces a lot of boilerplate code when working with e.g. databases and JWT authentication ([source](https://github.com/Buscedv/Ask))

## Contribution
I worked on an open issue called [turn 033 syntax into a styling string method](https://github.com/Buscedv/Ask/pull/44), my first step was to understand a bit of the code and then understand what was that 033 syntax. I found that the code was divided in two different files and that I should be working mainly on one of the two. I then read the [CONTRIBUTING.md](https://github.com/Buscedv/Ask/blob/master/CONTRIBUTING.md) that tells me that I have to follow rules for my syntax (I found out later on that he is very strict about that). \
The goal of the open issue was to modify how he creates his `print()`, he uses color and styling in the `print()` method to help understand what is happening in the terminal when someone uses the program. 

```python
print('\033[95m' + 'Watching... (timeout ' + str(timeout) + ' seconds)' + '\033[0m')
```

### First pull request
For my first pull request I created a new method `style_print` that should be used in a `print()` method.

```python
def style_string(text,color='', bold=False):

	ret = text
	if color == 'red':
		ret = '\033[91m' + ret + '\033[0m'

	if color == 'green':
		ret = '\033[92m' + ret + '\033[0m'

	if color == 'yellow':
		ret = '\033[93m' + ret + '\033[0m'

	if color == 'blue':
		ret = '\033[94m' + ret + '\033[0m'

	if color == 'pink':
		ret = '\033[95m' + ret + '\033[0m'

	if bold:
		ret = '\033[1m'  + ret + '\033[0m'

	return ret

print(style_string('Watching... (timeout ' + str(timeout) + ' seconds)', color='pink'))
```
I also commented on my request that I put my function in the two files and that I don't know if this is the best way.

### Evaluation
When I woke up, I found that he already has check my code and that there was a comment created for nearly every line of my method. I was a bit surprised has I thought that I could not make a mistake on a code like that, but we need to put more energy on the code quality part.

* Thank you for your time and work ⚡️!
You are right about ask.py and ask-watch.py being separate, but since ask-watch.py imports ask on line 3, you could import style_string from ask. e.g. from ask import style_string.
* Put spaces after commas.
* Rename to: style_print()
* Since style_string() this is only used when printing to the console, maybe the function could print the text out instead of returning it?
* You could create two variables: prefix = '\033[' & suffix = prefix + '0m' at the top of the method to reduce duplicate code a bit.
* Instead of doing the same thing many times, create a dictionary with 91m, 93m and so on with 'red' and 'yellow', etc. as keys. Then you can apply the styling (along with the changes from my previous comment about the prefix & suffix variable).

### Second pull request
To be able to use remove the `print()` and have it in my function means some reworking on a new feature : make the function add or not a `\n`.
There was also issue if he wants to add more text in front or after the styled text if I completely removed all other `print()` instances

I refactored my code to follow his rules and to make sure that my code could be easily updated in the future if new style or colors would be needed.

```python
def style_print(to_modify_text, left_text='', right_text='', styles=[], ends_with='\n'):

	prefix = '\033['
	suffix = '\033[0m'

	styles_dict = {
		'red' : '91m',
		'green' : '92m',
		'yellow' : '93m',
		'blue' : '94m',
		'pink' : '95m',
		'bold' : '1m'
	}

	ret = to_modify_text

	for style in styles:
		ret = prefix+ styles_dict[style] + ret + suffix

	print(left_text + ret + right_text, end=ends_with)

style_print('Building Folder Structure... ', styles=['bold'], ends_with='')
```

This time he directly accepted my code and merged it.
### After that
When finishing my report I took a look back at the repository to see what happened to the code I added.
I found that he modified just a bit my function and that when `style_print()` was not clearly needed, he just used the usual `print()` method in his code. This allowed him to remove all my left_text, right_text code.

The new version looks like this : 
```python
# Prints out text colorized and (optionally) as bold.
def style_print(text, color=None, styles=[], end='\n'):
	prefix = '\033['
	suffix = prefix + '0m'

	available_styles = {
		'bold': '1m'
	}

	colors = {
		'red': '91m',
		'green': '92m',
		'blue': '94m',
		'gray': '90m'
	}

	result = str(text)

	if color in colors:
		result = prefix + colors[color] + result + suffix

	for style in styles:
		result = prefix + available_styles[style] + result + suffix

	print(result, end=end)
```

## Conclusion
This was the first time of my life I did a contribution for a project I have no business with. I didn't know what to expect and how it would go down.

I am a bit sad to not have contributed for a very big project such as Kalibri and helped a non-profit delivering his product but I think that contributing to a small project broke a small barrier in my mind.

I know right now that if I want to develop myself in a specific technology or language I can just try to contribute to an open-source project. This will help me understand how to build those kind of project by reading the documentation, the contribution and the code. This will also make me follow a strict rule of coding and increase my code quality. I will be able to receive feedback on the code I write without the needs of a specific cursus or asking a professionnal.

This project made me crawl into a lot of different type of open-source project and find things that I didn't know existed in open-source (all those crypto framework). It made me also discussed with a stranger on github and I didn't know he would take the time to really assess my contribution.

This cursus also gave me the impulse to create projects in open-source and managing the issues so that other developers could come in and help me build the project.