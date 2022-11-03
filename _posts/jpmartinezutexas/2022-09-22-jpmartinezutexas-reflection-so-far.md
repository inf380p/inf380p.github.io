---
layout: post
author: jpmartinezutexas
title: "JP's reflection so far!"
---

# Reflection
Welcome to my reflection! I am glad you made it this far. I am happy to be in this class, and feel that I am learning at a pretty good pace. Git and github always seemed complicated to figure out, so the fact that I am now typing and building my own is very exciting for me. 

One interesting thing I have learned in the class so far is that if you don't have the answer, don't fret. It's out there. I have used the book as well as various websites like the raspberry pi website to get answers about code, and my classmates have been helpful as well. An example I have embedded below was the sleep function. I was not sure how to get my Turtle to just pause everything for a bit, but my classmate right next to me was helpful and simply told me "Use the sleep function". 

A learning moment I had was when I was trying to beef up a turtle, and had added everything except for the import function (for input random), it taught me to make sure you have everything, you can't just slap code in and expect it to work.

Something that kinda confused me at first was the concept of indenting. It makes sense definitely, but sometimes I forget where to indent, specifically how many indentations a function of code needs. I am not too worried about it, I am sure that I will get better in time, and the book as well always has exercises, and not only where the code goes but how far indented code goes is included, which I appreciate.

Something I have been doing to make sure I don't completely lose all my code at any point is to have multiple versions of files saved, I believe this is waht they call version control. That way when I experiment, I can always go back to my code that 100% works, and see where it went wrong on my experimental code. I also usually just comment out my code rather than delete it, although when I need to turn in big projects I will be sure not to leave excess code. I have also used # generously to tell myself what it is I'm working, on such as below.
```python
#printing intro function
def print_intro():
    print("This is my code")
    print('It is improved by functions')
print_intro()
```



## More Interactive Code

<iframe src="https://trinket.io/embed/python/78925de442" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

```python
# Here's an example of a function I made to make a random colored square at any location of my choice. 
def go_draw_square(x, y):
    tina.color(random.choice(colours))
    tina.penup()
    tina.goto(x,y)
    tina.fill(True)
    tina.right(90)
    tina.forward(100)
    tina.right(90)
    tina.forward(100)
    tina.right(90)
    tina.forward(100)
    tina.right(90)
    tina.forward(100)
    tina.fill(False)
    tina.pendown()
    # Now all I need to draw a square is to put this! It really saves a lot of space coding.
    go_draw_square(0, 0)
```

```python
#This is an example of the sleep function, I had to import the time function first. A student helped me implement it. I wasn't even aware of the sleep/time function until they mentioned it. It makes my turtle sleep for 5 seconds 
import time
time.sleep(5.0)
```

Thinking ahead for my final project, I really want to do either a text based adventure game, or maybe combination of a text adventure with the turtle function. The turtle seems so robust, I am interested to learn more about it.

