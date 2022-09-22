---
layout: post
author: alm7468
title: "April's Reflection on the Class So Far"
---

**What’s a lightbulb that has gone on for you? Give an example.**
The lightbulb moment I recall was when I realized I could use a second tab for function definitions in order to keep the main.py tab minimal and organized. We have covered this in class together now, but it felt clever at the time. I figured this out while using the code from Day 1 and modify it to meet my needs for the first homework assignment. I recreated the code of just the two desired shapes from the shapes.py tab.
	
  ex: shapes.py and week1Turtle line 15

Another realization involved having Tina include the user input into her messages.
	
  ex: lines 24 through 28


**Describe some confusion you’ve experienced. Did it help you learn?**
I was confused when using the tina.write command because I did not know what some of the parameters pertained to. 
For example, 
	tina.write("NOW", None, None, "50pt bold”). 
What was none specifying? (“text”, what?, what?, “font point and style”)
	example: TakeYourOrder line 41
I figured out the third parameter was alignment of text by observing line 20 from “Your First Python Program” in the Aug 25th Class Notes: 
	tommy.write("Welcome to INF 380P!", None, "center", "16pt bold")
Center immediately registered as alignment to me. I gathered this from my general knowledge of word processor formatting lingo. I still didn’t know what the first None controlled, so I resorted to Googling “python turtle.write parameters” and found this site: 
  https://www.bhutanpythoncoders.com/how-to-write-text-in-turtle-graphics-in-python/
Answer: (“text”, coordinated turtle movement, alignment, “font name, fantasize, and fonttype”)
I’ve also since learned that this write command is not the only acceptable format. This would also work:
	turtle.write("You win!", font = ("Arial", 30), align = "center")

**What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness?**
example: TakeYourOrder line 31-36
I wanted to pause Tina after she restates the order, this would allow the user to read the message, then produce a user input request (eventually a clickable response)  where the user confirms their order. 
Then the next comment Tina makes would depend on the user response (“if” parameters). 
I still don’t entirely understand how to pause Tina. I tried sleep and delay, but it slowed her and did not make her sit stagnant. I tried importing the sleep module from time like “Interactive Games” example on the Aug 25th Class Notes. I always get errors. hmmmm what am I doing wrong?
I ended up commenting the section away two weeks ago and not looking at it again.

**What problem solving strategies have been working for you? Give an example.**
Mostly trial and error, comparing my work to code examples from class, the textbook exercises, thinking in terms of the number scale/grid, being curious about what could be possible and how, Googling methods. 
