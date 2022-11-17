---
layout: post
author: alm7468
title: "Final Project Progess Update"
---
# Turtle, Two Game Program
I am developing a program containing 2 games  
game 1 is a click event game similar to the concept of wack-a-mole  
game 2 is a key response game similar to a typing test

## Where I am right now:

I've been setting up the games in a more simple interface, using only on module to reduce time spent on errors, since I know that trips me up. Here is how that is looking:
<iframe src="https://trinket.io/embed/python/b6c52eecb1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>  
 
### What I have accomplished so far:
- set a screen size and background color
- (menu) established menu dictionary successfully
- (menu + user input) defined the process of selecting a game with user input
- (game 1) mapped out where the black dots (representing holes) are located
- (game 1) created the target turtle (called "it" based off of the concept of being "it" in tag), made it red. I will likey import a tiny image to replace the red dot later in order to meet assignment requirements.
- (game 1) mapped out and created a temporary cycle of movement at a desired speed for "it". I have the program breaking after one cycle of location possibilities.
- (game 1) define a score keeper and display on bottom screen
- (game 1) create response to clicking that adds point to score counter
- (game 2) created the screen set up with a line of instruction
- (game 2) display random letters from a random choice method
- (game 2) clear the screen between letters displayed


### My next milestones list is:
- randomize "it" movement in game 1
- focus on adding levels
- incorporate an image
- create user key response in game 2, this feels ambious because I have to figure out to define the moment when user key matches the randomly generated key and I'm not sure what the limitations are there. Does the program recognize the individual letters displayed? How will the linear running quality of python limit the ability to check for matches every 1-2 seconds as the letter changes?
- migrate everything into a multi-module program for a clean look

### Project Expectations check list:
- ✅   Dictionaries
- ✅   definite (for) loops
- ✅   Custom functions
- ✅   A Python 3 or Pygame (Python 3 + GUI) Trinket. For Turtle projects only, a Python trinket with the #!/bin/python3 shebang enabled is acceptable.
- ✅  Have a graphical user interface, responding to key and click events
- ✅  Display information about the program’s state such as score or level
- ✅  Have an iterative interface. That is, the user should be able to perform any number of supported actions (such as playing the game over and over)
    - _I think I've done this by looping back to main menu at the end of game_over()_ 
- Custom modules  
   - _I will migrate game 1, game 2, and interface into separate modules_ 
- Have a constantly available help dialog. This can take many forms but should allow the user to learn what they can do in the program at any time.
- Have at least 3 levels, increasing in difficulty
- Extend a custom Turtle Class  
    - _I can do this to one of my many turtles (writer, dotty, it, or keeper)_
- Have a ‘win’ screen  
    - _Maybe add happy, congratulations image here? When user reaches certain score_
- Use one or more custom images  
    - _I think I will do this on the 'win' screen_
- At least one external data file. For Turtle, this can be game settings, character data, or etc. For the data tool, this should be your data.  
     - _need to figure this out_

-----

# Here is an example of an issue I worked though at the beginning of the development process:
I have established a small menu of options as
```py
#main menu
menu_dict = {
  "1" : "Dot Game",
  "2" : "Letter Game",
  "3" : "Exit Program",
}
```
Next I will ask the user to make a selection by sending it to a function in the details.py module with `choice_str = details.get_menu_choice(menu_dict)`
I have structured `get_menu_choice()` like our csv exercise.
```py
def get_menu_choice(choices_dict, prompt_str = "Game 1 or 2?"):
  assert all([isinstance(x, str) for x in choices_dict]), "Keys to choices_dict must be strings"
  
  # Keys of the dict are the possible choices
  valid_choices_list = list(choices_dict.keys())
  
  # Print all choices
  for key, value in choices_dict.items():
    print("{key} : {value}")
    
  # Get a user choice
  user_choice = input(prompt_str)
  
  # Check if it's a valid choice. If it is, loop is skipped.
  while user_choice not in valid_choices_list:
    # User's choice was invalid; loop until it is
    print("{user_choice} is not a valid selection. Enter 1 or 2.")
    user_choice = input(prompt_str)
  return user_choice
 ```
Unfortunately, I am printing: 
Select A Game to Play!
{key} : {value}
{key} : {value}
{key} : {value}
Game 1 or 2? 

SOLUTION: 
```print("{key} : {value}")``` properly formatted to  ```print(num + " : " + game)```
