---
layout: post
author: inf380pcoder
title: "Inf380pcoder's first reflection post"
---

Reflecting on the last few weeks, I think there are a few things that make more sense to me now compared to the beginning of class. Coming in to the class with no prior experience, I'm finding the coding syntax to be more clear now. Early on, when I saw code listed out I had wondered why some things were oriented differently and why there were error messages if things weren’t lined up properly. Now lining up the statements correctly makes more sense as a way of avoiding syntax errors. Forming shapes and designs in turtle makes more sense now, having had more time to practice with it. The conditional statements, and how to set them up properly, make more sense to me as well. Using some of the functions like “def”, and being able to define multiple shapes and call them if given a specific input from the user, is helpful too. I was looking at how to do “for” loops and I found them to be a helpful and more efficient way of creating the shape output. 


**Example:**

I've found that functions like “def” and “for” loops are useful because you can set a value and recall if later if needed or if certain input from the user is given. 

```python

shape_number = input ("How many sides should the shape have: 3-10?")

def triangle():
    for i in range(3):
        tina.forward(100)
        tina.right(360/3)

if shape_number ==('3'):
  triangle()
```

**Example:**

Conditional statements also make more sense now. They allow you to lay out different possible actions in the program, depending on what the input from the user is (if that’s something you’re incorporating). 

```python

colorful=input ("Do you want to color in your shape - yes/no?")

if colorful =="yes":
  color=input ("Enter the color of your shape")
  tina.fillcolor (color)
  tina.begin_fill()
  for i in range (num_sides_int):
   tina.right(angle_sides)
   tina.forward(side_length)
  tina.end_fill()
elif colorful == "no":
  print ("Ok, no color")
  for i in range (num_sides_int):
   tina.right(angle_sides)
   tina.forward(side_length)
else:
  print ("I don't understand. Please enter 'yes' or 'no'")

```
The toughest part of coding so far, which still causes some confusion at times, is just working through the concepts. The biggest cause of frustration is just being able to reproduce some of the code types on my own while avoiding errors. Learning code does feel like learning a new language. When you first learn a language, it can initially be easier to understand what people are saying to you, but more challenging to reproduce it back. That’s how I conceptualize learning coding so far. I can grasp the concepts in the homework and if I see the possible answers, I can usually decipher what the correct answer is. However, when I’m just given a blank canvas to code with, I have a harder time reproducing the right code from scratch. I usually have to go back and reexamine how to begin the statements before it starts to come back to me. Also, math has never really been a strong suit of mine, so I’ve had to spend more time on the of the math-focused concepts and breaking down the story problems in the homework step by step. I think this is just part of the process of learning and the more I do it (hopefully!) the easier it gets. 


Some of the things that have been helpful for me have included watching YouTube videos on things that are a bit unclear. I find it helpful to see people explain things as they are inputting the code. I think it helps me to better process some of the concepts. I’ve had similar experiences in courses that I’ve taken which have had a technical component. I tend to learn best by seeing the concepts worked through, and being able to rewatch things multiple times if necessary. Taking regular breaks and doing homework assignments in chunks has also been helpful. With many new concepts being introduced, I find that working a little bit at a time and pacing myself truly does help. If I find that I’m getting a lot of error messages or the concepts aren’t sticking, its usually because I’m tired and am not being as careful in my proofreading or am just too overwhelmed. In those cases, taking a break or coming back the next day does help me to see the problem with fresh eyes.

Here is one of my functional turtle codes: :turtle:

<iframe src="https://trinket.io/embed/python/404a62b956" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
