---
layout: post
author: hyotester
title: "Hyo's Final Project Interface Update"
---
# Final Project Interface Start

For the final project, I'm planning to  to build game to find your route in the hospital. So, I'm exploring pathfinding code and practice code through existing game: How to Make a Turtle Maze Game.
I have been able to create an interface that allows user to find path from one point to another in order to arrive their final destination!

Following can be a good plan to compelete my final project:

- To Make a map, and try to understand method to draw a Maze
- Create a maze with multiple paths ( I need to learn method by setting the optional argument loopPercent)
- Create Agents to place inside the Maze
- Set up the final goal (Location of the agent)

## Creating the Interface with Turtle Maze Game (Pathfinding)

To create the interface with pathfinding, I need to generate a Maze first:

```
#This function will draw our Maze Board
def draw():
	"Draw maze."
	color('black') # colour of the maze
	width(5) # size of the maze's walls

```
I was expected to import image as map, but I just need to create the maze object and then apply the CreateMaze function. 

To detect and draw multiple lines, I explored this method: 

```
#This function will detect and draw four lines
def tap(x, y):
	"Draw line and dot for screen tap."
	if abs(x) > 198 or abs(y) > 198:
    	up()
	else:
    	down()
```
Using a for loop:

```
for i in range(0,3):
   myPen.forward(100)
   myPen.left(90)
  
```

Here is my currenlty experiment to create a maze interface in turtle:

<iframe src="https://trinket.io/embed/python/3779b6ba4f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Next Steps
I will follow my plan to create a maze ( route for mao) and find way to follow multiple paths in a maze!



