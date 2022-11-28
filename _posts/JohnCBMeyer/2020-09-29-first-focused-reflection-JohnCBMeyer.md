---
layout: post
author: JohnCBMeyer
title: "Meyer, John First Focused Reflection"
---

## Finally figured out Python functions
I mentioned this in my first post, but for some reason, I always struggled with 
Python function definitions. I don't know why, but anytime I had to read or write
a function in Python, I was always confused by the syntax. I think it's partly
because it's different from R's method of defining custom functions. </br>
- For example, in R, I would write:
  
  ```r
  foo <- function(bar) {
    something(bar)
  }
  ```

But Python function definitions just didn't click with me until we tried the
first turtle assignment. The first custom turtle I tried to write used this:

```python
def draw_triangle(turtle, color, size, x, y):
  turtle.penup()
  turtle.color("black")
  turtle.shape("turtle")
  turtle.fillcolor(color)
  turtle.goto(x,y)
  turtle.pendown()
  turtle.begin_fill()
  for i in range(3):
    turtle.forward(size)
    turtle.left(120)
  turtle.end_fill()
  turtle.setheading(0)
```

Something finally just clicked when I was experimenting with turtle.

## More problems with Python functions
I thought I was pretty comfortable with Python functions until I wanted to use
some randomization in another turtle function. My idea was to use the `random`
package to have the turtle draw randomized designs. This seemed pretty
straightforward, so I just called the `randrange()` function normally inside the
function def statement. But it didn't work. I tried everything I could think of
(assigning the function call to a variable and using that variable in the def,
importing `random` at the beginning of the `shapes.py` file where the def was
stored, etc...), but nothing worked. Finally, I looked at StackOverflow to see
if there was some fundamental aspect of functions in Python that prevented what
I was trying to do. I had a suspicion that it had something to do with scope in
Python, maybe that globally-defined functions couldn't be called inside a def for
some reason. </br></br>

But I couldn't find anything. </br></br>

Finally, after hours of trying to figure it out, I realized something about my
def statement, shown below:

```python
def draw_random(turtle, rand, color = "black", lines = 10, line_length = 10, x = 0, y = 0):
  turtle.penup()
  turtle.color(color)
  turtle.shape("turtle")
  turtle.goto(x,y)
  turtle.pendown()
  for i in range(lines):
    turtle.forward(line_length)
    if ramd % 2 == 0:
      turtle.right(rand)
    else:
      turtle.left(rand)
  turtle.setheading(0)
  return rand
```

Do you see it? Let me zoom in on what I discovered.

```python
if ramd % 2 == 0:
```

Yep. I wrote `ramd`. Not `rand`. (As a side note,
I just found out that you can't use `<span style="color:red;"></span>`
in GitHub Flavored Markdown. That's a little disappointing.)</br></br>

Well, after cursing everything in sight, I got it to work by fixing the typo. I
then went on to make an even more randomized version, shown below:

```python
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
I'm particularly proud of this one. It draws a different shape every time, with
no need for input from the user other than clicking 'run'. I was planning to embed
this trinket in this reflection, but the 'Share' button on trinket.io wouldn't
work for me. Not sure what's going on with that.

## Final thoughts
The other important accomplishment I'm happy about is finally making a pull
request. I've been using GitHub for a little while, but I've never needed to make
a pull request before because I've only been editing my own code. It was nice to
finally hit that milestone in this class. I was also planning on using the Git
CLI to submit my reflection pull request for this week, but I read that GitHub's
built in request functions work a bit differently from requests submitted through
the command line. I'll probably test it out at some point in the next few weeks
myself, but for now I'm just writing the Markdown locally and pasting it into a 
new file on GitHub.

<em>Thanks for reading.</em>
