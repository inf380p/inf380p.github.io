---
layout: post
author: alm7468
title: "April's Completed Final Project"
---
## My Program:
<iframe src="https://trinket.io/embed/python/c337b694fd" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## My program choice and general game concepts:  

I chose to create a game with Python using the Turtle library. After skimming the project instructions once, for some reason, my first instinct was to create a dictionary as a menu of two games. I stuck with this idea and it caused me to do about double the work. I eventually opted to meet all the game requirements throughout the program, but not necessarily for both games. If I could use the same concept (ie. win screen) for both games, then I would implement the same feature in both games. I have included a guide at the bottom of this reflection to point out where all the requirements are met in my program.

For the interface, I imagined a menu prompt for the user to select a game.The menu would be in the form of a dictionary which utilizes keys and values. The user would enter a corresponding key for the game they wanted to play. The menu would navigate to a new screen to begin the chosen game, according to the user feedback.

Game 1, also referred to as the Dot game, would be an extremely simplified version of whack-a-mole. A 3x3 grid of nine possible locations would be identified with black dots (mole holes). One turtle would be the target (mole) and be defined as a red dot that appears and disappears quickly in the nine locations at random. The user must act quickly to click the red dot before it moves to the next location. As the user chases the red dot around the screen, a point is awarded for each successful click on the red dot, a live score would be displayed throughout the game. The user will have a limited amount of time to reach a particular number of successful clicks. The game will become more difficult as the speed of the red dot will increase when the player earns a certain amount of points.

Game 2, also referred to as the Letter game, would essentially be a typing game but instead of words or sentences, I would just use letters. By using letters I could randomize the letter selection. This game went through a few design concepts but ultimately became a typing challenge where the letters appear towards the top of the screen and fall downward, the player must key in the letters before the letter on the screen travels to the bottom of the game screen. The player gets one point for each letter they key in correctly, but for each correct letter, the speed increases which means the game gets difficult very quickly.


## My process, including skills and attitudes: 
I started writing the code with the plan just previously discussed. I had no idea how I would incorporate the other elements like data file, image, turtle class, etc. I started by writing as much as I could in one module. When It was necessary to play with one of the games on its own, I’d copy it into another trinket to avoid any errors caused by the other game or to avoid getting lost in errors on my main trinket. It was actually pretty hard to separate the games into their own modules as an afterthought and so I decided to just put my interface elements, help text, and custom turtles in their own individual modules, but keep the game code in ```main.py```. 

I first wrote my menu dictionary, then screen setup, the user prompt, and I established ```if choice == 1:```, and ```if choice == 2:```. 
I started on the Dot game first. I established how to draw the black holes ```draw_dots()```, who would draw them, and where they would be located by using coordinates ```back_drop()```. Then I established the target turtle and named the turtle “it” as in how the term is used in the game tag since the player is chasing the turtle around. To map his appearances, I plotted the coordinates to make “it” line up with each black hole, to my surprise they were not the same exact coordinates that I used to draw the black holes. Then I made a list of the coordinates and used ```random.choice()``` to select a location. Since the game is in a loop (```while True:```) the location refreshes making the red dot appear and disappear from the locations as I had hoped. I set the win screen to pop up when the score reaches 20 points. The Dot game was very simple and it served as a warm-up before I tried to code the Letter game.

Next, I wrote the Letter game. This took a lot of work, I read our class how-to guides, searched  docs.python.org/3/library/turtle.html, I watched other people build games on youtube, I read forums where other folks were having similar issues that I was having, and I even did some troubleshooting with two non-python coders but that part wasn’t as fruitful as one might hope. I have a hard time knowing when to use continue, pass, return, break, .append(), .update(), or .clear(). I resorted to trial and error every time I needed to reset, stop, or bypass an action. Sometimes I wasn’t sure if I needed to use ```while True:``` or ```screen.update()``` to get something to repeat. The screen timer was a temporary issue for me as well, this one has a VERY simple answer: I was trying to use ```.timer()``` when it needed to be ```.ontimer()```

The Letter game required many functions. The straight forward ones were: drawing the score, the game-over screen, and the winning screen. The difficult ones were when I had to randomly choose letters and draw the letters on the screen, get them to move downward consistently, create a response to user keys, clear and respawn new letters once they’ve been keyed in (AND determine the new speed and location), and increase difficulty as score increases. I think the thing that made this game possible was the use of lists and random(). Instead of assigning three turtles to be the letters, I used a list as a turtle and the selected letter would receive the commands. Ex: 
```python
 for i in range(n): #here n equals the number of letters displayed on the screen simultaneously
    lts[i].speed(0)
    lts[i].hideturtle()
    lts[i].up()
    lts[i].color('green')

```
 I learned about using lambda to create a library of key triggers which allowed me to store the lowercase alphabet values. Another helpful thing I learned online was ```chr(ord('a') + random.randrange(26))```  where ord() returns the integer ordinal/unicode of a one-character string aka a letter. I used range 26 because 1-26 are lowercase English letters. 
It was challenging to use helpful value names, for example, I used “letters”, “lts”, and also “l”. There's also “c” and “chr”, the quantity of representative things became hard to keep track of and distinguish between.

I wrote the score-keeping functions after the primary elements for both games were drafted. Then I was able to create a condition for winning and speed changes to increase difficulty. The turtle class implementation was one of the last requirements that I conquered. It's funny because I feel like the things that seemed daunting were not difficult at all, and the things that I thought would be easy caused me more problems. There were times when the code was correct but I simply needed to move it in front of another bit of code because order matters. My brother-in-law suggested that I use the data file to import help text which killed two birds with one stone. 

Fun fact: I made the silly  intro screen graphic with a digital collage beta tool on a whim while I was writing this reflection.

## Remaining issues:
While there are no bugs in my program, I do wish that I could have figured out solutions to these issues…  
For Game 1:   
The user can still earn a point just after the red dot has disappeared. If the user gets wild and clicks fast, all of those valid clicks count until the target turtle has made it to the new location  
For Game 2:  
The letters respawn on top of each other sometimes  
Can't get the letters to properly clear during win screen  
For Both:  
I don’t know how to turn off the game_over timer once someone has won.  
Cleanly stop the game, but not the program, and Navigate back to main menu

## Here is a list of the requirements and where I included them:
### Data file.
- ```HelpText.txt```

### Dictionaries
- main menu aka ```menu_dict```

### Custom modules
- ```details.py, custom_turtles.py```

### Definite (for) loops
- I used several for loops in the letter game to command changes to each letter on the screen individually
```python
    for i in range(len(letters)): #for each letter on the screen...
      lts[i].clear() #clear the letter so it can move down
      lts[i].goto(pos[i]) #appear in lower, newly determined position from pos[i][1] -= speeds[i]
      lts[i].write(letters[i], None, "center", "20pt normal") #print the selected letter
```
### Custom functions
- Example from Game 2 score keeping method:
```python
def draw_score():
    """write the score number that updates as points are earned"""
    score_turtle.clear()
    score_turtle.goto(-50,170)
    score_turtle.write('{}'.format(score), None, "center", "20pt normal") #insert score in brackets
    screen.update()
```
### Have #!/bin/python3 shebang enabled
- ```main.py```

### Graphical user interface, responding to key and click events
- Example of the interactive code from Game 1:
```python
clicks = 0
  
#CLICKING MEANS...
def clicked(x, y):
  """establishes what happens when user clicks"""
  global clicks
  clicks += 1
  keeper_1.clear()
  keeper_1.write("Score: " + str(clicks), None, "center", "30pt bold")
```
- and it is later called here...
```python
it.onclick(clicked)
```

### Constantly available help dialog. 
``` python
screen = turtle.Screen()
screen.onkey(details.help, '3')
screen.listen()
screen.mainloop()
```
### Display information about the program’s state such as score
- Present in both games

### Have at least 3 levels, increasing in difficulty
- Example from Game 2, when score reaches 5, begin increasing speed range by 1 point for each point earned until 15 points are earned. There aren’t distinct levels but there are many increments of difficulty added as the game progresses:
```python
      #level up
      if score >= 5:
        min_speed += 1
        max_speed += 1
      if score == 15:
        lts[i].clear()
        draw_winner()
        break
```
### Extend a custom Turtle Class
- Example from Game 1:
```python
class ItTurtle(turtle.Turtle):
  def __init__(self):
    turtle.Turtle.__init__(self)
    self.penup()
    self.color("red")
    self.shape("circle")
    self.speed(0)
```
### Have a ‘win’ screen
- Example from Game 1:
```python
    if clicks == 20:
      dotty.clear()
      it.clear()
      screen.bgpic("youwin.png")
      break
```
### Have an iterative interface.
- Example from main.py:
```python
if choice == "3":
  details.help() #print instructions
  choice = details.get_menu_choice(details.menu_dict) #prompt again
```
- Example from Game 1: This part isn't completely hammered out. I spent a while re arranging commands that I thought would clear the screen and allow the next game to begin but it was created issues in my game so I gave up.  If, in the below code, I put ```keeper_1.clear()``` to remove the score as well, the game never ends. It doesn't make sense to me if that request was already inside of the 20 clicks condition. I tried moving ```keeper_1.clear()```after the win screen, or after the reprompt, nothing worked.
```python
    if clicks == 20:
      dotty.clear() # clear black dots
      it.clear() # clear red dot
      screen.bgpic("youwin.png") #display win graphic
      choice = details.get_menu_choice(details.menu_dict) #prompt again
      break
```
### Use one or more custom images
- Intro graphic (built by me), gradient backgrounds in the games, win screen graphic  


## Other points of interest:
### Completion of self assigned intermediate milestones
- yes!

### Code style (guides)
- Proper commenting style used for general comments verses function explanations

### Code correctness (i.e. free of errors & bugs) 
- no red lines!

### Trajectory of improvement over the semester
- I literally knew nothing before, so absolutely.

### Overall ability to make a Python program
- Yes, it seems to have happened.
