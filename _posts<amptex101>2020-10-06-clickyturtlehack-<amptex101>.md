---
layout: post
author: <amptex101>
title: "Allison's Clicky Turtlehack exercise!"
---
### I am going to embed my code below. Hope it works! 
  
  <iframe src="https://trinket.io/embed/python/f3ab6743b1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### As for my reflection, this exercise taught me a lot. I got more comfortable using turtle animations and understood helper functions a little bit better. While helper functions are still a little bit fuzzy, I understand how to use them in actual coding a little more. I was able to successfully use the turtle to draw a triangle. I am still confused about how to use the keypress functions in turtle -- I tried and it didn't quite work. I will show the code I used below using the backticks. I am still happy about the small successes though -- turning the screen pink, and getting the turtle to exist and then draw a triangle, all by myself. 

```
turn_amount = 7                                       
move_amount = 10                                      


# Define a functions that should happen when a key is pressed
def go_left():
  tina.left(turn_amount)
  
def go_right():
  tina.right(turn_amount)
  
def go_forward():
  tina.forward(move_amount)
  
def go_backward():
  tina.backward(move_amount)
  
# Tell the program which functions go with which keys
myscreen.onkey(go_left, 'left')
myscreen.onkey(go_right, 'right')
myscreen.onkey(go_forward, 'up')
myscreen.onkey(go_backward, 'down')

# Tell the screen to listen for key presses
myscreen.listen()
```
  
