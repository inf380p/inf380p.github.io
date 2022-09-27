---
layout: post
author: martsale
title: Alexis's First Focused Reflection
---
# A Reflection On Using Logic In Code

For the *Logical Turtle Exercise*, I created a program that would give the user a customized ice cream cone.

<iframe src="https://trinket.io/embed/python/e1f1be2a97" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Getting Started

One of the most difficult aspects of creating this program was figuring out where to get started. I had the idea in my head of what it would look like, and I needed to parse out which components to start with to make sure that it worked consistently as I built the program. It was really tempting to just start from what I anticipated the top being and work my way down, but I realized that I needed to ensure that all of the parts worked in incremental sections. I started by creating the visual components for the ice cream scoop, the bowl, the cone, and the cherry. Once I ensured that the components were the shape I wanted, I moved on to making them line up.

After getting the componets created, I started to work on the logic statements. To ensure that the logic was running correctly, I hard-coded variable values into the beginning of the program to make it easier to see what was happening. 

Once I was sure that the logic was in place, I added the user inputs to allowe the user to control what type of ice cream they are looking for.

## Debugging

I really struggled with getting the logic to flow correctly. The boolean wasn't checking the values appropriately, and defaulting to the first choice. To confirm what was happening, I added print statements to test out what was going on behind the scenes. I eventually directly called the user input into a string function, and I believe along the way, I fixed the boolean operator to be "==" 
instead of "=". After watching a peer's code get edited in class, I realized that I could take out the conversion and the code still worked. 

Another challenge that I did some light error checking for was allowing multiple types of capitalizations of the user's choice to trigger the right answer. After reading about string functions, I believe this would be easy to go back and refactor for the capitalization of the string instead of calling out multiple options using "or".

```
if strFlavor == "chocolate" or strFlavor == "Chocolate":
  flavor = "brown"
  print("you chose chocolate")
elif strFlavor == "strawberry" or strFlavor == "Strawberry":
  flavor = "pink"
  print("you chose strawberry")
else:
  flavor = "yellow"
  print("you chose vanilla")
```

The example above demonstrates allowing multiple capitalizations for the flavors as well as printing the flavor that was chosen.

After writing this reflection, I realized that I should comment out old code or duplicate my program when I'm making large changes. A lot of the code I wrote originally that didn't work efficiently or was no longer needed for debugging so I deleted it. I effectively took away my documentation of the problem solving process, which could make it difficult in the future to go back and compare if I'm getting a similar error.

## Overall

I really enjoyed working on this assignment. In class we talked about building a little bit of delight into the projects to keep learning python more engaging. It was fun to ideate on a concept that would be engaging with users and fun to build out. Working out how all of the pieces worked together regardless of what answer was chosen was a fun thought experience.

## Next Steps

If I choose to refactor this project, there are a few areas where improvements could definitely be made. The first would be creating more detailed graphics. This project had very basic shapes and colors because I was focused on the function of the program more than anything else. Ice cream certainly wouldn't be perfectly round, and cones have a texture that could be drawn on.

I would also want to include functions for each component next time. Creating the components as functions could intake multiple ice creams instead of just one. This could simulate ordering for a family instead of an individual. 

Another option could be adding a for loop to create more than one scoop of ice cream per order. While we haven't directly learned loops yet, I believe I could ask the user for how many scoops they want and use a loop to keep drawing scoops within a certain scope that I determine. 

