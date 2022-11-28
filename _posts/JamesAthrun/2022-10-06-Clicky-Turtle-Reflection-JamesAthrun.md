---
layout: post
author: JamesAthrun
title: "JamesAthrun's Clicky Turtlehack"
---

## Introduction
For this week, I have created a game called Find the Treasure. The treasure will be hidden in any place of the chessboard. Players can click on the board to see whether they can find out where the treasure is. There will also be hints if players approach the treasure.

## Coding process
I have used python before, so writing the logic behind the game is not very difficult for me. 
First, I created the chessboard in the turtle and let turtle write some titles on the graph.
```
#Draw Chessboard
def drawInnerLine(t, startX, startY, size):
  t.penup()
  t.goto(startX, startY)
  t.pendown()
  t.forward(size)

#Background setup
def screen_setup():
  t.hideturtle()
  t.speed(0)
  t.penup()
  t.goto(base, base)
  t.pendown()
  for i in range(4):
    t.forward(300)
    t.left(90)
  
  add = 50
  for i in range(6):
    drawInnerLine(t, base, base + i * add, 300)
  
  t.left(90)
  for i in range(6):
    drawInnerLine(t, base + i * add, base, 300)
  
  t.penup()
  t.goto(-130, 190)
  t.write("Try to find the treasure in the chessboard!", font=("Arial", 10, "normal"))
  t.goto(-130, 170)
  t.write("Click it!", font=("Arial", 10, "normal"))
  t.update()
  ```
  Placing the title of the game makes me a little bit confused. Since there is a restriction of the drawing zone. I find it difficult to place my titles. So I have to make the title size much more smaller than I expected.

  Then I try to use the onclick() function to get the position clicked by the players, and then to give response accordingly.
  ```
  #HighLight Target
def highlight():
  t.penup()
  t.goto(base + (targetX + 1) * 50, base + (targetY + 0.5) * 50)
  t.pendown()
  t.color("red")
  t.begin_fill()
  t.circle(25)
  t.end_fill()

    
#Click Function
def clicky(x, y):
  if (x < base or y < base or x > 0 - base or y > 0 - base):
    print("out of boundary")
  else:
    curX = (x - base) / 50
    curY = (y - base) / 50
    if (int(curX) == targetX and int(curY) == targetY):
      print("you win!")
      highlight();
      return step;
    elif ((int(curX) == targetX - 1 or int(curX) == targetX+1 or int(curX) == targetX) and (int(curY) == targetY - 1 or int(curY) == targetY+1 or int(curY) == targetY)):
      print("almost")
    else:
      print("nothing is there")

  return step;
  ```


   <iframe src="https://trinket.io/embed/python/9042aa9412" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Reflection and Problems
The Gaming Logic is not very difficult to complete. However, I have spent much more time in adjusting the title size and position. And something is not as perfect as I have expected because of some problems I have met when using turtle and unable to solve.
1. I am trying to set the instructions (you win, almost, nothing is there) beside the chessboard instead of in the console. But when I try to clear the previous instruction using t.clear(), everything has been cleared. 
2. I am also trying to record how many steps one player have taken to find the hidden treasure. But I did not find a good way to do so. 
3. It seems that the first click of the game will not have any effect on the chessboard. Currently I have no idea why that happens.

Hopefully these problems can be solved in the following course of this class! I would like to make this game a perfect one.

