---
layout: post
author: hyotester
title: "Hyo's Final Project & Reflections"
---


# Reflection for turtle project

## Old plan
My initial idea for the final project to build a game to find a route in the hospital. I spent time exploring pathfinding code and practicing code through the existing frame: How to Make a Turtle Maze Game. Based on this experience, I’ve learned codes to achieve my initial milestones:
- [x] Drawing or import hospital map (images) at the right scale 
- [x] Calculate the speed and direction to search for current place / follow right direction / arrive final destination
- [x] Clicks or keypresses(Listen for at least the 4 arrow keys and one more key to control the red ball’s position and one other aspect of its state)

<iframe src="https://trinket.io/embed/python/3779b6ba4f" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
<iframe src="https://trinket.io/embed/pygame/67bcbed925" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

However, I spent a week completing milestones, but I couldn’t add three milestones into the maze game. So, I decided to postpone completing the maze game and changed direction to build ping pong game. 

## What I intended to accomplish for my final project:
- [ ] Add instruction to let user know how to use keyboard shortcuts to start/pause/quit and restart
- [ ] Count time to arrive final destination
- [ ] Provide view solution (create a pathfinding solution)
- [ ] During the break, I will plan to continue and build maze pathfinding as a GPS.

Reference: https://devpost.com/software/mizzou-path-finding.
# New Direction

## Final Project objective
In fact, I wanted to build a pathfinding game similar to a GPS function, but for a limited time I decided to build a Ping Pong game to achieve all the requirements of the final project. I recreated a Ping Pong uisng Python and Pygame library in Trinket. The Pygame library provides additional features such as adding sound and adding animation to make interactive games that I want to use in the final Ping Pong game. Also, the library helps me to develop my Object -Oriented Programming skills. 

<iframe src="https://trinket.io/embed/pygame/7b7b4c7777" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Process1 | Getting started 
To start a project, I thought the game flows focusing on clear goals, control, interface and challenge parts. For the clear goal, the game objective needs to be clear, but also convey information (instruction) at the right time. Before playing a game, players should know how to start, what they should be doing, and what is different levels to master in the game. First of all, I installed turtle and used screen methods (code1) to set up and run in its own window including game title, color, width and height. 

#### Code1: Screen setting 
```
screen = turtle.Screen()
screen.title('Ping Pong Game')
screen.setup(800, 400)
screen.bgcolor('#007500')
screen.tracer(0)
```

The rules of the game and clear instructions are the most important part for players.
First of all, I created an external data file called guide.py explaining the rules (code2), how to start, pause, exit and keep restarting the game from the beginning, over and over again. 

#### Code2: Call function from another file 
I Created a guide.py file containing conditional statements and time.sleep() functions. 
```
import time
import random

def main():
    
    print("Welcome to the Pin Pong Word")
    print("The Tutorial....\n")
    print("For 1 player mode :")
    print('use arrow keys or w,s for movement of ur bat (left screen)')
    print('the velocity with which you strike the ball affects its angle too\n')
    print('For 2 player mode : ')
    print('for left player : w,s / (arrows)')
    print('for right player : i,k for movement\n')
    time.sleep(1)
    start = input ("Do you want to read instruction step by step click 'y' or click 'n' to start the Ping Pong now? (y/n)")
    if start == "y":
        print ("Welcome to the Ping Pong Word.")
        print("Starting Poing Poing game ...")
        print
        print("Press space bar to pause the game anytime")
        time.sleep(2)
        
        print("Press escape to exit the game anytime")
        print
        time.sleep(2)
        
        print("The player who reaches 10 scores first wins the game!")
        print("When this game is over, you will return to the main home page where you can start again!")
        print("Select For 1 player mode of For 2 player mode to start the Ping Pong")
        
          
            
    elif start == "n":
        print("Press space bar to pause the game anytime")
        print ("Follow the instruction and enjoy! ")
        print('Press escape to exit the game anytime')
        print('Thank you for choosing to play Pong game :)))')
        print('The player who reaches 10 scores first wins the game!')
main () 
```
I also created another Main.py and imported the previous  guide.py file into it. I used syntax below to call the functions defined in the  guide.py file.

```
from guide import main 
```
#### The main game for loop
I used a python function which is a definite iteration for loop that repeats the game over and over until a specific conduction is over. Also, the range () function allows the user to loop through  a specified number of starting and end. These functions are an iterative interface and able to perform playing the game over and over. 

```
def rect(t, l, b):
    t.pendown()
    for i in range(2):
        t.forward(l)
        t.right(90)
        t.forward(b)
        t.right(90)
```

#### Display information about the game’s state such as score or level: 4 levels(Easy, Medium, Hard and Unlimited) in order to increase in difficulty. 

A game’s levels are important since it allows players to create a challenge and be professional. Controlling the level of difficulty can be easy to learn, but difficult to master. From learning experience, I will be able to learn a new module, function (code3) in Python to control how much information is given to the player.

#### Code3: Creating 4 levels of difficulty

```
def level_screen():
    pen.clear()
    pen.penup()
    pen.goto(-205, 120)
    pen.write('Select the Levels', font=('ravie', 22, 'normal'))
    pen.goto(-150, 80)
    pen.pendown()
    rect(pen, 300, 40)
    pen.penup()
    pen.goto(-150, 20)
    pen.pendown()
    rect(pen, 300, 40)
    pen.penup()
    pen.goto(-150, -40)
    pen.pendown()
    rect(pen, 300, 40)
    pen.penup()
    pen.goto(-150, -100)
    pen.pendown()
    rect(pen, 300, 40)
    pen.penup()
    pen.goto(-35, 45)
    pen.write('Easy', font=('comic sans ms', 20, 'normal'))
    pen.goto(-55, -17)
    pen.write('Medium', font=('comic sans ms', 20, 'normal'))
    pen.goto(-35, -77)
    pen.write('Hard', font=('comic sans ms', 20, 'normal'))
    pen.goto(-65, -137)
    pen.write('Unlimited', font=('comic sans ms', 20, 'normal'))
    screen.update()
    screen.onclick(level_select)
    screen.mainloop()
```
I used three main functions to create different levels of difficulty. 
- global min_pos
Function to find minimum and maximum position in list
- delay_time
Function to adjust the speed of the game
- win_score
Function to define the Score above which the 10 score means a win. Define a Python function named win_scores which has two parameters. The first parameter will be a dictionary mapping strs to ints. The second parameter will be a list of str. The function must return a list of values associated with the strings in the second parameter. 

```
def level_select(x, y):
    global min_pos, delay_time, win_score, mode
    if x >= -150 and x <= 150:
        if y <= 80 and y >= 40:
            min_pos = length / 2 - 100
            delay_time = 0.006
            win_score = 10
            pen.clear()
            main_game()
        elif y <= 20 and y >= -20:
            min_pos = length / 2 - 200
            delay_time = 0.005
            win_score = 10
            pen.clear()
            main_game()
        elif y <= -40 and y >= -80:
            min_pos = length / 2 - 300
            delay_time = 0.002
            win_score = 10
            pen.clear()
            main_game()
        elif y <= -100 and y >= -140:
            min_pos = length / 2 - 200
            mode = 3  # special unlimited mode
            delay_time = 0.005
            win_score = 999
            pen.clear()
            main_game()

```




## Process2 | Playing Ping Pong: Adding and controlling the paddles
I draw components to start and create the game. First of all, the game has two players: a human and a machine. Two players have control over the paddles of their side so I needed to create two paddles to move the paddles on vertical sides from up to down or down to up (code4). Also, the user needed to control the ball that I needed to create the ball as well. 

The turtle is a built-in module in Python which is used for graphical illustrations. So, I used the turtle module to illustrate the graphics such as paddles and ball. 

#### Code4: Adding and controlling the paddles
```
bat1 = turtle.Turtle()
bat1.color('#964B00')
bat1.shape('square')
bat1.shapesize(7, 1, 2)
bat1.penup()
bat1.setpos(-length / 2 + 15, -width / 2 + 80)
bat2 = turtle.Turtle()
bat2.color('#964B00')
bat2.shape('square')
bat2.shapesize(7, 1, 2)
bat2.penup()
bat2.setpos(length / 2 - 22, width / 2 - 75)

ball = turtle.Turtle()
ball.penup()
ball.color('#FFFFFF')
ball.shape('circle')
ball.shapesize(1.7, 1.7, 1)
ball.seth(45)

ball.hideturtle()   
bat2.hideturtle()
bat1.hideturtle()
```
I have a graphical user interface, responding to key and click events. You can use arrows on the keyboard to "Up key" for "Up" and "Down key" for "Down". Also, the shortcut on keypress  "w" for "Up" and "s" for "Down" for the left player and  "i" for "Up" and "k" for "Down" for the right player (code5).
As you know about the tennis game, we will initiate how the ball and striking of the paddle will work, as if the ball hits the paddle, it will go for the opposite player, but if the paddle misses the ball, then the ball will hit the border, and the opposite player will get the score!!

#### Code5: Responding to key and click events 
```
screen.onkeypress(up_p1, 'Up')
screen.onkeypress(down_p1, 'Down')
screen.onkeyrelease(up_p1, 'Up')
screen.onkeyrelease(down_p1, 'Down')
screen.onkeypress(up_p1, 'w')
screen.onkeypress(down_p1, 's')
screen.onkeyrelease(up_p1, 'w')
screen.onkeyrelease(down_p1, 's')
screen.onkeypress(up_p2, 'i')
screen.onkeypress(down_p2, 'k')
screen.onkeyrelease(up_p2, 'i')
screen.onkeyrelease(down_p2, 'k')
screen.onkey(waiting, 'space')
screen.onkey(finish, 'Escape')
screen.listen()
```

## Process3 | Playing Ping Pong: Adding bouncing balls and Adding a score system
To understand how to implement a bouncing algorithm, I learend about random.randint () method and velocity vector. I’ve really struggled with understadning methods to calculate velocity, position and time.

#### Basic Example : Final velocity (v) is calculated.

```
time = 1
finalVelocity = initialVelocity + acceleration * time
print("Final velocity = ", finalVelocity)
```


```     
if mode == 1 or mode == 3:
            if ball.xcor() >= min_pos:
                    if ball.heading() <= 90 or ball.heading() >= 270:
                        pos = ball_calculate_trajectory()
                        if bat2.ycor() > pos + 10:
                            if not bat2.ycor() - 70 < -width / 2:
                                bat2.sety(bat2.ycor() - speed / 3)
                        elif bat2.ycor() < pos - 10:
                            if not bat2.ycor() + 70 > width / 2:
                                bat2.sety(bat2.ycor() + speed / 3)
            if time.time() - prev_time1 >= 0.2:
                velocity1 = int(
                    (((bat1.ycor() - prev_pos1)) / (time.time() - prev_time1)) / 5)
                prev_time1 = time.time()
                prev_pos1 = bat1.ycor()
            if time.time() - prev_time2 >= 0.2:
                velocity2 = int(
                    (((bat2.ycor() - prev_pos2)) / (time.time() - prev_time2)) / 5)
                prev_time2 = time.time()
                prev_pos2 = bat2.ycor()
 ```
#### Collision Detection 1

The next step to make a bouncing ball is to detect when the ball hits/collides with one the two paddles. I added a new method called bounce() to make it bounce using a random new direction.

```	
# wall collisions
            if ball.ycor() >= width / 2 - 20:
                ball.sety(width / 2 - 20)
                ball.seth(360 - ball.heading() % 360)
            if ball.ycor() <= -width / 2 + 20:
                ball.sety(-width / 2 + 20)
                ball.seth(360 - ball.heading() % 360)
            # wall collisions end
            # bat collisions
            if ball.xcor() >= length / 2 - 40 and ball.xcor() <= length / 2 - 20:
                if ball.ycor() > bat2.ycor() - 80 and ball.ycor() < bat2.ycor() + 80:
                    if ball.heading() <= 90:
                        ball.seth(180 - ball.heading() % 360 + velocity2 / 6)
                        if (ball.heading() >= 80 and ball.heading() <= 110):
                            ball.seth(ball.heading() - velocity2 / 6)
                        ball.forward(ball_speed * 5)
                    else:
                        ball.seth(180 + 360 - ball.heading() % 360 + velocity2 / 6)
                        if (ball.heading() >= 250 and ball.heading() <= 300):
                            ball.seth(ball.heading() - velocity2 / 6)
                        ball.forward(ball_speed * 5)
            if ball.xcor() <= -length / 2 + 40 and ball.xcor() >= -length / 2 + 20:
                if ball.ycor() > bat1.ycor() - 80 and ball.ycor() < bat1.ycor() + 80:
                    if ball.heading() <= 180:
                        ball.seth(180 - ball.heading() % 360 + velocity1 / 6)
                        if (ball.heading() >= 80 and ball.heading() <= 110):
                            ball.seth(ball.heading() - velocity1 / 6)
                        ball.forward(ball_speed * 5)
                    else:
                        ball.seth(180 + 360 - ball.heading() % 360 + velocity1 / 6)
                        if (ball.heading() >= 250 and ball.heading() <= 300):
                            ball.seth(ball.heading() - velocity1 / 6)
                        ball.forward(ball_speed * 5)
```
#### Collision Detection 2
```	
            if bat2_score % win_score == 0 and bat2_score > 0:
                bat1_score = 0
                bat2_score = 0
                if mode == 1:
                    print('Machine Wins!')
                    end_screen('Machine has won!!!')
                elif mode == 2:
                    print('Player 2 Wins')
                    end_screen('Player 2 has won!!!')
            elif bat1_score % win_score == 0 and bat1_score > 0:
                bat1_score = 0
                bat2_score = 0
                if mode == 1:
                    print('Player Wins!')
                    end_screen('You have won!!!')
                elif mode == 2:
                    print('Player 1 Wins')
                    end_screen('Player 1 has Won!!!')
                wn.update()
        screen.update()
        time.sleep(delay_time)
```
## Process4 | Having a Win screen

```
            if bat2_score % win_score == 0 and bat2_score > 0:
                bat1_score = 0
                bat2_score = 0
                if mode == 1:
                    print('Machine Wins!')
                    end_screen('Machine has won!!!')
                elif mode == 2:
                    print('Player 2 Wins')
                    end_screen('Player 2 has won!!!')
            elif bat1_score % win_score == 0 and bat1_score > 0:
                bat1_score = 0
                bat2_score = 0
                if mode == 1:
                    print('Player Wins!')
                    end_screen('You have won!!!')
                elif mode == 2:
                    print('Player 1 Wins')
                    end_screen('Player 1 has Won!!!')
                wn.update()
        screen.update()
        time.sleep(delay_time)
```

## The most challenging part and further direction
I’ve struggled with adding gif(custom image) into turtle, I used all methods in order to add gif but I couldn't. I will continue and find solution.
Also, I've tried to add having a constantly available help dialog during play Ping Pong. I wroted many forms to allow the user to learn 
what they can do in the program at any time. However, when I add external file into main.py, it has error and couldn't play game. 


## Video
<iframe width="560" height="315" src="https://www.youtube.com/embed/aDV6QPtHT_Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


