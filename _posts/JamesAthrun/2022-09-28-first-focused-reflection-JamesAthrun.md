---
layout: post
author: JamesAthrun
title: "JamesAthrun's first post!"
---

I’m looking forward to do a tic tac toe game using python and turtle. I do think turtle is a good drawing tool for me to draw the chessboard of this game. However, I have not came up with the idea of how to draw chess on the board. So for this week, the only thing I have done so far was to draw a automatically generated chessboard on the trinket.
The trinket was able to read the input and take them as the size of the chessboard and also as the color of the chessboard.

A sample code block of drawing the inner line of the chessboard
```
def drawInnerLine(t, startX, startY, size):
  t.penup()
  t.goto(startX, startY)
  t.pendown()
  t.forward(150)

```
During the coding process, I have found that the customization of size is not a good idea currently, which would result in a lot of calculation problems. So I decided to make the size 150.

Here is the whole program:
<iframe src="https://trinket.io/embed/python/67059aa7aa" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
