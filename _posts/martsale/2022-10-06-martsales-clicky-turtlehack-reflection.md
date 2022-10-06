---
layout: post
author: martsale
title: "Alexis's Clicky Turtlehack Reflection"
---

# Thoughts on OnKey and OnClick
Learning OnKey and OnClick was exciting for me because it opens up so many possibilities for user interaction. However, reading this assignment was really daunting because it left so many possibilities of what could be done. After spending a few days unable to decide on a projct, I decided to use the treasure map example from the project brief. 

Here is my treasure hunt code that I ended up with:

<iframe src="https://trinket.io/embed/python/767f95fc15" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# Wins for this project
## Figuring out distance between points
In order to provide user feedback if they're getting closer to the winning spot, I needed to create a function to calculate the distance between where the turtle is and where the randomly determined treasure location was. After consulting my engineer boyfriend about what math would yield a value for this distance, I created a formula for the pythagorean theorem. 

```
distance = math.sqrt(((x1 - x2)**2) + ((y1 - y2)**2))
```

## Calling on Random to create treasure location
Another challenge I was presented with was how to create a random treasure location to make the game exciting every time it's played. I imported the "random" module, and assigned a random x and random y variable. I was then able to pass these variables into my distance formula, and declare the user a winner if distance is less than or equal to 10.

```
x1 = random.randint(-150, 150)
y1 = random.randint(-100, 100)
```

## Using logic to indicate how close the user is
As mentioned above, I used my distance formula to determine how close the user is. Using logic, I also changed the color of the turtle to reflect how close the user was to the target coordinates. 

```
def proximity(distance):
  if distance <= 10:
    tina.color("green")
    congratulate(tina)
  elif distance <= 40:
    tina.color("yellow")
  elif distance <= 80:
    tina.color("orange")
  else:
    tina.color("red")

```

## Drawing a hint button
Another challenge to tackle was drawing a hint button in my setup function so the user knew where to click to trigger the hint function. We've been drawing with turtle since the first week, but it still took coordination to draw the button in a convenient location and declare that as the hint click parameters.

the hint button drawing:
```
 sally.color("purple")
  sally.penup()
  sally.goto(-20,20)
  sally.pendown()
  sally.fill(True)
  sally.forward(40)
  sally.right(90)
  sally.forward(40)
  sally.right(90)
  sally.forward(40)
  sally.right(90)
  sally.forward(40)
  sally.right(90)
  sally.fill(False)
  sally.penup()
  sally.goto(-5, 0)
  sally.color("white",)
  sally.write("hint", None, "center", "12pt bold")
```

the click function:
```
def clicky(x, y):
  if x > -20 and x < 20 and y > -20 and y < 20:
    hint()

```

# A few things could've gone better as well...
## Calling in a new module
I tried to create another module page in this code to call in a few functions. I really struggled passing the turtle and my coordinates across the modules and did not end up succeeding. It also seems to be working in different ways depending on the day that I load it. Here's a copy of the code I was working on that kept failing:

<iframe src="https://trinket.io/embed/python/dd6ad705d7" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Resize Turtle
I tried to make the turtle bigger when the user hits the space bar to make it look like it's jumping, but trinket was throwing an error that it didn't recognize the functions I found in turtle documentation.

Here's the code that didn't work:
```
  tina.shapesize(5, 5, 12)
  time.sleep(1)
  tina.resizemode("auto")
```

Here's the documentation for the functions I was trying to call:
[Python Turtle Resize Documentation](https://docs.python.org/3/library/turtle.html#turtle.resizemode)

## Z Index to hide hint box
I tried to hide the hint box on a win condition, but then the black box I drew over the hint box always seemed to be on top of everything that happened after this. After some quick searching, it seems like other people are also struggling with the z-index in turtle. Here's my win condition code, piggybacking on the animation provided in the starter code:

```
a_turtle.color("black")
  a_turtle.penup()
  a_turtle.goto(-22,22)
  a_turtle.pendown()
  a_turtle.fill(True)
  a_turtle.forward(44)
  a_turtle.right(90)
  a_turtle.forward(44)
  a_turtle.right(90)
  a_turtle.forward(44)
  a_turtle.right(90)
  a_turtle.forward(44)
  a_turtle.right(90)
  a_turtle.fill(False)
  a_turtle.penup()
  a_turtle.penup()
  a_turtle.speed(10)
  a_turtle.goto(0,0)
  a_turtle.color("yellow")
  a_turtle.write("You Win!", None, "center", "20pt bold")
  for i in range(100):
    random_xy = (random.randint(-200,200), random.randint(-200,200))
    random_360 = random.randint(0,360)
    random_color = (random.randint(0,255),random.randint(0,255),random.randint(0,255))
    a_turtle.color(random_color)
    a_turtle.goto(random_xy)
    a_turtle.stamp()
    a_turtle.seth(random_360)
    
```

## Make Line Breaks
I also struggled with  making line breaks in my turtle instructions using \n. I'm not sure if that's because I had it in what the turtle was writing? I ended up rephrasing my instructions to keep them visible on one line.
