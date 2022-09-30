---
layout: post
author: RosalindBradshaw
title: "Rosalind Bradshaw's First Focused Reflection"
---


So far, the most challenging/frustrating/fun piece of code I’ve written, or tried to write, was trying to get multiple turtles to perform the same action.
I remember we talked about this, briefly, very early on. I knew that in the future I’d likely want to have turtles doing simultaneous actions, and I wanted
to figure out how to make that happen. In my first reflection I mentioned thinking it should be as simple as telling turtle 1 `and` turtle 2 to do something,
and tried a number of variations of the term `and` to no avail. After that I started looking online and talking to a programmer friend which is how I found
out simultaneous turtle commands are pretty much impossible in python.

But what isn’t impossible is coding two turtles to do something so closely together that it looks simultaneous, as I did with my dancing turtles code.
But, this can also be used in a more subtle way as well. For example, in this code:

<iframe src="https://trinket.io/embed/python/44f0fbd215" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


Just looking at the code, it’s not all that impressive. Two turtles draw a small rectangle. In fact, for just that purpose the code is super inefficient.
Why have two turtles do the job that just one can do?

The reason is this:
```
#Tina
tina = turtle.Turtle()
tina.hideturtle()
tina.speed(0)
tina.color("blue")

#Raphael
raph = turtle.Turtle()
raph.shape("turtle")
raph.speed(0)
raph.penup()
raph.color("red")
```

By having two independent turtles, I can have one, invisible turtle, mirror the movements of the visible turtle, but draw in an independent color.
That’s how the red turtle, Raphael, “draws” a blue rectangle. In reality, Tina is drawing the rectangle, Raph’s just moving, but because they are each
taking tiny movements in sequence, it appears as though it is simultaneous.
Drawing this way takes an enormous amount of coordination, much like early animation where hundreds of pictures with minute details run at a high enough
speed made it look as though the image was moving. If either turtle moves too far too quickly the drawing lags behind or jumps ahead, breaking the illusion.
So why not just use the `fillcolor` command?

<iframe src="https://trinket.io/embed/python/a051178309" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


As you can see in this code, modified from the one above, the `fillcolor` command makes it so that Raph is blue with a red outline, just like the rectangle
he’s drawing. Not the tidiest look, in my opinion. Likewise, including a `pencolor` command changes Raph’s color entirely, and still has the same outline
issue. So, I made Raph red, the invisible Tina blue, and have them pseudo-simultaneously draw the same rectangle, allowing me to make the rectangle whatever
color I want while keeping Raph an entirely different color.

In actuality, this piece of code is just one tiny bit of a much larger code to have four turtles appear to build a house. Each of the four draws a section
in parallel with Tina and allows the user to input the color of each of the four turtles, and the colors of all the sections of the house. Thereby allowing
the user-dictated turtle colors to remain the same but allowing Tina to invisibly change colors and color the house independently, thus creating the overall
illusion that the turtles are drawing a house wildly different colors from their own.

Full Turtle House code:
<iframe src="https://trinket.io/embed/python/d2576675b5" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>



