---
layout: post
author: elliott
title: "Final Project Guide: User Interfaces"
categories:
- reading
- how-to
external: false
---



# Interface Notes

These notes are intended to help you get an initial user interface sketch, to which you will add features. The advice varies slightly depending on the final project type you selected, since text and graphical interfaces are different.


**You may adapt code I've shared with you throughout the semester if you like.** When you do so, document where it came from, both as a component of good practice and so that you can discuss that decision in your reflection.
Data Processing projects, for instance, can use or expand upon the `interface.py` file included with a prior assignment. 

To use prior code, you'll need to understand how it's organized and how your subsequent code should adapt to it. If you use the dictionary-based menu structure from a prior example, for instance, that's how you'll want to add options to your main menu.

## Data Processors

Your interface consists of two things: A way of getting input from your user, and logic for what to do about that.

Your interface sketch probably mixes these together. That's OK! You're sketching.

But at this point it's probably a good idea to think about using functions to get user input if you haven't already. That way, things like ensuring the user made a vaild choice, etc, can happen all over your program, reusing your code. Here's an example of how that might look:
<iframe src="https://trinket.io/embed/python3/a72ec71424" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I wrote the `get_input` part of this sketch quickly, trying to see if I could ensure that a function would only return valid input if I gave it a prompt and a list. I could then use this function in a larger program to do that job repeatedly.

Then, I set myself the challenge of making the user input easier. I wanted to automatically provide choice numbers, and translate those to the text choice. I wanted the **API** of my function to remain the same. In other words, I wanted the function to have the same **parameters** and `return` the same kind of data. That lets me replace `get_input` with `get_numerical_input` throughout my program, making no other changes, and gaining the numerical input functionality.

So, in addition to suggesting a specific approach to collecting user input in text interfaces, this is an example of how you might start with an initial idea and improve it over time. The latter part is relevant to everyone.

## Turtlers

_Your_ interface is circumscribed by what kinds of user events Turtle can handle. Those are: key presses, clicks, and drags. We talked about methods of the `Screen` class before, `.onkey()` and `.onclick()`. The `Turtle` class also has mouse-based event handlers, `.onclick()` and `.ondrag()`. The click methods for both need to point to functions or methods that accept two parameters, `x` and `y` corresponding to the X and Y location of the click (or drag). **You don't need to do anything with these parameters if the location of the click isn't relevant.**

In other words, if you want to use a turtle as a button for the user to change something about your game, the fucntion or method you pass to `.onclick()` needs to take x and y parameters but might just set some variable or change some state of your game.


Here's a sketch that demonstrates Screen and Turtle event handlers, and uses a custom module:
<iframe src="https://trinket.io/embed/python/b91cc63e7e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

The animation code is separated from the rest of the game, and is imported. This keeps things organized.

I could also move some of the functions I wrote into other modules. BUT: be careful about what assumptions your functions make about variables that exist at that point in the program. Always move them one by one and test whether the program behaves as expected.

## Evolving your interface sketch

I got something usable above, then wanted to add a button. So, I **made a copy** and kept going. I got this:

<iframe src="https://trinket.io/embed/python/be0dcd052b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I added a class for turtle buttons. When clicked, they change Tina's color. The code that links my button with tina can't go in one of my custom modules, because `tina` gets defined in `main.py`.

I then noticed that when I clicked the button, `tina` would go there! That's not what I want. So I used an `if` statement to prevent tina from moving when the `y` value of the click is above `160`. This area of the screen is now I a place I can put clickable turtles. It's kind of like a menu area.

Note that there's only one function you can refer to in the Screen's `.onclick()` method. So, if you need screen clicks to do different things based on location, you'll need to write chained conditional (`if`/`elif`/`else`) statements to define that behavior. Or, like I did, 'turn off' part of the screen and put clickable turtles up there.

# Examples 

These examples can give you a sense of what I'm looking for.

## Data Processors

Check this example code for the kind of text-based interface I'm looking for:

<iframe src="https://trinket.io/embed/python3/b5c5eced6a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

You can use functions to respond to the options, or you could store the choice in a variable that's
passed to one function that changes its behavior based on logic you write.

You'll need to get your dataset inside the function, either as a parameter or as a global.

## Turtlers

Check out this example code that defines an interface in turtle:

<iframe src="https://trinket.io/embed/python/1eb70f077e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

(press run and then click or press up or down)

