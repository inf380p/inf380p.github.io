---
layout: post
author: rabouti
title: "Rabouti's first focused reflection"
---


My favorite part of this class is the unlimited amount of creative freedom that is encouraged. I loved the first day of class when we immediately jumped into editing/changing codes on the class website. I realized that coding had a lot of creative/artistic potential and that gaining fluency in Python was actually going to be more feasible (for myself to figure out/learn) than I anticipated. I've had a lot of fun exploring and strengthening my artistic abilities in tandem with gaining fluency in/experimenting with Python. 

It's been a real challenge trying to organize my random and chaotic thinking patterns to articulate the processes I went through while coding (i.e., the method to my madness). For example, I made my "random design" program (embedded below) during the first week of class and have been refactoring/perfecting it since then - given the new information and coding techniques we've built upon. 


 <iframe src="https://trinket.io/embed/python/ac50ff4b89?outputOnly=true&runOption=run" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
 
 



Since I was a complete novice upon being in this class, my "random design" simply started with me experimenting with the current level of fluency/information I had at my disposal. Hence, I experimented by changing the background color multiple times, creating designs with multiple circles (without loops), creating a design by stamping the turtle 8 times in a circular motion, and repetitively using other various methods (penup, pendown, forward, backward, left, right). While I was writing and experimenting with code for the first time, I used a lot of code that was very repetitive and I remember thinking, "There has to be an easier/more efficient way."  

With my new and (slightly) more advanced status, I've incorporated functions and loops to make the main lines of code in my “random design” program more organized, efficient, and manageable. Each class session, we learn something valuable which has helped me continually pinpoint new, more efficient ways to refactor my “random design” program (and other programs I've written). For example, up until today (09/29), “arguments” have been fuzzy for me, and as a result the functions I’ve written were not as usable or efficient as I knew they could be. Logically, I understood the purpose of arguments and parameters, but I wasn’t confident in how to appropriately incorporate them in my custom functions (which now makes me feel silly).  After the hands-on practice and visual guidance from class today, and by simply watching Dr. Hauser effectively write a function with arguments and parameters, I instantly recognized what I needed to change about my functions in my “random design" program and how to appropriately utilize arguments to make my functions more generalizable. Which, in turn, has allowed my program to create the same designs with varying parameters multiple times (with a singular, more general function). Hence, I learned how to define more efficient and usable functions by diagnosing a fundamental misunderstanding on my end.  

Below I have provided my original/less efficient function and my new/more efficient function that create a design using multiple circles: 

 

Less efficient function: 

```
 # Look what I did here
 def draw_circle_loop():
    for i in range(8):
        tina.left(45)
        tina.circle(100)
 draw_circle_loop()
 ```
 
I only implemented this function 3 times throughout my program. Before I refactored my "random design" (the first time) with the use of this function, I had 271 lines of code. After utilizing this (less efficient) function, there were 132 lines of code.


More efficient function: 

```
#Look what I did here
def draw_circle_loop(left_degrees = 45, circle_size = 50):
  for i in range(8):
      tina.left(left_degrees)
      tina.circle(circle_size)
      
draw_circle_loop(left_degrees, circle_size)
```

I implemented my new function 5 times, and now there are only 119 lines of code - which is definitely progress. 


Another challenge I’ve experienced in this class is using the readings/textbook to learn new techniques and concepts, for I’m a very visual and hands-on learner. While the readings are interactive, it’s still more beneficial for me to learn by seeing and doing (in-person), opposed to reading about “how to Python.” For example, my misunderstanding regarding functions and arguments was instantly resolved when I watched Dr. Hauser write a function with arguments (containing loops) today in-person. To resolve this issue, I’m going to make it my mission to incorporate more visuals and hands-on practice while reading the textbook (since this class has a flipped design) and utilizing the additional resources provided in the syllabus.


I'm excited to learn more about designing games, learning how to effectively use modules and how to write reflectioins that better encapsulate my creative process while writing programs. 



