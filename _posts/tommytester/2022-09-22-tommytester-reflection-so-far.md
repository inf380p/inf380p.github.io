---
layout: post
author: tommytester
title: "Tommy's reflection on the class so far"
---

Then, under the hyphens, put the content of your post, and format it so that your interactive 
code and static code blocks will show up.

# Reflection Text  
Include your pre-composed reflection on the class so far in the post. You can paste the text 
into github and click on the Preview pane to see what it will look like. From there, you’ll 
need to do a little bit of reformatting.

## Interactive Code  
To include embedded interactive trinkets in your post, go to your Trinket program(s) and 
follow the instructions here to get the embed code.

Then, paste the code into the text of your post. At this point your post will look something 
like this:

<iframe src="https://trinket.io/embed/python/c26c35e489?start=result" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Here's the `draw_circle` function:

```python
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
