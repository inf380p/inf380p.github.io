---
layout: post
author: JohnCBMeyer
title: "John's Clicky Turtlehack"
---

## Man, do I hate Python sometimes.
I decided that I wanted to make a Frogger clone for this week. I loved Frogger
as a kid, and I fondly remember spending hours trying to beat it on my grandparents'
ancient HP CRT hooked up to an equally ancient HP tower. Not sure why they were
so fond of Hewlett-Packard, but I can't remember them ever having a different
brand.</br>

Anyway, things went about as well as expected. My 'final' product for now is a
screen with a moveable turtle that has a goal zone and prints "VICTORY!" when
you enter that zone. No obstacles, and the only scenery is a couple of roads (of
which I am damn proud, by the way).</br>

So, I'm going to walk you through all the frustrating bits and show off my results
at the end.</br>

### Streets are hard, man.
I assumed that drawing two black rectangles the width of the screen with some
white stripes down the middle would be an easy, not-in-any-way-Herculean task.
My bad, Python. After much struggle, this is what I came up with to draw some
decent looking streets without hard coding each part:

```python
# Draw a street
def draw_street(turtle, y, width, height):
  # Draw streets
  turtle.color("black")
  turtle.penup()
  turtle.goto(-250, y)
  turtle.pendown()
  turtle.begin_fill()
  for _ in range(2):
    turtle.forward(width)
    turtle.left(90)
    turtle.forward(height/5)
    turtle.left(90)
  turtle.end_fill()

  # Draw lanes
  turtle.color("white")
  turtle.penup()
  turtle.goto(-250, y + height/10)
  for _ in range(25):
    for _ in range(2):
      turtle.pendown()
      turtle.begin_fill()
      turtle.forward(width/50)
      turtle.left(90)
      turtle.forward(2)
      turtle.left(90)
      turtle.end_fill()
      turtle.penup()
    turtle.forward(20)
```

I know, beautiful, isn't it?</br>

Sarcasm aside, this is around when I realized that
drawing things in a four-quadrant cartesian plane is a little irritating. I thought
the world would be all positive, with (0, 0) at the bottom-left corner and whatever
the max for both axes is at the top right. Somehow, *somehow*, I did not realize
that the `setup()` function has the ability to do this until I was 99% finished.
That is my first refactoring goal, as seen here in my to-do list:

```python
# XXX 1. Create a background image of several parallel streets
# XXX 2. Create a moveable player character
# TODO 2a. Refactor using setup() to make the coord plane only first quadrant
# TODO 3. Create moving enemy characters
# TODO 4. Detect collision with enemies
# TODO 5. Create buttons for menu
# TODO 6. Create Alternate map / enemies
# TODO 7. Create multiple levels
```

As a side note, I recently learned how to make checkboxes in Markdown. That list
would look like this:

- [x] 1. Create a background image of several parallel streets
- [x] 2. Create a moveable player character
- [ ] 2a. Refactor using setup() to make the coord plane only first quadrant
- [ ] 3. Create moving enemy characters
- [ ] 4. Detect collision with enemies
- [ ] 5. Create buttons for menu
- [ ] 6. Create Alternate map / enemies
- [ ] 7. Create multiple levels

Anyway, on to my next topic of suffering.

### Wow, onkey events can be weird.
I didn't have too much trouble coding player movement. I originally had the right
and left moves just rotate Frogger (or Turtler?), but I decided that just moving
left or right would be easier on the player. All of that looked like this:

```python
# Define player movement
def up(screen, turtle):
  turtle.setheading(90)
  turtle.forward(50)
  screen.update()
  if turtle.ycor() > 200:
    turtle.goto(-2, -225)
    turtle.write("VICTORY!", align="center", font=("Arial", 20, "bold"))
    turtle.goto(-2, -175)
    screen.update()


def down(screen, turtle):
  turtle.setheading(90)
  turtle.backward(50)
  screen.update()

def left(screen, turtle):
  turtle.setheading(180)
  turtle.forward(50)
  turtle.setheading(90)
  screen.update()

def right(screen, turtle):
  turtle.setheading(0)
  turtle.forward(50)
  turtle.setheading(90)
  screen.update()
```

That bit about writing "VICTORY!" in the `up` function is essentially a placeholder
for now, but I'll get to that. This all worked fairly well from the beginning, so
not too bad. The hard part was getting it to work with onkey events. I assumed
that it would be as simple as passing a movement function to the `.onkey()` method.
I didn't realize that `.onkey()` can't accept functions with arguments normally.
So, after a good bit of research, I found the `lambda` function in Python. That
solved my problem, and all of my key events are working now:

```python
# Let player move with arrow keys or WASD, exit with Esc
screen.onkey(lambda: movement.up(screen, frogger), "Up")
screen.onkey(lambda: movement.up(screen, frogger), "w")

screen.onkey(lambda: movement.down(screen, frogger), "Down")
screen.onkey(lambda: movement.down(screen, frogger), "s")

screen.onkey(lambda: movement.left(screen, frogger), "Left")
screen.onkey(lambda: movement.left(screen, frogger), "a")

screen.onkey(lambda: movement.right(screen, frogger), "Right")
screen.onkey(lambda: movement.right(screen, frogger), "d")

screen.onkey(bye, "Escape")
```

Click events were even weirder, since they have to us the click's x and y coordinates
as arguments. That took another while, but I finally got my turtle to change color
randomly on click:

```python
# Change player character color on click
colors = ["green", "blue", "red", "black", "white"]

def change_color(x, y):
  if x < 1000 and y < 1000:
    frogger.color("black", colors[randrange(0, 5)])
  else:
     frogger.color("green")
  screen.update()

screen.onclick(change_color)
```

Part of the problem was the weirdness with four-quadrant cartesian coordinates
not seeming to work the way I think, but I found a work around by setting the values
higher than the max on screen, so this guarantees a roll on the color table each
click.

### Turtle.pos() doesn't want to work for me.
For some reason, every time I tried to code in the victory condition, I created
a memory leak and the program crashed. I was following suggestions found online,
and I'm still not sure what I was doing wrong. But, awarding the victory screen
anytime Frogger gets above a certain y-value seems fine, so I'm okay with the way
things currently work. Basically, if you get Turtler past the last road, you win.
Simple enough.

### Next steps
I really need to get the enemies (cars) working. Right now, I have created the 
world's least interesting turtle simulator. So, my next priority is getting cars
to move around on the roads. After that, I need to make sure that touching a car
kills Turtler. Poor little guy. Not sure how I'm going to accomplish this yet, but
I'll figure it out.

### The prototype
Okay, finally, here's the trinket with my current version. You can use the arrow
keys or WASD to move, and clicking will roll and random color for Turtler. Have
fun.

<iframe src="https://trinket.io/embed/python/2e445245ba" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
