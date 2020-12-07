# Open Source Contribution Project
*Author :* Loïc Laderrière

*Date :* 2020

*NOMA :* 44261900

*Selected project :* [ServerSync](https://github.com/superzanti/ServerSync)

*Pull request :* https://github.com/superzanti/ServerSync/pull/223
## ServerSync
ServerSync is intended to make it easier for beginners to connect to a modified Minecraft server by automating certain tasks. It will sync all files and make any necessary changes for the user to join the server. (A player must have the same modifications as the server to be able to connect to it)

It is currently developed by one person (Created by [@superzanti](https://github.com/superzanti) and taken over by [@rheimus](https://github.com/rheimus)) it has +30,000 downloads on its [CurseForge page](https://www.curseforge.com/minecraft/mc-mods/serversync)

### Project Selection
It was obvious for me to choose this project because I use it personally.
I find that this one has a great potential but that the lack of functionalities and its too rudimentary interface fail it. Having already thought about working on it in my spare time, it's a pleasure to be able to do this as part of a course to try to make it more popular in the Minecraft community.

### Communication
I contacted [@rheimus](https://github.com/rheimus) by email to find out if he was interested in the complete GUI change and if so, did he agree to switch from Swing at JavaFx. I told myself that if a redesign had to be done, I might as well take the opportunity to change the librairy.

You should know that JavaFX is considered the successor to Swing because it has more support and features and that Swing will no longer be maintained by Oracle from 2026.

He suggested that I use [Miro](https://miro.com/), an online whiteboard, to discuss the project.
I started by showing him a prototype and then for each major modification, he gave me his opinion and guided me towards a design that he liked.

| <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture2.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture3.PNG" width="480"> |
|:---:|:---:|:---:|
| <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture4.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture5.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture6.PNG" width="480"> |
| <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/Capture7.PNG" width="480"> |
### Collaboration
I collaborated with [@FabianPuche](https://github.com/FabianPuche), one of the friends that I use this app with. So we divided the tasks. Each having implemented features as well as on its interfaces.

We helped each other to understand the code to integrate our codes together but each one has coded its features.

### Contribution
I continued to respect the main goals of ServerSync are:

- Small, ideally we don’t use libraries unless it would be unreasonable not to or it would provide a much worse experience

- Simple, whatever ServerSync does it should be usable by less technical users (difficult to achieve but a worthy goal)

The main objective of the redesign was to make it more "user-friendly" by changing the design too rudimentary for the "material design", by adding more information (list of mods, are they up to date or outdated ?, ...) and adding some features like the ability to change and save the app options. Previously, the user had to manually access modifier options files.
Make it more "maintainable" by switching to JavaFX and adding a navigation bar that will make it easier to add elements to the user interface.

The GUI has been improved: 

- Switch GUI widget toolkit (~~Swing~~ -> JavaFX) [@hadyark](https://github.com/hadyark)

- Add of a menu to navigate through the application [@hadyark](https://github.com/hadyark)

- Add a table to display every mods and their status [@hadyark](https://github.com/hadyark)

- The log panel has been separated from the other panels [@hadyark](https://github.com/hadyark)

- Add of a panel to modify the options [@hadyark](https://github.com/hadyark)

- Add custom themes [@hadyark](https://github.com/hadyark)

- The progress bar changes according to the overall progress and not according to the individual progress of the files [@FabianPuche](https://github.com/FabianPuche)

- Improve information about the progression during the update [@FabianPuche](https://github.com/FabianPuche)

New features:

- Can save and edit options in the application [@hadyark](https://github.com/hadyark)

- Can check the status of mods without forcing the update ("Up to date", "Missing", "Outdated") [@FabianPuche](https://github.com/FabianPuche)

### Old UI
<img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/OldUI.PNG" width="480">

### New UI
| <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/NewUI1.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/NewUI2.PNG" width="480"> | <img src="https://github.com/Hadyark/lingi2401/blob/master/images/Lo%C3%AFc-Laderri%C3%A8re/NewUI3.PNG" width="480"> |
|:---:|:---:|:---:|
