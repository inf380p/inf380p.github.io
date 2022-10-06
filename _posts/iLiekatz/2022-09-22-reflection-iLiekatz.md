---
layout: post
author: iLiekatz
title: "iLiekatz's Reflection on the Class So Far"
---

Here are the two program I'm embedding:

<iframe src="https://trinket.io/embed/python/d0628d545f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
<iframe src="https://trinket.io/embed/python/022fb77027" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Getting into the swing of learning code, and being disciplined with spending time on it every day has been a struggle. As I have gotten better with it over the past few weeks, I can really begin to see how spending small chunks of time over a week has helped me progress tremendously. I feel like the past few weeks has been a multitude of small lightbulb moments. They have been more of “Duh, I knew that!” than crazy insightful ‘A ha!” moments. But the culmination of all these moments has been huge I think.

My first turtle program seemed so tedious, and I just felt like I was wasting my time and there was a better way to do it. My program has almost 400 lines of code, almost identical lines to each other. 

Basically my first program was this, repeated 40 times!! 

```
#Look what I did here:
tina.penup()
tina.goto(150,150)
tina.pendown()
tina.fill(True)
tina.pencolor("#b497d6")
tina.circle(10)
tina.color("#b497d6")
tina.fill(False)

tina.penup()
tina.goto(45,80)
tina.pendown()
tina.fill(True)
tina.pencolor("#b497d6")
tina.circle(10)
tina.color("#b497d6")
tina.fill(False)
```
This week's refactoring assignment was a really great moment for me. I knew there had to be a better way, and I was right!

```
def wisteria_turtle(x, y):
    tina.penup()
    tina.goto(x,y)
    tina.fill(True)
    tina.pendown()
    tina.pencolor("#b497d6")
    tina.circle(10)
    tina.color("#b497d6")
    tina.fill(False)
 
wisteria_turtle(0,0)
wisteria_turtle(150,150)
```

I was able to take my first program, define 5 different variables, and call them each instead of the time consuming way I had done it the first time. And best of all, it made sense why I was doing what I was doing. In class talking about the concepts has been hard for me to wrap my head around. But when I go home and I practice the code myself, things really begin clicking.

I had a strange error on this week's assignment. My code called for the pen to go to (x,y), and when I ran multiple lines of my code that included (-) values for either x or y  I was receiving an error that I could not understand. To fix it, I commented off all my lines of code. Without changing anything, when I uncommented line by line it worked! So, I am still fuzzy on what was going on and what I even did to fix it. I would like to try to recreate what was happening and spend some time diving into that rabbit hole to understand more. 

I have been having to do a lot of debugging of my code. I have found the keyboard shortcut to comment off multiple lines of code at once extremely helpful for this. It has allowed me to narrow my window of focus more efficiently. Looking at a lot of lines of code can be a little overwhelming visually for me to understand, so when I am able to narrow my focus to one thing at a time I am better able to put together the whole picture. 


