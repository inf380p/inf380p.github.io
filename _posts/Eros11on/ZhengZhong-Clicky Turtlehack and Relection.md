---
layout: post
author: Eros11on
title: "Zheng Zhong's Clicky Turtlehack and Reflection"
---

## Reflection
So far I've  known the basic syntax of Python, and in particular, I've gained a lot of new insights into the Turtle library. It can create infinite possibilities. Of course, I know that Python is a very malleable programming language. I'm looking forward to learning more about Python's powerful libraries and their applications. 

## Clicky Turtlehack
- _**Now I would like to share a small game used Clicky that I created.**_ 🤩🤩🤩

- _**Gluttony Snake🐍**_

  - Game Rules
    1. The game begins, use keyboard up and down, left and right to control gluttonous snake movement direction, to find food, gluttonous snake to eat food will increase a section.
    2. The snake will die if it touches itself.
    3. The Snake will die after touching the wall.
  
  - Set up the game interface
    1. Draw game contents such as game window, snake head and food, and also need to show game score at the top
    
    
     ```wn = turtle.Screen()
        wn.bgcolor("blue")
        wn.setup(width=600, height=600)
        wn.tracer(0)
        
        head = turtle.Turtle()
        head.shape("square")
        head.color("blue")
        head.penup()
        head.goto(0, 0)
        head.direction = "Stop"
        
        food = turtle.Turtle()
        colors = random.choice(['red', 'green', 'black'])
        shapes = random.choice(['square', 'triangle', 'circle'])
        food.speed(0)
        food.shape(shapes)
        food.color(colors)
        food.penup()
        food.goto(0, 100)
        
        pen = turtle.Turtle()
        pen.speed(0)
        pen.shape("square")
        pen.color("black")
        pen.penup()
        pen.hideturtle()
        pen.goto(0, 250)
        pen.write("Score : 0 Best Score : 0", align="center",
                  font=("candara", 24, "bold"))
     ```
   - Add listening to keys
     1. After adding the objects, we need to listen to the keys in order to control the snake's movement through the keys. In this game, we use the four WASD keys to control the up, down, left, right and center movements respectively

     ```# set button direction

          def group():
            if head.direction != "down":
          head.direction = "up"


          def godown():
             if head.direction != "up":
          head.direction = "down"

          
          def goleft():
              if head.direction != "right":
                  head.direction = "left"
          
          
          def goright():
              if head.direction != "left":
                  head.direction = "right"
          
          
          def move():
              if head.direction == "up":
                  y = head.ycor()
                  head.sety(y+20)
              if head.direction == "down":
                  y = head.ycor()
                  head.sety(y-20)
              if head.direction == "left":
                  x = head.xcor()
                  head.setx(x-20)
              if head.direction == "right":
                  x = head.xcor()
                  head.setx(x+20)
          
          wn.listen()
          wn.onkey(group, "w")
          wn.onkey(godown, "s")
          wn.onkey(goleft, "a")
          wn.onkey(goright, "d")
          ```
   - Change the length and color of the snake's body, score points after the snake eats food, check the snake's head collision, score and save the highest score

   _**Now Enjoy the game and good luck !🤘🤘🤘**_
   
   <iframe src="https://trinket.io/embed/python/6579639c30" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
        
<div align=center><img width=300 hight=300 src="https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg"/></div>
