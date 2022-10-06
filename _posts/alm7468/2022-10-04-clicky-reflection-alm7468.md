---
layout: post
author: alm7468
title: "April’s Clicky Reflection"
---

I’m trying to do a simple I-Spy point-and-click game experience. 
I created the intro setup where 4 options are presented. The user is prompted to double click one option (double clicking is a way to incorporate the required trinket screen click + user selection click). The screen should clear, the puzzle image becomes the background, and the user is prompted to click on a particular item. 

***Main Obstacle:***  
_(starting point)_ The screen is clearing but the next function is not operating properly. For now, I am just asking the screen to turn a color. Once it is operating properly I will continue to build the details.
_(progress? not really)_ I now know that ```screen.clear()``` is stopping anything from showing on the screen after that function executes. I figured this out by commenting out screen.clear() for the green door and watching what happened when I chose that door. The green_door() tester function executed finally. So now I think I need to clear tina, not the screen.  
(that did not work.)
_(baby step one)_ My only advancement has been adding a tracer/update feature to my setup.
_(baby step two)_ Now I have inserted the I-Spy image as the background.

I think I want a line on the bottom of the screen to ask for each item, maybe I should include a time clock that counts down per turn to make the game more exciting.

Curious— How do you sort the layers (image, text, turtles) on the screen?

***TO-DO:***  
I have written a bunch of comments in my code with my intentions. Below are some current areas of concern.  
- clear setup once clicked by user, then start Puzzle output functions  
- make sure no history is present so that we don’t navigate to other puzzles when clicking the item asked for.  
- define item coordinates, create an if/else response.   
  - if user clicks correct item, within time frame— success! then clear screen and identify new item coordinates, then refresh to a new item search prompt.  
  - else “That’s not what we were looking for, try again!”  
- create count down clock that, when hits 0, communicates failure and loops to setup()  

<iframe src="https://trinket.io/embed/python/31b57ff962" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
