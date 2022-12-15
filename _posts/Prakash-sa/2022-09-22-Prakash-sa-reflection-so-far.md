---
layout: post
author: Prakash-sa
title: "Prakash's reflection on the class so far."
---

**Reflection**

In this reflection, I have made the new python file shapes.py and added the functions of square, triangle, pentagon, polygon and random polygon. I used the concept of generating random number and importing the functions from different file that was taught in the class. Now I got good grasp of that concept.


Below code generate the random number from 0 to 360 with the step of 1
```
# get randome integer from 0 to 360 with the step of 1
rand = random.randrange(0, 360, 1)
```

Below code will draw the random polygon with random color. I have implemented the random length and random lines formula. It will pick up the random color from the colors list. We can also give the x and y coordinate to the function. Then it will draw the random polygon based on the count of random lines.

```
def draw_fully_random(turtle, rand, x = 0, y = 0):
  rand_length = (rand % 10 + 2) * 10
  rand_lines = rand // 3
  colors = ['blue', 'black', 'red', 'green']
  turtle.color(colors[(rand % 5) - 1])
  turtle.penup()
  turtle.shape("turtle")
  turtle.goto(x,y)
  turtle.pendown()
  for i in range(rand_lines):
    turtle.forward(rand_length)
    if rand % 2 == 0:
      turtle.right(rand)
    else:
      turtle.left(rand)
  turtle.setheading(0)
  return rand
```

This exercise help me to get the better understanding of importing functions from other files, write neat, readable and understandable code and got the good grasp of using turtle library.

# My functional trinket
An iframe of my functional trinket can be found below.

<iframe src="https://trinket.io/embed/python/1e7203d8d0" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
