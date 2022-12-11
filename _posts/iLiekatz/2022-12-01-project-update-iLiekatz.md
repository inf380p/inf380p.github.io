---
layout: post
author: iLiekatz
title: "My Snake Game Project Update"
---

### Project Update

#### Better Snake Movement
I spent this past week addressing the movement of my snake. I had 2 goals in order to complete this: Smooth Movement and Proper Turning

To address the smoother movement of the snake, I used the `screen.tracer()` method. Tracer turns the animation on and off. When it is turned off, I can then use the `screen.update` method to tell my program when to refresh the screen. This allowed me to build the entire snake while the animation is off, so when I update the screen the snake doesn’t show up in pieces but as one single unit. Next I put an update method in the while loop that defines the movement of each segment. This allows it to move all the segments while the animation is off, then update so it appears to move as a single unit rather than in pieces. 

My next goal was to get the snake to move properly. Last week I was left with a snake that would turn, and the body would detach from its head and keep moving on. So I needed to get the snake to turn and have the entire body follow. After 

I first tried this block of code, but the head turns left forever while body keeps going forward:

```
while game_is_on:
  for seg in segments:
    seg.forward(20)
  segments[0].left(90)
```

Then I tried this. It moved the last segment to the one before like an inchworm. However the head still turns but the body kept moving forward:

```while game_is_on:
  for seg in segments [::-1]:
    seg.forward(20)
    segments[0].left(90)
```

I was really stuck on this, and had to do a live coding session with my programming friend. She helped break the problem down so that I could refactor the snakes movement to this:
```
 # Body of snake follows when head turns
 for segment_num in range(len(segments)-1, 0, -1):
    new_x=segments[segment_num-1].xcor() # challenge, I left out ()
    new_y=segments[segment_num-1].ycor() # challenge, I left out ()
    segments[segment_num].goto(new_x, new_y)
```
#### Movement with Key Clicks
This task was very easy for me! It is one of the best understood methods from previous work we have done in class. I was able to get the snake to move up, down, left and right with the arrow key presses.

#### Next Steps 
My next things to focus on will be developing the food, so that the snake can collide and grow. I have considered attempting to use png’s for this. I have found several fruit images like an apple banana, and orange that would be great food. I have also found a poison apple that could be interesting to place at the hardest level in the future!

#### Current Milestone Checklist
- [x] Create Snake Class
- [x] Develop the Initial Interface
- [x] Create the Snake Body
- [x] Get the Snake Moving
- [x] Get snake moving properly
- [x] Control Movement with User Input
- [ ] Create Food 
- [ ] Grow Snake when Collides with Food
- [ ] Determine the End of Game with Wall Collision
- [ ] Determine the End of Game with Snake Collision
- [ ] Develop the Scoreboard
- [ ] Creating Levels

Here is my current Snake Game Trinket as of this update:
<iframe src="https://trinket.io/embed/python/a632670456" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
