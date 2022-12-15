---
layout: post
author: nemothefish260
title: "First Reflection: The Class So Far"
---

**What’s a lightbulb that has gone on for you? Give an example.**
My lightbulb moments mostly consistent of getting over the mental obstacles of feeling anxious about code. One technical lightbulb I guess would be realizing that 
coding is not innate and if even experts can make mistakes (such as missing a bracket) then it's alright for me to do the same. So now instead of panicking I just 
look for the 'small' errors and try to see how different objects and pieces of code are interacting with one another to identify where the 'break' could've occured.

For example, I was struggling to make the following function work because I was assigning it more arguments than I had defined for it while trying to draw the leaves
for a flower drawing. Just that small fix of making the data consistent with the function helped my code.

```
def draw_oval(x,y,big_radius,small_radius,tilt)
```

**Describe some confusion you’ve experienced. Did it help you learn?**
I was confused as to how the basics we have learnt so far relate to my career choice as a UX/Ui designer. However, after reading about it, I realize that I can approach
the code I create from a user-centric perspective and see how clunky and inaccesible interfaces might impact user-behavior.

**What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness?**
The act of physically writing the code and the use of math in my programs (e.g. to create a function that triggers a scorekeeper when turtles come into contact or loops
that would allow me to make drawings) is extremely confusing for me. My first porgram which I have linked below involved writing a very long code for a small animal drawing.

        dodo = turtle.Turtle()
        dodo.speed(0)
        dodo.color("black")
        dodo.circle(radius = 50)
        dodo.pu()
        dodo.goto(-30, 90)
        dodo.pd()

        dodo.fillcolor("black")
        dodo.begin_fill()
        dodo.circle(radius = 15)
        dodo.end_fill()

        dodo.pu()
        dodo.goto(30,90)
        dodo.pd()
        dodo.circle(radius = 10)
        dodo.pu()
   
   Since I don't have a tech background, coding gives me a lot of anxiety and therefore leads to procrastination. At the same time, I know that I only need to divide
   my work in smaller steps so that I can create positive reenforcement by accomplishing small steps.
        
**What problem solving strategies have been working for you? Give an example.**
I think I just need to reiterate and watch tutorials (as opposed to read about code) because, as a visual learner, I will understand more through replicating what is shown.
For example, it's important for me to see a visual sample of code that uses loops and conditionals to understand the logic as opposed to reading about it in a book.
