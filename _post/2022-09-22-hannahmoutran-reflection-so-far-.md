---
layout: post 
author: hannahmoutran
title: "Hannah's reflection on the class so far."

# Lightbulb Moment 
I think the real lightbulb has been realizing that, most of the time, the error is caused by a punctuation mark that is missing or a capital letter or an extra space that means that Python doesn’t recognize what I am referring to.  That said, there was also the misunderstanding that I had of how to speed up my turtle. 
 
Originally, I wrote this: 
turtle.speed (0)

That made it faster than it had been, but still slow as molasses.  

The solution was to write this instead, using the name of my specific little turtle that I created: 
tina.speed (0) 

# Confusion I have experienced.  Did it help me learn? 
I want to say no to this, because I wish that there were no confusion and I just learned in this very stress-free, one thing after the other manner.  However, yes, I am finding that when I run into problems, I do end up learning a lot.  As an example, in the beginning, I made every plank of the bookshelf by making a rectangle and filling it in.  It worked, but it was really hard to keep track of where I was in the screen grid, and also my turtle would sometimes end up turned the wrong way.  I ended up making a plank function, so that was easier and made it simpler to keep track of what way the turtle was turned.  

```
#Here's my plank function  
def plank (x=-150,y=150):
	tina.penup ()
	tina.goto (x,y)
	tina.pendown ()
	tina.fill (True)
	tina.color (bookshelf_color)
	tina.forward (300)
	tina.right (90)
	tina.forward (10)
	tina.right(90)
	tina.forward (300)
	tina.right (90)
	tina.forward (10)
	tina.right (90)
	tina.fill (False)
```
To make all the horizontal planks of my bookshelf now, all I need to write is this: 
```
#here's my bookshelf
plank (-150, 150)
plank (-150,75)
plank (-150,0)
plank (-150,-75)
plank (-150, -150)
```
And now, to do all the vertical planks of my bookshelf (just the sides) all I have to do is change direction once, and call the planks again: 
```
#direction change
tina.left (90)
plank (-150,-160)
plank (140, -160)
```
Still, while doing the cactus and flowers, I realized that sometimes I didn’t remember how many degrees I needed to get back to wherever I wanted the turtle to turn.  So, I googled a bit and found this line of code will turn the turtle (tina) to the direction of my choice.  The cheat sheet to this is that 0 makes the turtle face east, 90 makes it face north, 180 makes it face west, and 270 makes it face south.  For example: 
```
tina.setheading (0) 
```
I use it at the end of the code where I give choices to call the flowerpot or cactus functions, so that no matter what is called, it goes back to facing east afterwards.  

Here it is in my code: 
```
if whatplant == "cactus":
	print cactus (70,76)
	tina.setheading (0)
elif whatplant == "a cactus":
	print cactus (70,76)
	tina.setheading (0)
else: 
	print flowerpot (70, 76)
	print flowers (78, 138)
	tina.setheading (0)
``` 
So, yes, confusion has definitely been the impetus for learning. 

# What is still fuzzy for me, and what can I do to work on it? 
The concept of try/except is still tough for me.  I think practicing is the only way to get better at it, maybe going back to the book, looking to see if anyone has written or shot a video simplifying the topic.  

# Problem solving strategies that have been working for me. 
Looking things up online, trying a bunch of stuff, taking a break, asking my husband who is an app developer (last resort, but he is a good resource), and looking back at my notes.    



---
