---
layout: post
author: inf380pcoder
title: "Inf380pcoder's final project"
---

### Final Project and Reflection 

 

#### My Project Choice
Going into the final project, I felt a good amount of trepidation. I was nervous about being able to complete a large-scale coding project and I worried that I wouldn’t be able to complete such a task. Over the course of the semester, I found that I often understood the broad concepts, but hit a wall when trying to write code myself. I would often get errors, be unable to get the programs to do what I wanted, and I’d get frustrated along the way. I sometimes felt like I was lagging behind others classmates who were grasping the materials more effectively and creatively than I was. However, I tried to approach the final project as a learning experience. As we’ve discussed often in class, there is much to be learned by examining our own learning processes and as much as we put pressure on ourselves to avoid “failure,” it is often through these experiences that we learn the most about ourselves and our abilities. 

With that in mind, I initially tried to brainstorm an idea for myself that I believed would be attainable. While I debated between the two final options, I ultimately chose to complete a turtle project. :turtle:I enjoyed the creative element that the turtle programming offers, and I felt that it would help to keep me motivated and engaged throughout the process. The first things that ran through my head were some of the retro-style games of childhood. I initially thought of a block breaker-type game, but I wasn’t sure that I’d be able to complete some of the elements. I then thought of a :boom:Minesweeper:boom: game. I was confident that I could execute an `onclick` function, which was a major component of the game, and I could challenge myself by building it up and making it more complex. I figured I’d be able to implement multiple levels by creating successive boards with more bombs. Going through the requirements, I figured that I’d be able to work through most of them successfully. I didn’t want to get in over my head and begin something that I wouldn’t be able to finish, so I approached it by starting simple and leaving myself room to add difficulty.


#### My Process for Completion
I began the final project by sketching out the gameboards for the three levels and deciding how I wanted to orient them. I had to plot out where the bombs would be, and then map out the numerical values of the board. For example, if a square touches only one bomb, the value of the square would be one, if it touches two, the square value would be two etc. I repeated this for each level, gradually adding more bombs each time to increase the difficulty. 

The first step of the actual coding process was trying to complete the `draw_game_board` function. For this, I created a function with `for` loops that would draw the board for all the levels. I chose to create a 9x9 board because I figured that multiples of 9 would be easy to deal with (9,18,27,36..) 

```python
def draw_game_board():
      square_color = "black" 
      start_x = -130 
      start_y = -125 
      box_size = 30 
      for i in range(0,9): 
          for j in range(0,9):
              draw_box(sam,start_x+j*box_size,start_y+i*box_size,box_size,square_color)
              box = "white"
              
  draw_game_board()
```

Then, I had to effectively created a board full of `onclick` functions. I had to figure out the coordinates of all of the squares, which took me longer than I initially thought it would. I know now that there were easier ways of finding the coordinates which would have gotten me there faster, as I explained in previous posts, but I eventually figured out the dimensions of all of the squares on the board. This allowed me to set up all of the the `onclick` functions that would allow the turtle to draw a value  (1,2,3, or :bomb:) when each square was clicked. For example:

```python
  #box 1 
  def box1():
    bob.color("light green")
    bob.penup()
    bob.goto(-115,95)
    bob.write("0",None,"center","14pt bold")

 def clicky(x, y):
  #row 1 (squares 1-9)
    if -130 < x < -100 and 85 < y < 115:
      box1()
```

If the user hit a bomb, this triggered a :heavy_exclamation_mark:`Game Over`:heavy_exclamation_mark: screen and a prompt asking them if they wanted to play again. Setting up all of the `onclick` functions was a lengthy process because of all of the coordinates involved, but once I was able to get all of the components set up for the first level, it made creating the other levels much easier.

I initially envisioned the `main` screen as just the first game board in one of my early drafts, but I realized that the game would need a `main` menu upon startup so that the game’s help screen and levels could be displayed. As a result, I made my initial interface screen into game #1. I then created a `main` screen with the user options in `main.py`. The only way I could think to integrate a `dictionary` was to make it the way that the user would choose their level or choose the help option. The `dictionary` would launch the game option based on what number they chose. Pressing `4` at any time brings up the `help` screen.  

One of the next problems that I faced was bringing all of the elements together. I had created the `main` interface,`level one`,`level two`, `level 3` and the `help` screen in separate trinkets. This actually proved helpful as they provided a backup in the event that I accidentally erased code (which I did a few times…:eyes:) or tried things that ended up throwing errors. Integrating the `levels` into the main interface was tricky, because when I first tried to add in levels to the options on the main screen, the gameboards would just draw over each other. Findings solutions for this took a lot of trial and error. I had to try several different things to get the screen to clear and load each `level` independently. Each level is a giant function, which is called with user input on the `main` screen, and which then needed to be reset when another option was chosen. To the user input option,  I added `screen=turtle.Screen()` , `screen.reset()`, then aded the `level` or `help` screen from there.  I then reloaded the `startup` function to the beginning of the `help` screen and `level` functions: 

```python
def setup(screen):
  myscreen=turtle.Screen()
  screen.bgcolor("white")
  window = turtle.Screen()
  window.bgpic('jungle.png') 
  window.update()
```

This seemed to work. It cleared the screen, reloaded the correct background, and then displayed the right game or `help` option, depending on what number the user chose.  


For some reason, the `score` function was the area that gave me the most trouble. I had to test some different options to get the `flow of control` right. Whenever I felt like I had found a workable solution, it either didn’t work correctly or it only partially worked. In that case, there was usually another problem that was introduced.:chart_with_downwards_trend:Finding the right solution felt a little bit like taking two steps forward and one step back. As I mentioned in previous posts, coming up with a way to set up the `score` function within the `game` function was tricky, because it either didn’t recognize the `click` elements or it only worked for the first click but not the others. I finally got it to work by placing the `score = 0` piece outside of the game function and the rest within it. This seemed to work without errors. :chart_with_upwards_trend: I initially put:

```python
def score(x,y):
    global clicks
    if (110 < x < 140 and 55 < y < 85) or (-70 < x < -40 and 25 < y < 55) or (-70 < x < -40 and -35 < y < -5) or (20 < x < 50 and -65 < y < -35) or (50 < x < 80 and -95 < y < -65) or (-100 < x < -70 and -125 < y < -95):
      clicks -= 0
    else:
      clicks += 1
sara.penup()
    sara.goto(-140, 140)
    sara.color("white")
    sara.clear()
    sara.write("SCORE: " + str(clicks), None, "center", "10pt bold")

myscreen.onclick(score, add=True)

```

Setting `clicks -= 0` worked to keep the program from adding a point when a bomb was hit. However, if the user wanted to replay the game, it continued to add points to the score. Instead, I changed it to `clicks = 0` and that seemed to fix the problem, however it also cleared the `score` instead of displaying the user’s final score. This wasn’t a big issue, but it would be nice for the user to be able to see how far they made it without the score clearing so quickly. In the interest of time, I didn’t add in a `top score` function but this would have been one workaround to this. In the future, I would probably try to add that in, so that a `top score` would display as well. 

It was also tricky to figure out how to get two `onclick` functions to work together. Points could either be added to the `score` or the board could be drawn on, but not both.  I tried to approach this through the turtle `Class`, but I had trouble implementing them correctly. I  found that adding `add=True` to the second `onclick` function to be one solution. So, once I (:tada:FINALLY!:tada:) had a workable `score` function I added that in, which allowed both `onclick` functions to work together, adding a point and drawing the values on the board at the same time.  

Having the `score` function work properly was important because that would be the only way to get the `win` screen to really work. When the `score` continued to add points upon replaying, as in my first few attempts, the `win` screen wouldn’t have been effective because it was triggered by a click count. This wouldn’t have been accurate because the count wouldn’t have been true to the number of squares needed to win. So, having a working solution for the scoring then allowed me to add in the `level complete` and `win` screens. I made sure to go through and test out all of the levels, to be sure that these were triggered correctly. This was one of the last major steps that I hoped to complete to get the program to work the way that I wanted. 


The last thing I needed to complete the project requirements was to import an external data file.:page_facing_up: I left this one for last because I wasn’t sure how to incorporate this into the game in the same way that we imported CSV files for the data processing assignment. I decided to try to try to corporate it into my `help` screen. Initially, I just had a turtle `write` the instruction on the screen. But instead I reworked it so that the instructions were imported from a `help.txt` file. I found that this was actually a much simpler way of importing text into the game! I wish I had done that sooner because I had to had to play with coordinates a bit, but it was more efficient than having a turtle write out everything. 

```python
  with open ("help.txt") as file:
    for line in file:
        bob.write(line.strip(), font=FONT)
        bob.goto(-160, bob.ycor() - FONTSIZE)
```
<br>

#### Areas for Improvement
:construction:The program is still a little bit wonky if the user accidentally clicks outside the board because it still counts the click, which is a problem for the scoring. I didn't realize that was a problem until I did that myself. That’s also something I would need to work on a bit more, to create a score boundary. I would also change the scoring to reflect multiple point values, instead of just one. Another thing is that even though I'm sure I set `hideturtle` for all of my game turtles, there is still one that is visable in the game levels. I can't, for the life of me, figure out where it's coming from and it doesn't show up in my individual draft programs. It doesn't affect the functionality, its just annoying. Overall, though, I’m proud of what I was able to accomplish. From doing multiple trial runs, it is error free and generally works as intended. I’m sure there are other things that I could have added or changed. I know there are probably much simpler, less verbose ways of writing some of my code as well. I’m interested in practicing more and building my knowledge in the future. 

#### General Comments
In general, I was able to keep to my intended schedule throughout the process. I tried to break up the process into smaller milestones. I found that working little by little really helped me to make slow and steady progress without burning myself out. Having the weekly check-ins was helpful for keeping myself accountable and making progress on the things that I wanted to accomplish. I told myself that I would do a reflection for the week of Thanksgiving, just so that I would keep progressing and reflecting on the things that were working and the areas that I needed to continue to work on. This was a really useful exercise in mapping out a trajectory for completion.  All in all, this assignment and the class in general really helped me to build a foundation in programming. Starting this class as a total novice, I think I was able to really grow in my abilities. I truly learned a lot about both the material and my own ability to face new challenges.:raised_hands:

#### Final Requirements

- [X]  **At least one external data file** - external .txt file
- [X]  **Dictionaries** - on main.py for level/help option
- [X]  **Custom modules** - main.py, setup.py, help.py, one.py, two.py, and three.py
- [X]  **Definite `(for)` loops** - gameboard drawing functions
- [X]  **Custom functions** - misc. functions throughout including `score` function
- [X]  **Have a graphical interface, responding to click events** - gameboard is made up of `onclick` functions 
- [X]  **Consistently available help dialog** - user can press `4` anytime for help
- [X]  **Display information about programs state** - program shows `level` and `score`
- [X]  **Have at least 3 levels** - three levels with increasing # of bombs
- [X]  **Extend a custom turtle class** - has `Title` and `Rules` classes
- [X]  **Have a ‘win’ screen** - with a certain score, it triggers a `win` level or `win` game screen
- [X]  **Have an iterative interface** - user can play multiple times by pressing 1,2,3 etc. again
- [X]  **Use one or more custom images** - background image 

#### My Final Game

:video_game:<iframe src="https://trinket.io/embed/python/523654d891" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

#### Game Cheat Code
**Level 1** Bomb locations: squares 18, 21, 39, 51, 61, 65<br>
**Level 2** Bomb locations: squares 6, 21, 25, 29, 40, 46, 53, 61, 66, 78<br>
**Level 3** Bomb locations: squares 2, 6, 16, 20, 24, 28, 30, 36, 50, 53, 56, 71, 73, 77, 81
