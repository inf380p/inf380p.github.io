---
layout: post
author: RosalindBradshaw
title: "Rosalind Bradshaw's Interface Draft"
---

### Final Project Workplan:

#### Nov 12-16: Base Functionality
  - Draw level maps on graph paper
  - Code level maps with `functions` for each section (Custom Modules, Functions, 3 levels)
  - Expand `Turtle Classes` (extended turtle class)
  - Code Start Menu with number entry options (iterative interface)
    - Level 1
    - Level 2
    - Level 3
    - Help
    - Exit
  - Allow a user to navigate between new screens using the Start Menu
  - Code consistently available help menu (help dialogue)

#### Nov 17-23: Interactive Functionality
  - Research `screen-clear` functionality for between-level-transitions (program state)
  - Research click-counting ability for turtles
  - Incorporate click counting into game levels
  - Code scoreboard to display moves taken (program state)
  - Code player-navigation for each maze section (graphical user interface)
  - Boundaries for turtle movements
  - Options to proceed to the next area

#### Nov 25-Nov 30: Background Functionality
  - Code `list` or `dictionary` of error codes
  - Incorporate error codes into main code sets
  - Code images into the levels (custom images)
  - PC icons?
  - Transition images?
  - Win animation (definite `for` loops, win screen)

#### Dec1-7: Playtesting and Debugging

#### Dec 8: Project Complete and Turned In


As of writing this post, I've managed to cross of several items from this list of things to do. I've drawn-up the hardcopies of all of my level maps,
expanded some `turtle classe`s, including adding a custom `turtle function`, coded a start menu, figured out some of how to get between screens with the 
start menu, and researched some screen `clear` functionality.

Coding the start menu was the first big task of today, originally I thought about making it a `dictionary` system the way we saw the CSV coding's main menu, but
I realized that that was going to take a lot more work to figure out than I wanted to put into the project at this moment. Instead, I shifted tactics to a 
click based system and ended up with this:

<iframe src="https://trinket.io/embed/python/b6dd9c7cbd" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

This version actually did almost everything I wanted it to do: it allowed a user to click on each button and get a defined response without having to use a
keyboard entry format. To map the locations of the buttons, I built a smaller, secondary function that let me click on a spot and get the turtle coordinates
returned as a `print` statement. This helped me make sure the boundaries of each button were within the squares drawn on the screen.

```
def screen_map(x,y):
  matt.goto(x,y)
  print(x,y)
```

Unfortunatly, while I was trying to move on to the next step: getting the code to move onto a playable level I ran into some big issues. Notably, if I got 
the screen to clear and go to an actual game level, the program would still remember where the original buttons had been mapped and they would still be 
accessible through the game screen, even though they weren't visible. After taking a break from the coding for a while, I came back to it with a different plan.
To get around the issues created by encoding the start menu navigation within a `function` I, instead, went for a less elegant, but more straight forward
plan to build the whole start menu as just a sequence of nested `if/else` conditionals within a `while` loop. Now the player has to use a keyboard entry to 
navigate the Start Menu, but it still does everything I wanted it to at the outset.

I also took the opportunity to code a quick help menu option that I will be able to re-use later in my code as a persistent help-button.
```
def help_menu_start():
  print("Pick a number from the start menu to start playing.")
```
My plan is to, later, expand my DMTurtle class a little more and give it a help button `function` that it will automatically generate on game-levels.

By the end of the day, I managed to pull together all the various bits and pieces I'd been working on to create this:

<iframe src="https://trinket.io/embed/python/294b0413fb" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

As you can see, the user can navigate through the start menu to various options, and move past the start menu into the early forms of one of the playable
levels. For each playable level, the user will be able to navigate the maze via click inputs. Each section has carefully prescribed boundaries to prevent the
turtle from going through the "walls". So this is what my workplan looks like right now:

### Final Project Workplan:

#### Nov 12-16: Base Functionality
  - ~~-Draw level maps on graph paper~~
  - Code level maps with functions for each section (Custom Modules, Functions, 3 levels)
  - ~~Expand Turtle Classes (extended turtle class)~~
  - ~~Code Start Menu with number entry options (iterative interface)~~
    - ~~Level 1~~
    - ~~Level 2~~
    - ~~Level 3~~
    - ~~Help~~
    - ~~Exit~~
  - ~~Allow a user to navigate between new screens using the Start Menu~~
  - Code consistently available help menu (help dialogue)

#### Nov 17-23: Interactive Functionality
  - ~~Research screen-clear functionality for between-level-transitions (program state)~~
  - Research click-counting ability for turtles


I still have a lot of work to do for this program, but I'm pleased with how its coming along so far. I think the goals I've set for myself are reasonable,
and I have some more ideas in the back of my head to expand the game out even more if I run out of things to do before the end of the semester.

Before the next class period, the biggest thing to be done is to have all of my mazes coded, with each section broken down into callable 
`functions` to enable each section of the maze to be drawn as the player gets to it. There will be some roadblocks with that, with a notable one being how to
accurately and consistenly draw curved lines between two given grid points. I'm sure it can be done, it will just be a matter of figuring out the exact
math to make it happen. After that, the next goal will be to code the help button within the expanded `turtle class`.
