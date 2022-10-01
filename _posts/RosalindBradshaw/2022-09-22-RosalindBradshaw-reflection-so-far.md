---
layout: post
author: RosalindBradshaw
title: "Rosalind's reflection on the class so far."
---

I came into this class with very rudimentary, and rusty, skills in programming from a computer science class I took in high school. As such, I was a little apprehensive about jumping into an entirely new programming language. I remember, when writing my first few test-codes, fumbling around with the syntax and getting frustrated when things that I thought, logically, should exist within the code just didn’t work. For example, I wanted a program to have two turtles perform a single action, simultaneously. In my mind, I thought it should be as simple as telling turtle1 and turtle 2 to do something, and tried a number of variations of the term “and” to no avail. After that I started looking online and talking to a programmer friend which is how I found out simultaneous turtle commands are pretty much impossible in python. Another command that I knew should be possible, based on my previous coding experience, was the `if/then` concept. I tried messing around with that idea too for a bit, but put it aside when nothing was working. I knew that would probably come up later, though, so I knew I didn’t have to give up on it entirely.

I was pretty happy when I found out that `if/then` statements were now `if/elif/else` statements, something that I’ve been quite happy to incorporate into my current code projects. The real “lightbulb” moment for me, so far, was the `while` command. I had a program that I was working on that I wanted to be able to repeat, and a quick google search told me that loops were possible, but I wasn’t able to understand how to make them happen. Then `while` statements were briefly mentioned in class last week and that was when the loop idea clicked for me. That command, alone, has allowed me to refactor some of my code that was, previously, 192 lines long, into a section only 34 lines long. This also helped me streamline my workaround for the non-simultaneous turtles; giving each turtle a tiny instruction in sequence then having the entire sequence repeat for a number of times. I control the repeating by including an increasing variable so that the `while` loop only repeats for a limited time before moving on. An example of this code is what I call my Dancing Turtles.

The original dancing turtles had this code, repeated 14 times per action, for hundreds of line of code.
```
leo.left(5)
don.left(5)
mike.left(5)
raph.left(5)
```

The refactored code uses this:
```
def dance():
  n=0
  print ("Dance Party!!")
  while n<7:
    leo.left(5)
    don.left(5)
    mike.left(5)
    raph.left(5)
    n = n+1
    
  d=0
  while d < 4:
    r = 0
    while r < 14:
      leo.right(5)
      don.right(5)
      mike.right(5)
      raph.right(5)
      r = r+1
    
    l = 0
    while l < 14:
      leo.left(5)
      don.left(5)
      mike.left(5)
      raph.left(5)
      l = l+1
    d = d+1
    # print (d)
  
  n=0
  while n<7:
    leo.right(5)
    don.right(5)
    mike.right(5)
    raph.right(5)
    n = n+1
```
and that's the whole function!

An area that is still fuzzy for me are functions. Especially the more indepth uses of functions that call to other functions and process a variety of variables. There are a lot of capabilities in functions, and that is taking some time for me to work through to fully understand. I know that I’ll get it more as we keep working with them and as I keep using them within my own code and working through the textbook, I just have to not let myself get frustrated when I start getting overwhelmed. To deal with that frustration and feeling of being overwhelmed I’ve made sure to take frequent breaks, as well as going back and refreshing myself on earlier concepts. Another technique that helps me understand the concepts more is to write my own code involving them, just playing around with it and seeing what I can do. Usually, I’ll pull up a blank trinket and isolate the code to the bit that I’m working on so that I can experiment with it and troubleshoot it before incorporating it into the larger code that I’m working on for class. 

This is the interactive trinket I made with my dancing turtles code:
<iframe src="https://trinket.io/embed/python/55d48540c6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
