---
layout: post
author: Eros11on
title: "Zheng Zhong's Project Update"
---

**This week, I have completed the initial game interface with the following code.**

**Its overall background is orange, and there is a large matrix of 10*20 small rectangles spelled out in the middle, which gives a good reference for the shape of each block afterwards.**
```
class Block:
    def __init__(self, color, tiles):
        self.color = color
        self.tiles = tiles
        
I = Block("cyan", [ [ [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ] ],
              
              [ [ 0, 0, 0, 0 ],
                [ 0, 0, 0, 0 ],
                [ 0, 0, 0, 0 ],
                [ 1, 1, 1, 1 ] ] ])
                
J = Block("blue", [ [ [ 0, 1, 0 ],
                [ 0, 1, 0 ],
                [ 1, 1, 0 ] ],
              
              [ [ 0, 0, 0 ],
                [ 1, 1, 1 ],
                [ 0, 0, 1 ] ],
              
              [ [ 1, 1, 0 ],
                [ 1, 0, 0 ],
                [ 1, 0, 0 ] ],
              
              [ [ 0, 0, 0 ],
                [ 1, 0, 0 ],
                [ 1, 1, 1 ] ] ])
                
L = Block("orange", [ [ [ 1, 0, 0 ],
                [ 1, 0, 0 ],
                [ 1, 1, 0 ] ],
              
              [ [ 0, 0, 0 ],
                [ 0, 0, 1 ],
                [ 1, 1, 1 ] ],
              
              [ [ 0, 1, 1 ],
                [ 0, 0, 1 ],
                [ 0, 0, 1 ] ],
              
              [ [ 0, 0, 0 ],
                [ 1, 1, 1 ],
                [ 1, 0, 0 ] ] ])
                
S = Block("lime", [ [ [ 0, 0, 0 ],
                [ 0, 1, 1 ],
                [ 1, 1, 0 ] ],
              
              [ [ 1, 0, 0 ],
                [ 1, 1, 0 ],
                [ 0, 1, 0 ] ] ])
                
Z = Block("red", [ [ [ 0, 0, 0 ],
                [ 1, 1, 0 ],
                [ 0, 1, 1 ] ],
              
              [ [ 0, 1, 0 ],
                [ 1, 1, 0 ],
                [ 1, 0, 0 ] ] ])
                
O = Block("yellow", [ [ [ 1, 1 ],
                     [ 1, 1 ] ] ])
                     
T = Block("magenta", [ [ [ 0, 0, 0 ],
                [ 0, 1, 0 ],
                [ 1, 1, 1 ] ],
              
              [ [ 0, 1, 0 ],
                [ 1, 1, 0 ],
                [ 0, 1, 0 ] ],
              
              [ [ 0, 0, 0 ],
                [ 1, 1, 1 ],
                [ 0, 1, 0 ] ],
              
              [ [ 1, 0, 0 ],
                [ 1, 1, 0 ],
                [ 1, 0, 0 ] ] ])
                



tile_size = 25
map_rows = 20
map_cols = 10
map_x = -125
map_y = 250


map_turtle = turtle.Turtle()
map_turtle.hideturtle()
map_turtle.up()

game_map = [["" for _ in range(map_cols)] for _ in range(map_rows)]


active_block = None
active_block_row = 0
active_block_col = 0
active_block_index = 0

block_turtle = turtle.Turtle()
block_turtle.hideturtle()
block_turtle.up()

game_update_interval = 250


def draw_box(t, width, height, pencolor, fillcolor):
    t.color(pencolor, fillcolor)
    t.down()
    t.begin_fill()
    for _ in range(2):
        t.forward(width)
        t.right(90)
        t.forward(height)
        t.right(90)
    t.end_fill()
    t.up()



def draw_map():
    map_turtle.clear()
    for row in range(map_rows):
        for col in range(map_cols):
            map_turtle.goto(map_x + tile_size * col, map_y - tile_size * row)
            draw_box(map_turtle, tile_size, tile_size, "black", game_map[row][col].color if game_map[row][col] else "mintcream")

```

**This weekend and next week, I plan to design each block so that they can have different shapes. Also I plan to design the function to make the block move and change its direction.**



<div align=center><img width=300 hight=300 src="https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg"/></div>
