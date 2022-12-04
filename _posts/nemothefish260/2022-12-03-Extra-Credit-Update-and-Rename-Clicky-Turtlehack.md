---
layout: post
author: nemothefish260
title: "CLicky Turtlehack"
---

**Link to my Clicky Turtlehack program**
https://trinket.io/python/e636857dc0

**Rationale for the Update**
I am updating the code for my clicky turtlehack because of two reasons. Firstly, I have partially lost the code on my previous clicky turtlehack (forgot to save it).
Secondly, it was merged incorrectly.

**New Features and Issues**

This time, I have added some text-based narrative to my code to give the user more context about the maze game, where a turtle is trying to run away from his teacher,
because he forgot to complete his homework.

I have also added a function that triggers another turtle to display dialogue on-screen in the beginning and write "YAY! I HAVE ESCAPED ACADEMIC TYRANNY!" at the end of
the game depending on the turtle's distance from a particular coordinate. However, this function is not perfect since one has to be fairly close to the coordinate to 
trigger the event intended.

The code I am using for this purpose is given below:

  while True:
  if math.sqrt(tina.pos()[0] - 0)**2 + (tina.pos()[1]- 154)**2 <100:
    sally.write("YAY! I HAVE ESCAPED ACADEMIC TYRANNY!", "Verdana" , "right", "12pt bold")
    
**Lightbulbs**
At the time of writing this code, I am definitely not a 'pro'but the anxiety around typin meticulous code into the screen has significantly declined. Now I am only
treating the coding process as a matter of looking at different recipes for a dish to create one that suits my taste. I hope I am able to continue this attitude till
the final submission. This is definitely a huge leap for someone who majored in literature and still is not the most technologically skilled. 

When Professor Eliot talked about feeling anxious about having to start from zero as an adult, I could relate to that since I am in the middle of transitioning careers
and learning code is a part of that proces. However, I feel more confident in my ability to learn technical things now.
