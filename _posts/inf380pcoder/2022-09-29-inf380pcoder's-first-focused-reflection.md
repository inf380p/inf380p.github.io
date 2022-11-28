---
layout: post
author: inf380pcoder
title: "Inf380pcoder's first focused reflection"
---

**Reflection**

My experience coding in class so far has had some ups and downs, which comes with learning anything new.  Learning new types of codes, and what can be accomplished using various function types, has been interesting. It gives you the ability to be creative and build fun programs. Getting to see other’s codes and how they came up with different ideas using the tools we’ve learned so far has been interesting as well. It gives you a sense of accomplishment when they actually work.  On the other hand when they don’t work, and you have to reread through the various codes to see where you may have made an error, it can also be a challenge. I’m finding that I’m understanding the basic concepts, and slowly making progress on moving through the concepts. 

Using the example I posted last week, I feel like I’m understanding how to build conditional statements and incorporate user input so that the user can choose multiple combinations of things, and there is then a response from the program for the possible responses. This includes choices such as the color of a background, the turtle color, how many sides you want your shape to have, if the user wants to color in the shape and, of so what color they want. For example, in an early program, one of my inputs simply asked the user to choose a color. To add more input layers here, I tried to input more questions: <em>(do you want to fill in the shape (yes, no?) If yes, then what color? if not, then print `x`).</em>

In going through the program, I also had to input error conditionals too, just in case the user accidentally input a value that wasn’t included in the parameters, which was something I experienced from inputting the wrong data a few times. I noted that if the user chooses a value that is beyond the scope of the choices given, it’s helpful to add an `else` statement to signal to the user that they should reenter the values and try again. One thing I also noticed going through this program was that I couldn’t fill in a shape while keeping the turtle the original color. For example, if the turtle is green, and you want your shape to be blue, the turtle then turns blue. So if you have `tina_color` as an input value, then the value changes after creating a shape. The only solution I could think of was just to have the turtle move directions after making the shape and then changed the color of the turtle back to its original color. The shape is still outlined in the original color, but I wasn’t sure how to fix that. 

````python
if shape_number ==('3'):
  if colorful =="yes":
    tina.fillcolor (color)
    tina.begin_fill()
    triangle()
    tina.end_fill()
    tina.penup()
    tina.left (90)
    tina.forward (50)
    tina.color (tina_color)
    print ("Good job!")
  elif colorful == "no":
    triangle()
    print ("Ok, no color")
    print ("Good job!")
  else:
    print ("Input is wrong. Please choose 'yes' or 'no'")
````

I know this code is simple and I’m trying to work on building more complex programs that have more features. I’m still working on wrapping my brain around inputting more of the functions from the homework assignments.  The chapter on functions had a lot of information, and I think I’m still trying to take it all in and figure out how to apply them to a turtle. As I mentioned in my last post, when I see code samples in front of me I can put it in order and orient it correctly, but when I try to do some of the coding questions from scratch it’s more challenging for me to put it all together. That’s probably still my biggest hurtle. There’s still some trial in error in inputting different functions and seeing what works and what doesn’t. 



**Here is my Trinket:** :turtle:

<iframe src="https://trinket.io/embed/python/404a62b956" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
