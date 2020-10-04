# Open Source Contribution Project
*Author :* William Visée
*Date :* November 2019
*NOMA :* 67181500

## Research and Selection of the Project
I used to play a lot to video games when I was in high school. When I arrived at the university, I stopped mostly because I did had the time to play anymore.
I was a little nostalgic of this period so I decided to contribute to an Opensource game. I search for games that I have played before and decided to contribute to a Minecraft mod.
The mod is [Mekanism](https://github.com/mekanism/Mekanism). It is a mod that add high-tech machinery that can be used to create powerful tools, armor, and weapons. In this mod there are solar panels, wind turbine, ballon, tubing of water and lava, ...

The mod is dependent of [Forge](https://github.com/MinecraftForge/MinecraftForge). It is an open-source modding API for Minecraft. It basically help you create your own mod with by example given API.

The community has a Discord to communicate about issues or new idea. I've posted a message on it first to ask if I could send 1 or 2 pull request about new content and the community looked positif about it.

I first installed the mod and played at the game to see what I could do. I started playing with a flamethrower and advanced TNT from the mod and I've seen that the flamethrower couldn't burn and make explode the advanced TNT. I decide to cover this issue.
## Contributions

As I said, I implemented the feature where the Obsidiant TNT could be burn by the flamethrower and explode.

Here is my [pull request](https://github.com/mekanism/Mekanism/pull/5677). The pull request is still not accepted while I'm writing this lines.

The problem came from the fact that the Obsidiant TNT block hadn't the property to burn. I also haded a function that is currently called by fire when it is on top of this block. This function will launch the function that make the block explode.
