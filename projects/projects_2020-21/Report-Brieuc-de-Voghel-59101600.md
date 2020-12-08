# Open Source Contribution Project
*Author :* Brieuc de Voghel

*Date :* 2020

*NOMA :* 59101600

*Selected project :* [GIMP-ML](https://github.com/kritiksoman/GIMP-ML)

## Project Selection

For a first open source contribution, I wanted to select a project I would use myself. There are a few software I use at least monthly, but the one that caught my interest is a tool I really enjoy using. [GIMP](https://www.gimp.org/) (GNU Image Manipulation Program) is the open source equivalent to Photoshop and is a great idea for this project.

Contributing to the real GIMP seemed to be a bit overwhelming though. So I settled for a useful add-on, called GIMP-ML. GIMP-ML allows you to apply advanced Machine Learning and Computer Vision algorithms to your creations. As I've always been interested in these subjects, I decided to get to know the project.

## GIMP-ML

![GIMP-ML](https://github.com/kritiksoman/tmp/raw/master/screenshot.png)

GIMP-ML regroups tools developped in part by others into a library using GIMP's add-on API. Some methods use state of the art deep learning models, other methods use more traditional approaches.

Reasearchers who developped some image processing tools even asked the maintaner to incorporate their tool into GIMP-ML for a more practical use.


Here is a [list of the different tools](https://github.com/kritiksoman/GIMP-ML#tools) available in GIMP-ML.


### Getting in touch with the maintainer

As the GIMP-ML library only exists since March 2020 and since there is still no real community, I contacted the project owner (only maintainer for the moment) to know if he would be interested in some help to open up the project to open source. We discussed for a while but I quickly realised he mainly developed the project for himself but decided to publish it anyways.

Luckily, short time after that, the project quickly got popular and some pull requests / issues were posted, and the maintainer seemed to be interested in incorporating those changes.

### GIMP switching to Python 3

GIMP latest stable version, 2.10, still uses Python 2.7. They should be switching to Python 3 late 2020, but in the meantime, this still limits the usability of potential interesting tools and image processing tools for GIMP.

## My contribution

When first installing the GIMP-ML add-on, I encountered some issues with instalation. I disregarded those at first.
It was only later that I considered to correct the bug I encountered. 

The bug was related to the instalation of python packages in a python virtual environments. Packages were loaded without giving the correct package version.
Also, if the envoronment was created but the packages did not manage to be installed, running the install script would not do anything.

This is [my pending pull request](https://github.com/kritiksoman/GIMP-ML/pull/30).

``` diff
@@ -23,85 +23,21 @@ if [ ! -d "gimpenv" ]; then
	python -m pip install --user virtualenv
	python -m virtualenv gimpenv
	source gimpenv/bin/activate
-	python -m pip install torchvision
-	python -m pip install "opencv-python<=4.3"
-	python -m pip install numpy
-	python -m pip install future
-	python -m pip install torch
-	python -m pip install scipy
-	python -m pip install typing
-	python -m pip install enum
-	python -m pip install pretrainedmodels
-	python -m pip install requests
+	python -m pip install -r requirements.txt
	deactivate

	echo "-----------Installed GIMP-ML------------"

else

-	echo "Environment already setup!"
+	echo "------Checking GIMP-ML environment------"

+	source gimpenv/bin/activate
+	python -m pip install -r requirements.txt
+	deactivate

+	echo "------------GIMP-ML updated-------------"

fi
```

Of course the `requirements.txt` was also added : `pip freeze > requirements.txt`

## Bigger contribution

Of course this first contribution was very easy and quickly implemented. I wanted to participate in a bigger contribution. 
[An issue](https://github.com/kritiksoman/GIMP-ML/issues/29) was posted asking to add a particular tool available in another GitHub repository. [This tool](https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life) allows to restore old photos.

Before commenting on this issue stating I was interested in implementing the addition of the tool, I started to explore the said tool. I quickly familiarized myself with the code and the deep learning model. I tested the tool on some pictures and then started to implement the GIMP-ML add-on using this tool.

Unfortunately for me, the maintainer quickly implemented to tool into GIMP-ML so my work became obselete.


## What I have learned

My key take-aways are the following :

* Do not over-estimate a project to contribute to. If the bigger picture seems overwhelming, try to find "sub-projects" or add-ons, improving the larger project at a smaller scale.
* Communicate ! I did well by contacting the maintainer and discussing potential needs etc., but I underestimated the importance of discussing a particular issue before diving into the implementation itself on my side.
* I learned interesting aspects of image processing and more particularly the inner workings of GIMP. I surely will continue to use the GIMP-ML add-on and I might implement other tools in GIMP in the future