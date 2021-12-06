# Open Source Contribution Project

Author: Elio Pani

NOMA: 61541400

Year: 2021

Selected project: https://github.com/pytorch/pytorch

*Pull Request :* [Pull Request #69218](https://github.com/pytorch/pytorch/pull/69218)

# About the project

While working on a project, I was using a lot PyTorch, it is an open source machine learning library based on the Torch library, used for applications such as computer vision and natural language processing, primarily developed by Facebook's AI Research lab. I saw that there was an issue in the documentation when comparing it to the result I got. As I learned to use more and more Pytorch, I thought it was a good idea to learn more about it's world and the people behind. It's a highly used application so I know I would learn a lot.


# About the issue <span style='font-size:8pt;'>*(2021/09/19)*</span>



In deep learning by default, the calculations are made with float32 (32 bits for each number). Pytorch offers “AMP” (Automatic Mixed Precision) which mixes calculations between float16 and float32 which makes calculations faster and lighter.

For several GPUs you use “DataParallel” from Pytorch which allows to parallelize the calculations on several gpu.
According to the documention you couldn't use AMP and DataParallel,together, but when you tried with the code it worked. So I looked at the issues related to the problem and found that in fact the code had been updated to resolve this problem, but not the documentation.

When I wanted to use DataParallel with AMP I went to see how it works in the doc and when I compared my logs with the information in the docs, I realized that it was not up to date. Moreover, while digging a little, i saw one of the contributors who had commented that the code had been modified but that the doc was still the one for the old code.In the previous version, it was necessary to add lines of code for it to work while the current code does not require it. So I modified the doc to be consistent with what the code is doing.

# About the process 
Begin the process of correcting the documention, I had to fork the project on my account. Once the project copied, I could modify the doc.

![Capture d’écran 2021-12-06 à 19 26 42](https://user-images.githubusercontent.com/71745763/144901395-de7001e2-6b78-4eda-86f3-b8e9b5b82252.png)
Once that was done I created a new branch, commited and push the request. The Pull request was then created citing the issues.

As it is a highly developped application, it is developped by Facebook, there are many check that are runned through and you have to sign a contributor license agreement (CLA)

![Capture d’écran 2021-12-06 à 19 29 36](https://user-images.githubusercontent.com/71745763/144901782-2e97429f-c729-4dcc-8563-df6390214a66.png)


![Capture d’écran 2021-12-06 à 19 11 13](https://user-images.githubusercontent.com/71745763/144899277-72cb6224-29e0-4bb0-90fd-ad915abd04ba.png)

Once everything was settle from the other contributors, the push request was approved and the docuementation changed on the main repository of PyTorch

![Capture d’écran 2021-12-06 à 19 12 01](https://user-images.githubusercontent.com/71745763/144899391-1a19e8d1-3e0d-4103-92c4-1bbb6d0599e2.png)


# Conclusion

To conclusion, working in Open Source is something that really opened my eyes on the possibility of working on something big without central entity. That was my first experience in the world of Open Source and it was a really good one.

I'm also suprised to see how fast a project can grow when there are multiple contributors ready to put effort in it. There are over three thousand pull request right now on pytorch and forty thousands already closed. Futhermore there are still more than five thousands issues still unreasolve. To have all that open for everyone to use and see under the hood is a jewel of modern technology.
