---
layout: post
author: Rowan_Loft
title: "Rowan-Loft's first focused reflection"
---

So far, our classes on conditionals, flow of control, and functions has felt the most beneficial to our understanding of how code works and how we can manipulate code in trinket. Functions are very helpful because they help reduce the chance for errors and the need for debugging, which can be pretty hard at times when the error isn't very obvious like one word being spelled incorrectly. It's also very useful for creating code that would usually take up a lot of space. In the following program, I use functions a number of time in order to help shorten the ammount of code that has to go into the program.

	<iframe src="https://trinket.io/embed/python/3c5345e913" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

You can see the functions used for creating star shapes in the code:

```
def draw_star(turtle, color, size, x, y):
  turtle.penup()
  turtle.color(color)
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  turtle.right(144)
  for i in range(5):
    turtle.forward(size*2)
    turtle.right(144)
    turtle.forward(size*2)
  turtle.end_fill()
  turtle.setheading(0)
```

as well as the code used for generating stars using random parameters in the code:

```
def stars_in_space():
  draw_star(random.choice(s), random.choice(c), (random.choice(t)), random.randint(-200, 200), random.randint(-200, 200))
```

On the topic of random stars though, our runestone chapter on functions where they focus on using math and random numbers appears extremely useful for stress-testing different programs that have been created. But being able to curtail the code to certain parameters by defining what numbers among an unlimited-until-restrained stack also appears very beneficial, like what you can see part of in my code. I used `random.choice()` multiple times in the same line of code and pulled from three different variables, those being: 1 of 3 turtles, a size for the stars generated among a controlled list, and a color among a controlled list. Knowing the general dimensions of the invisible *x,y* cordinates that trinket uses also helped in the "random" generation. 

In my code, I assigned three different turtles in the program that would accomplish the same task, but independently. The code for them was one that we've seen multiple times, being,

```
lofty = Turtle()
lofty.shape("turtle")
lofty.speed(10)
```

but I'm wondering if it would have made the code even easier to accomplish if we could assign a turtle to accomplish this task but without having to assign a quick speed like I did, `lofty.speed(10)` and instead just make the program execute instantly. I'd also like to know how the code would change if the other turtles were to be removed, if that would have any effect at all. The last thing that comes to mind if imported packages. I know that we've scratched the surface with `turtle`, `random`, and `math`, but I really want to learn about what other packages can accomplish or help accomplish in our code. 
