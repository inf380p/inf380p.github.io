---
layout: post
author: martsale
title: "Alexis's Reflection on the Class So Far"
---

#Learning Python Thus Far

Creating functions has been a really fun learning experience to try and optimize the programs that I've been writing. I first looked at functions weeks 2-3 to try and figure out how to create multiple circles in the custom turtle application. I was really confused about what the arguments meant at the time. Having gone through the Runestone chapter, it all makes a lot more sense and has given me a new tool when problem solving. 

One of the biggest difficulties I've consistently experienced when doing the book work is struggling to keep up with the math. It's been a really long time since I've taken a real math class or had to apply a lot of math, so that's slowing me down morethan the pragmatic programming. I've found that slowing down and really reading what is being asked of me makes it easier to work through those specific problems. 

#Some debugging experience

I also got some good experience at debugging for the week that we were accepting user input to change pieces of the program. I had somebugs that I couldn't figure out, and including print statements helped me understand where the program was and was not running. Addingin "permenant" declared variable expedited the development process as well when working with parameters that would typically beinputed from the user. I honestly don't know what the specific problem was, but after making a few code changes based on the print statements, I was able to get the code to run in the flow of control that I expected. 

#Refactoring for the first time

I chose to refactor week 1's basic turtle remix. In the first program, I copy and pasted a lot to create 7 hexagons. In the first program, I just rotated the hexagons around to fit together: 

<iframe src="https://trinket.io/embed/python/ac7bddac09" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

When refactoring, I created a hexagon function. This made the code a lot easier to call, however it required rethinking how the hexagons would be drawn. Instead of starting where the last one ended, I had to calculate the distance between hexagons to get them to line up while the hexagon was drawn in the same orientation every time.  

I also added some user input in a second function in the refactoring, allowing the user to control the turtle color, name, background color, and what the turtle says:  

<iframe src="https://trinket.io/embed/python/9e790ea83a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>  


#In conclusion

So far, I'm really pleased with the progress I've made in the course. I've come a long way with understanding and writing python. Functions are such a fundamental part of code, and it was really daunting to think about learning them so early in the semester. However,taking them in bite-sized pieces has helped a lot. 
