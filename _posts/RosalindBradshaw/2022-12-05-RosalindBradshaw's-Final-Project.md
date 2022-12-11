---
layout: post
author: RosalindBradshaw
title: Rosalind Bradshaw's Final Project and Final Reflection
---

## Adventure Maze:


<iframe src="https://trinket.io/embed/python/cb199402f6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


## Reflection:

When I first heard that one of the final projects for this class was to code a video game, I knew right away that would be the option I would choose for a 
couple of reasons; I love playing video games, and the graphical turtle exercises were much more engaging for me, so I knew that would be easier for me to 
commit to doing for a larger, more complicated project. I was also inspired by my love of D&D to create an adventure-maze game in which levels of the maze 
were drawn as the player navigated through the maze it self via `click` actions.

To start out, before I even began coding anything, I had to draw out the mazes I wanted to use on graph paper. Each map is drawn as a 26x26 square area, with 
each square corresponding to roughly 15 pixels on the `turtle screen`, and x and y coordinates are charted along the edges of each map. I knew each of these 
steps would be critical to allow me to build such complex structures within the code and have all the sections match up to each other. Each section of the 
maze is built into a smaller `function`, allowing me to call each one only when I need it to be drawn. This allows the illusion that the maze is being 
generated or revealed as the player is reaching that area, and creating a “fog of war” effect on the maze areas that have yet to be drawn.

The first level of the maze is themed as the player making their way through a forest. To help convey the concept of the forest, I imported an image of a 
tree, made that the `turtle shape`, then had the turtle `stamp` the image in the appropriate areas. The forest isn’t as thick as I might have otherwise 
liked, because I didn’t account for the space of the tree image when originally drawing my maze maps. If I was to re-do this project in the future, that 
might be one avenue that I would rework. This was the most challenging map to draw, as it incorporates mostly curved lines throughout. To achieve this, I 
used many definite `for` loops to create each section of curved area:
```
for i in range (20):
    matt.forward(3)
    matt.right(4)
```
Each `for` loop had to be meticulously, and repeatedly, tested to ensure that all of the ends matched up and looked good in the final product. As a byproduct 
of all of the `for` loops, this maze is also the slowest one to generate. I don’t know if there was a way to get around that, but I’m pleased with how it 
turned out. 

Levels two and three of the maze are themed to be inside the theoretical castle. These levels both use exclusively straight lines, which are far easier and 
faster to draw. To convey the idea of the castle, I used two separate background images of cobblestones for the levels. The original images I used presented 
a few different issues. Both were too “busy” and were highly distracting from the basic maze generation I was creating. They were also the wrong size to 
convey the idea I was going for. To address both of these issues, I imported the image files into GIMP, shrank them down, then tiled them across an area to 
create a larger composite image. Then I added a second layer and modified the opacity settings to dull out the overall image. This allows the background 
image to be just that, a background, and not be quite so distracting to the player experience.

To test all of the mazes being drawn by the turtles, I created separate trinkets for each maze. That allowed me to test and modify each one independently, 
before importing them into a larger program.

Level 1 Map: https://trinket.io/python/462f27804c

Level 2 Map: https://trinket.io/python/e38d389f4e

Level 3 Map: https://trinket.io/python/311c68b732


Once all the mazes were good and each section was able to be called independently, I imported them all into a `mazes.py module`.
The next step, after coding the basic maze functions, was to allow the player to navigate the mazes. This ended up being the most challenging part of this 
entire project because of the extremely complicated `flow of control` I had to generate. At first, I made the choice to put all of the navigation codes into 
a separate `module`. I made this choice, initially, because I wanted the code to be well organized, but this ended up creating a huge problem. While I could 
create the navigation `functions` and call them from the `main module` I couldn’t figure out how to pass the `flow of control` back into the `main module` to 
create an iterative process. I experimented with a number of different options to try to fix the issue, but none of them were really successful. Finally, 
after ruminating on that issue for the better part of 3 weeks I realized that the solution was to get rid of the `navigation module` entirely, and just keep 
all of the navigation code within `main.py`. This prevents flow of control traveling outside of `main.py` and allows me to create a truly re-playable game, 
with the ability for the player to exit out of a maze level, or replay at the final screen.

The other big challenge with the movement was how to create boundaries for the player turtle. I did a lot of research early on and found out that `turtles` 
can’t recognize a shift in their background screen. Originally, I’d wanted to create an `if/else` loop such that if the background color were a certain 
color the turtle knew not to go there, but that was impossible with the turtle’s current functionality. Instead, each section of movement happens within 
carefully prescribed `x,y` boundaries. If the player clicks within the allowed area, the turtle moves to that space, a new section of maze is drawn 
(if necessary) and the game progresses. If the player clicks outside of that allowed area, a random error message is pulled from the `error_code dictionary` 
and displayed. Each section of movement works through nested `if/else` loops, allowing the player to move through an area, interact with doorways, and reveal 
new sections of the maze. This is why the `flow of control` was so challenging; the code allows for full backwards movement, meaning that each `function` 
calls to other related `functions` to create a mostly-seamless loop. This is also why having the mazes physically drawn out was critical as well, because 
that way I could keep track of which coordinates were in and out of bounds. It took me a solid 4 or 5 days, with well over 24 combined hours of coding to 
get all of the navigation completely done, but given that that was such a huge component of the maze, I’m not surprised it took most of the time to get 
done. I also made sure to include a few secrets, as any good video game should have. Each level has at least one secret to discover, though some are more 
challenging than others.

After the maze and navigation codes, the next biggest hurdle was the start menu. Originally, I coded the start menu to respond to player `clicks`, but I 
quickly realized that the start menu would continue to exist as a phantom artifact after the code progressed to one of the playable levels. A player could, 
if they knew where to click, still interact with the start menu, even though it wasn’t visible. To get around that, originally, I modified the start menu to 
respond to keyboard `input` commands. That wasn’t as nice of a player experience as I wanted, but it solved the problem. You can see from my various trinket 
iterations, that coding the start menu was actually a very early piece of work. I kept it as a keyboard `input` system right up until the last few days of 
coding when I decided to go back and see if I could make it work through `screen clicks`. This time, the code I’d already created, was robust enough that the 
phantom menu I had been encountering was overridden and the game play progressed as expected. Moving the navigation into `main.py` also allowed me to create 
the functionality to go back to the start menu whenever I wanted to, which creates a more complete player experience.

Adventure Maze Draft 1: https://trinket.io/python/213825b302

Adventure Maze Draft 3: https://trinket.io/python/294b0413fb

Adventure Maze Draft 5: https://trinket.io/python/954170a20a

Adventure Maze Draft 8: https://trinket.io/python/8b54fafe40


Another major piece of code that I wanted to work in was the ability for the code to count the clicks the player made as they moved through the levels and 
display that as a sort of “score”. I was grateful to see that Dr. Hauser had provided a basic `click-counting` code segment in one of the resources for our 
class, and I attempted to incorporate that into my code. The issue I ran into was that I could get the code to either count the clicks, or move the player 
turtle, but not both simultaneously. In the end I gave up on actually incorporating this into my end product. I made this decision because I knew that I was 
already behind where I really wanted to be at that point in working on my final project and I opted to make a more polished finish product that just lacked 
that aspect, than have a code that counted clicks but wasn’t as complete in other aspects. If I had more time I’m positive I could have figured out a way to 
incorporate both click counting and click movement, but it will have to be something I really dedicate more time to later. To display the turtle’s state, I 
opted to have a display on each screen to show which level the player is playing on.

After getting the start menu, mazes, and navigation established, I began working on the extra pieces to really flesh out the code. The first was the 
`error_code dictionary`. For this, I had to do a lot of research and experimentation to actually create my own dictionary. After it was created, I had to 
figure out how to grab a `key`, at random, to display. To achieve this, I turned the `dictionary` into a `list` and used:
```
    error = random.choice(list(error_code.values()))
    print(error)
```
To generate each error message when the `if/else` loops call it. The `dictionary` process ended up creating one of the single most annoying and frustrating 
bugs within my code in the entire project. As I was playtesting, at one point, my code stopped and returned an error message 
“bad token on line 5 in menus.py”. Trinket flagged my `menus.py` module as the source of the error was the line `from navigation import *`. 
Since the line it was having issues with was an entire other module that had over a thousand lines of code, it was definitely the most unhelpful error message 
I’d ever seen. It took me several minutes to figure out what it was trying to tell me. Fortunately, I knew the code had been working prior to building the 
`dictionary`, so I was able to go back to a working form and work forward from there to figure out what had happened. In the end, it turned out that the 
error was coming up because I’d missed a single apostrophe in a new line I’d put in my `dictionary`. While debugging this particular error didn’t really 
take all that long it was definitely the most annoying one I encountered, just because of the vagueness of the error message, and the actual cause of the 
error. It really demonstrated how beneficial it is to run your code frequently as you work, if I’d gone on to work on another section after finishing the 
`dictionary`, I know debugging this error would have been enormously more challenging to figure out.

The final piece of my code was the images I incorporated. Overall, I imported and incorporated 6 different images in my code: the trees in level one, the 
cobblestone backgrounds in levels two and three, the player character image, the final win screen, and the scrolling credits. Incorporating the images ended 
up being a bit more challenging than I originally anticipated because I had to do a lot of modification to get the images to work with my base code. To get 
the player icon, I started out with a generic “adventurer” image, shrank it down, and imported it as the player turtle image. I actually imported two images, 
one facing right and one facing left, so that the player character isn’t moving backwards all the time, though it does still appear to be moving backwards 
occasionally. This could be solved by finding a character image that is facing the “camera” head on, or by implementing more swaps between left/right facing, 
but that would be something I’d leave to a future refactoring of the code. Another idea I had for an eventual refactor of my code was to build in an ability 
to select a player character from a screen of options. For the win screen image, I used the same process as the trees, I incorporated an image, assigned it 
as a `turtle shape` then had the turtle `stamp` it on the screen. I’m actually pretty proud of how I created the final credits image and gave it the 
appearance of scrolling. I started out with creating the image as a google slide, taking a screen shot of it, and importing that as a custom image. Then 
I set it as the `turtle shape` and used a `for` loop to animate it.
```
for i in range (200):
    matt.forward(5)
    matt.delay(30)
```
I chose to use a `for` loop instead of just setting the turtles speed because, even at the slowest speed, the turtle was still moving too quickly for the 
credits to be read. Using the `for` loop allowed me to slow the turtle down enough to have the credits be readable and scroll across the screen from top to 
bottom.

I'd like to credit the following websites for the artwork I used within my game:

Trees: https://www.deviantart.com/phyromatical/art/Tons-of-Tileset-1-10-Light-jungle-trees-485775828

Cobblestone 1: https://www.reddit.com/r/PixelArt/comments/faapnw/my_first_attempt_at_a_decrepit_cobblestone_road/

Cobblestone 2: https://thumbs.dreamstime.com/b/set-seamless-cobblestone-paving-patterns-to-improve-textured-backgrounds-rubble-drawing-173259074.jpg

PC Icon: https://www.nicepng.com/png/detail/785-7857975_generate-sprites-pixel-art-rpg-character.png

Cake: https://png.pngtree.com/png-clipart/20210714/ourmid/pngtree-celebrate-the-cute-pixel-style-of-the-three-tier-cake-tower-png-image_3584824.jpg



Starting out, this was my original, anticipated workflow:

#### Nov 12-16: Base Functionality
- Draw level maps on graph paper
- Code level maps with functions for each section
- Expand Turtle Classes
- Code Start Menu with number entry options
    - Level 1
    - Level 2
    - Level 3
    - Help
    - Exit
- Allow a user to navigate between new screens using the Start Menu
- Code consistently available help menu 
#### Nov 17-23: Interactive Functionality
- Research screen-clear functionality for between-level-transitions
- Research click-counting ability for turtles
- Incorporate click counting into game levels
- Code scoreboard to display moves taken
- Code player-navigation for each maze section
- Boundaries for turtle movements
- Options to proceed to the next area
#### Nov 25-Nov 30: Background Functionality
- Code list or dictionary of error codes
- Incorporate error codes into main code sets
 -Code images into the levels
    - PC icons?
    - Transition images?
- Win animation
#### Dec1-7: Playtesting and Debugging
#### Dec 8: Project Complete and Turned In

Overall, I ended up not keeping to this timeline quite as well as I had anticipated. Partially, that was because I didn’t work in the order I originally 
laid out, not due to any real flaw in my own planning, but simply because I had a lot of real-life stuff come up all at the same time that required a lot of 
flexibility on my part. And partially that was because I didn’t know how to anticipate the amount of time certain sections would take because I’ve never done 
a project like this before.

For my final project, this is the way I completed all the requirements laid out for this assignment:
- At least one external data file. – turtleclass.py, menus.py, drawmazes.py, random
- Dictionaries – error codes
- Custom modules – turtle classes, menus, and maze graphics
- definite (for) loops – level 1 maze graphics, win animation, credits screen
- Custom functions – navigation, maze graphics, win animation, credits screen, start menu, help menu, exit menu
- A Python 3 or Pygame (Python 3 + GUI) Trinket. – #!/bin/python3 shebang enabled
- Have a graphical user interface, responding to key and click events – start menu, level navigation, exit menu
- Have a constantly available help dialog – help option in start menu, and help button in maze levels
- Display information about the program’s state such as score or level – maze level display
- Have at least 3 levels, increasing in difficulty – levels 1-3 of the mazes
- Extend a custom Turtle Class – PlayerTurtle and DMTurtle
- Have a ‘win’ screen – Win animation
- Have an iterative interface – Start menu, Exit buttons in levels, and Exit menu after credits
- Use one or more custom images – Trees, cobblestones, player image, win screen, and credits

In the future, I see many ways I could improve my code, overall. There is the obvious addition of more levels, or a more comprehensive storyline to the 
code. But on the actual coding side, a big part would be to re-work the navigation such that the maze doesn’t draw every section over and over. Right now, 
every time a player navigates to an area, that section gets drawn again. This isn’t normally a big deal, because they player doesn’t see it happening. But 
it does mean that if they player clicks repeatedly in an area, the turtle will scribble all over the screen. The way to fix that would be to code a 
duplicate navigation set for each section so that the maze is only drawn the first time. Another big change would be to introduce a broader selection of 
player icons. Additionally, I would have liked to have the player icon respond so that it always appears to be traveling forwards, which would have required 
having the image change to face the correct direction. I’d also like, at some point, to figure out how to actually get the click counting to work. I’m sure 
it’s possible, it will just take time to figure out exactly how to make it happen, as an addendum to that I’d like to code in a score board so that players 
can see how many moves they take compared to how many other players took on the same level. 





