Open Source Contribution Project

Author: Belami Nizeyimana

NOMA: 26041600

Year: 2021

Selected project: command-line-chess

#  command-line-chess

For this project I knew I wanted to contribute to an open source project related to chess game but which one ? After having searched for a long time and compared a lot of  projects between them my I finally chose to contribute to **command-line-chess**. It is a python program to play chess against an AI in the terminal, it also allows us to play against a second player. 

![Chess game](https://camo.githubusercontent.com/476a7673cc67d54216a18525b940a05b1df32c52da4c0d84572ec0b3a0e3b462/687474703a2f2f692e696d6775722e636f6d2f417358686876432e706e67)


## Random move bug

Before I started my contribution, I had already spotted a bug. Indeed, the game offers to the player the possibility to make a random move if he can't decide. He just had to enter the "r" key on the console when it's his turn to play but it didn't work. Then, my first contribution was to fix the bug.

## Chess pieces

The first contribution I made was to give to the different pieces of the chess game a illustration
Before, the pieces were only represented by letters, 'p' for pawns, 'K' for knights, 'R' for rooks, 'B' for bishops, 'K' for kings and 'Q' for queens. So I decided to illustrate all these pieces with their respective images. 


"R" -> '♜', "N" -> '♞', "B" -> '♝', "K" -> '♚', "Q" -> '♛', "P" -> '♟'

![enter image description here](https://i.imgur.com/qQrINcA.png)

## Chessboard

I decided to add a kind of chessboard to the game. From now on, players will have the possibility to play with black and white squares like a real Chess game. However, after thinking about it, some may find that there is too many images in the game because of this. In fact, before playing the game seems to be perfeclty 'balanced' but it's only after playing a few moves that you realize that the game is a bit messy with all its illustrations. So, I decided to keep the points : '.' instead of squares

![enter image description here](https://i.imgur.com/UjypQIi.png)

![enter image description here](https://i.imgur.com/ACxNG2v.png)

## Better gameplay

When I played the game for the first time, the first thing that bothered me was the way the chessboard was printed. The board was printed direclty after we enter a command in the terminal. For instance, it printed the board after I asked for possible moves to do. It causes that sometimes the game would print the same board twice in a row, which can be a hindrance to the game experience. So I decided to print the board only after making a move.

## Noticed bug

After playing a entire game I noticed that not all the rules were respected. Indeed, the game did not stop after one of the two kings was taken. In other words, the game continue even after checkmate. Unfortunately, I couldn't fix this bug but I left a 'TODO' in the code so that the bug could be fixed by another contributor.


