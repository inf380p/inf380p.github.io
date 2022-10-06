---
layout: post
author: shashwatj14
title: "Shashwat's Clicky Turtlehack"
---

For this assignment, I used every piece of information I've learned so far in this course. I have created a snake-based game where you have to control the movement of the snake within the screen and you'll lose the game if the snake moves outside of the screen. The number of points you earn is determined by the number of seconds you stay in the game after beginning the snake movement.

I used keyboard bindings for the snake movement, using four keys - a,s,w,d - to move the snake in four different directions. Here's my code for the game:

```
# import required modules
import turtle
import time
import random

delay_value = 0.1
score = 0
high_score = 0

# Creating a window screen
screen = turtle.Screen()
#screen.title("Snake Movement Game")
screen.bgcolor("black")
# the width and height can be put as user's choice
#screen.setup(width=600, height=600)
screen.tracer(0)
game_start = False

# head of the snake
snake_head = turtle.Turtle()
snake_head.shape("square")
snake_head.color("white")
snake_head.penup()
snake_head.goto(0, 0)
snake_head.direction = "Stop"

score_pen = turtle.Turtle()

# assigning key directions
def goup():
  global game_start
  game_start = True
  if snake_head.direction != "down":
    snake_head.direction = "up"


def godown():
  global game_start
  game_start = True
  if snake_head.direction != "up":
    snake_head.direction = "down"


def goleft():
  global game_start
  game_start = True
  if snake_head.direction != "right":
    snake_head.direction = "left"

def goright():
  global game_start
  game_start = True
  if snake_head.direction != "left":
    snake_head.direction = "right"

def update_score(pen, score, game_over):
  screen_width, screen_height = screen.window_width(), screen.window_height()
  pen.clear()
  pen.speed(0)
  pen.shape("square")
  pen.color("white")
  pen.penup()
  pen.hideturtle()
  pen.goto(0, screen_height / 2 - 50)
  sc_string = "" if not game_over else "GAME OVER!!!"
  sc_string += "Score : " + str(score) 
  pen.write(sc_string, align="center", font=("candara", 24, "bold"))


def move():
  screen_width, screen_height = screen.window_width(), screen.window_height()
  x = snake_head.xcor()
  y = snake_head.ycor()
  
  if snake_head.direction == "up":
    snake_head.sety(y+20)
  if snake_head.direction == "down":
    snake_head.sety(y-20)
  if snake_head.direction == "left":
    snake_head.setx(x-20)
  if snake_head.direction == "right":
    snake_head.setx(x+20)

  if(x < -screen_width / 2 or x > screen_width / 2):
    return True
  if(y < -screen_height / 2 or y > screen_height / 2):
    return True
  return False

screen.listen()
screen.onkey(goup, "w")
screen.onkey(godown, "s")
screen.onkey(goleft, "a")
screen.onkey(goright, "d")

segments = []


# Main Gameplay
while True:
  screen.update()
  game_over = move()
  update_score(score_pen,score, game_over)
  if(game_start):
    score += 1
  time.sleep(delay_value)
  if(game_over):
    break

update_score(score_pen, score, game_over)

```
  
There were a few things that bothered me as I worked through this code. And there was one new concept that I learned that I had never heard of before: Global Varibales. When you create a variable inside a function, it is normally local and can only be used within that function. The global keyword can be used to declare a global variable within a function. In my case, I also had to use the global keyword because I needed to change a global variable within a function. Without this, I wouldn't have been able to set my game_start variable to True when I encountered any user movement for the game's start.

Initially, I wanted the game screen to be titled 'Snake Movement Game,' and I wanted the user to be able to select the screen size dimensions, but I couldn't do either. This was strange to me because I was calling the correct methods. When I attempted to use the title method, I received an error about an unknown attribute. And, for some reason, when I tried to change the screen size, my background color was reset to white. As a result, I had to comment this line out.

Overall, developing this game was a fantastic learning experience, and it was also my first-ever python game, so I'm looking forward to more innovative and meaningful programming projects in the future.

Here's the link to my trinket:
<iframe src="https://trinket.io/embed/python/66aed09093" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
