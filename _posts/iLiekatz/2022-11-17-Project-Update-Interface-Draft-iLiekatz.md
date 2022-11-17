—
layout: post
author: iLiekatz
title: "My Snake Game Interface Draft"
—
This past week I have definitively  decided on what I will be building for my project. I will be building my version of the game snake. I believe that this will allow me to both put what I have learned to practice, as well as be a big challenge for me to accomplish the simultaneous user interaction and game output. Now that I have decided on what I will be building, I have been able to lay out an overall milestone plan. I will be taking weekly inventory, and when necessary break down the overall milestones into more consumable, manageable pieces for me to work on. 

 ### Milestones
- [ ] Develop the Initial Interface
- [ ] Create the Snake Body
- [ ] Get the Snake Moving
- [ ] Control Movement with User Input
- [ ] Create Food
- [ ] Develop the Scoreboard
- [ ] Determine the End of Game with Wall Collision
- [ ] Determine the End of Game with Snake Collision
- [ ] Creating Levels
- [ ] Transforming UI to a better visual experience

### Challenges I Faced This Week
#### Creating the Snake Body
In order to complete this task, I knew that my snake needed to be made up of segments to help me out with the later tasks of growing the length of the snake. I thought 3 segments made sense to begin the game with, so that the snake can have a head, body, and tail. Once I had determined the requirements, I initially struggled with how to best produce the snake. 

First I tried to draw 3 separate squares that were side by side on the (x,y) coordinates. This was my first attempt at creating my snake following  that logic:
```
def snake_segment(x,y):
  snake.goto(x,y)
  for i in range (4):
    snake.forward(20)
    snake.right(90)

snake_segment(0,0)
snake_segment(20,0)
snake_segment(40,0)
```
I spent some time trying to figure out how I could fill in my 3 `snake_segment(x,y)` that I called so that it would resemble one snake. Ultimately I couldn't do it with my written code. While parsing through the turtle documentation I realized that there was a `turtle.shape(“square”)` that would work better for this. This was my new code for my initial snake body:
```
segment_1 = Turtle()
segment_1.shape("square")
segment_1.color("white")

segment_2 = Turtle()
segment_2.goto(-20,0)
segment_2.shape("square")
segment_2.color("white")

segment_3 = Turtle()
segment_3.goto(-40,0)
segment_3.shape("square")
segment_3.color("white") 
```
But now I was left with 12 lines of code just to create my initial snake, and I wanted to challenge myself at refactoring this. In the past I have really struggled with refactoring, so this took me some time to figure out. I had a live coding session with a good friend who is a programmer and she helped show me the pathway to do this. This is my initial snake body that I ended up with:
```
starting_positions = [(0,0), (-20,0), (-40,0)]

Segments = []

for position in starting_positions:
  snake_segment = Turtle()
  snake_segment.shape("square")
  snake_segment.color("white")
  snake_segment.goto(position)
```
#### Moving the Snake
Once I had the initial snake body, the next thing I needed to do was figure out how to make a simple continuous forward movement of all the segments together. Because I want the snake to constantly be moving while the game is going, I made a while loop. Inside the while loop, I nested a for loop that moves each segment of the snake that is in the segments list forward 20 pixels as shown below:
```
game_is_on = True

while game_is_on:
  for seg in segments:
    seg.forward(20)
```
When I ran my program it worked! But I found it had a very awkward movement and left the pen marks from the turtles. To account for the pen line I added `snake_segment.penup()`,

#### Turning Snake
I had a relatively easy time getting my snake to move forward. But when I added in a line of code to get the head, or `segments[0]`, to turn left or right I had trouble getting the body and tail of the snake to follow.

This was my code I tried first to move the head:
```
while game_is_on:
  for seg in segments:
    seg.forward(20)
  segments[0].left(90)
```
This code however did not work the way I intended. It moved the head, or `segments[0]` independently of the rest of the snake. This really stumped me for a long time, and I had another live coding session with a friend to talk through the problem I was facing. My friend posed me a question to think about, should movement be from the head to the tail or the tail or the head? 

### Current Road Block 
##### Rethinking the Logic of Movement
I spent some time with this question, and to be honest it hurt my brain a lot. I was going in circles, and I had to take a break and return the following day with fresh eyes. When I returned, I was still stuck but the break helped me not go in circles. 
I began breaking down the problem. I identified that currently it is going through the list from index[0] to the end. So when `segment[0]` turns, it is the only segment that turns, and everything continues on forward. I tried to get all the segments to turn and move forward by adding `seg.left(90)` to the for loop, however that didn’t do what I was hoping either. 
Then I gave more thought to specifically how I could make the last segment move first. If index[2] replaces index[1], and index[1] replaces index[0], I could get the snake body to follow wherever the head went. 

My current next steps are to figure out how to take the logic of moving the snake starting at the end first, and turn the head with the body to follow, and put it into code that executes properly. I also want to address the smoothness of the snake movement. It is moving segment by segment, but there has to be a way to make the movement visually smoother. I will have to examine the turtle documentation a little more and hopefully find some ideas on what can be done. After this I will develop code that control the snake via user input with the keyboard arrows. 

#### Current Milestone Checklist
- [x] Create Snake Class
- [x] Develop the Initial Interface
- [x] Create the Snake Body
- [x] Get the Snake Moving
- [ ] Control Movement with User Input
- [ ] Create Food 
- [ ] Grow Snake when Collides with Food
- [ ] Determine the End of Game with Wall Collision
- [ ] Determine the End of Game with Snake Collision
- [ ] Develop the Scoreboard
- [ ] Creating Levels

Here is my code as of right now: 
<iframe src="https://trinket.io/embed/python/bce622100a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
