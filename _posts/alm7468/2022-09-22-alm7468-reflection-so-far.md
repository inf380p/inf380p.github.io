---
layout: post
author: alm7468
title: "April's Reflection on the Class So Far"
---

**What’s a lightbulb that has gone on for you? Give an example.**  
1.) I realized I could use a second tab for function definitions in order to keep the main.py tab minimal and organized. We have covered this in class together now, but it felt clever at the time. I figured this out while using the code from Day 1 and modify it to meet my needs for the first homework assignment. I recreated the code of just the two desired shapes from the shapes.py tab.

2.) I noticed that the turtle had a cute name; I assumed that must be customizeable. After a photograph of multiple turtles I thought to duplicate the code with new names. I assigned each turtle a unique color to keep track of who was who.
    <iframe src="https://trinket.io/embed/python/56a9712d00" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>   

3.) Another realization involved having Tina including the user input into her messages. See lines 25 through 30 below:
    <iframe src="https://trinket.io/embed/python/baa7b987bc" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

**Describe some confusion you’ve experienced. Did it help you learn?**  
I was confused when using the tina.write command because I did not know what some of the parameters pertained to. 
For example, 
```python
tina.write("NOW", None, None, "50pt bold”). 
```
What was none specifying? (“text”, what?, what?, “font point and style”)

I figured out the third parameter was alignment of text by observing line 20 from “Your First Python Program” in the Aug 25th Class Notes: 

```python
tommy.write("Welcome to INF 380P!", None, "center", "16pt bold")
```
"center" immediately registered as alignment to me. I gathered this from my general knowledge of word processor formatting lingo. 
I still didn’t know what the first None controlled, so I resorted to Googling “python turtle.write parameters” and found this [site](https://www.bhutanpythoncoders.com/how-to-write-text-in-turtle-graphics-in-python/) 

This is what I learned: (“text”, coordinated turtle movement, alignment, “font name, fantasize, and fonttype”)
The first None was in a location that determined if the turtle would move along with the text, or not.
I’ve also since learned that this write command is not the only acceptable format. I've seen the format below and I think it works because you are directly specifying what each quality should equal and not relying on a pre-defined function:
```python
turtle.write("You win!", font = ("Arial", 30), align = "center")
```
**What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness?**
Example:
    <iframe src="https://trinket.io/embed/python/baa7b987bc" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I wanted to pause Tina after she restates the order, this would allow the user to read the message, then produce a user request (eventually a clickable response) to confirm their order. I currently use an input line to stop tina at this point and confirm with a typed Y or N. 
I still don’t entirely understand how to pause Tina without input(). Delay only slowed her down, it did not make her sit stagnant. I've tried sleep but recieved AttributeError: 'Turtle' object has no attribute 'sleep' on line 32 in main.py. I tried importing the sleep module from time like “Interactive Games” example on the Aug 25th Class Notes. Again, errors. hmmmm what am I doing wrong?

**What problem solving strategies have been working for you?**
- Mostly trial and error
- Context clues, since Python is human friendly
- Comparing my work to code examples from class
- The textbook exercises
- Being curious about what could be possible and how
- Googling code key terms
