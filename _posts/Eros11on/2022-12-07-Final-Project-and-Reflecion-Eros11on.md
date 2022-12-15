---
layout: post
author: Eros11on
title: "Zheng Zhong's Final Project and Reflection"

---

# Tetris

<iframe src="https://trinket.io/embed/pygame/75f8b69ce2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


# Reflection

## Why I choose Turtle project as my final project?

* As a future software engineer, I focus on users' experiences. Also, I always show a strong ownership on my program and want to make my program perfect. With this spirit, I would like to write a program that allows the user to have a good interaction process and feel relaxed and happy when using it. 
* Reviewing my past learning modules about Turtle, I have completed a lot of fantasic programs. I even wrote a little game of snake eating in turtle. Although it was only a half-finished product, through the progress, I felt how exciting it is to write a program that gives the user a great experience. So, I choose Turtle project as my final project. 

## Project Plan

#### Nov. 11th - Nov.16th: Review

- Review previous Turtle modules and read more materials about Turtle.
- Break down each feature of this game.

#### Nov.17th - Nov.22th: Basic Functionality

- Draw background of the game on the graph paper
- Draw block
- Set up the turtle window
- Design scoring features

#### Nov.23th - Nov.28: Interactive Functionality

- Design the function of controlling, moving and changing directions of block
- Design the function of eliminating a row and getting the score
- Design the function of increasing the score and difficulty when a row is completed

#### Nov.29th - Dec.4th: Advanced Functionality

- Design the advanced function of changing directions of block, pausing block and changing shapes of block
- Design the function of restarting the game
- Custom modules and reorganize codes

#### Dec.5th - Dec.8th: Debug, Project Complete and Turned In

Overall, I basically completed the whole project according to the initial plan, although some parts didn't go exactly as planned because when I actually got started, I found that some features had to be implemented with previously completed features.
Below I will highlight my thinking and the skills I used to complete the entire project.

## Project Realization Process

### Milestones achieved

-  [x] **At least one external data file** - block.py, draw.py, random<br />
 -  [x] **Dictionaries** - mainy used in drawing map and block<br />
 -  [x] **Custom modules** - block.py, score.py, draw.py<br />
 -  [x] **Definite `(for)` loops** - functions of blocks and map setting up<br />
 -  [x] **Custom functions** - functions of moving, changing shapes, pausing blocks, function of restarting game, function of score...<br />
 -  [x] **Have a graphical interface, responding to click events** - function of restarting game<br />
 -  [x] **Consistently available help dialog** - displaying score<br />
 -  [x] **Display information about programs state** - displaying game over state, displaying score, displaying how to restart game<br />
 -  [x] **Have at least 3 levels** - level 1 - normal speed, higher level: with the increasement of socre and when a row is completed, the speed of game increases： block falls faster<br />
 -  [x] **Extend a custom turtle class** - block class<br />
 -  [x] **Have a ‘win’ screen** - displaying 'game over'<br />
 -  [x] **Have an iterative interface** - restart game<br />
 -  [x] **Use on or more custom images** - bg image<br />

### Difficulties and Solutions

#### Set up block

Before I designed the blocks, I firstly listed the types of blocks I needed, which were 7 in total, and specified their sizes. Then I drew all the shapes they would change on paper. Finally I chose to use an extension class to cover all the blocks. Depending on the number of small squares they are composed of, it is determined how big a matrix to use to represent them. For example, the long bar is represented by the following code.

```
I = Block("cyan", [ [ [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ],
                [ 1, 0, 0, 0 ] ]
              
              [ [ 0, 0, 0, 0 ],
                [ 0, 0, 0, 0 ],
                [ 0, 0, 0, 0 ],
                [ 1, 1, 1, 1 ] ] ])
#This block is made of 4*4 matrix, every '1' reprensents a small quare and four '1' compents to one block, '0' represents Null.
#This block has two shapes. One is vertical and one is horizontal.
```

```
def set_block_on_map():
    block_tiles = active_block.tiles[active_block_index]
    for row in range(len(block_tiles)):
        for col in range(len(block_tiles[row])):
            if block_tiles[row][col] == 1:
                game_map[active_block_row + row][active_block_col + col] = active_block
    draw_map()
    
#This code sets a block on the game map. The active_block and active_block_index variables represent the current block and the current orientation of the block, respectively. The active_block_row and active_block_col variables represent the row and column of the upper left corner of the block on the map.

The block_tiles variable is initialized to the tiles of the active_block in the current orientation. The code then loops over the rows and columns of the block_tiles and sets the corresponding tiles in the game_map to the active_block object if the tile is not empty (i.e., if its value is 1).
```

#### Set up background

At first, I wanted to simply draw the whole game interface with turtle, but when I was ready to design the block after the simple drawing, I found that the interface I drew before didn't match the block settings and other functions at all. I needed an interface that could cover all the blocks. After reading a lot of materials, I found that Tinkter is a very suitable library for drawing GUIs, and it can easily draw a large 10*20 matrix.

```
game_map = [["" for _ in range(map_cols)] for _ in range(map_rows)]
def draw_map():
    map_turtle.clear()
    for row in range(map_rows):
        for col in range(map_cols):
            map_turtle.goto(map_x + tile_size * col, map_y - tile_size * row)
            draw_box(map_turtle, tile_size, tile_size, "black", game_map[row][col].color if game_map[row][col] else "mintcream")


#This code uses a turtle to draw a map on a screen. The map is represented as a two-dimensional array, game_map, with map_rows and map_cols representing the number of rows and columns in the map, respectively. The map_x and map_y variables represent the x and y coordinates of the upper left corner of the map.

The map_turtle variable is an instance of the turtle, which is used to draw the map. The tile_size variable determines the size of each tile on the map. The draw_box function is called for each tile on the map, with the coordinates, size, and color of the tile passed as arguments. The color of the tile is determined by the color attribute of the game_map object at the corresponding row and column, or "mintcream" if the object is empty.
```

#### Design functions of blocks

I think The moving function of blocks is one of the difficult points in the whole project.Following is the code I designed and the explanation.

```
def moveTheBlock(move):
    #define a function named moveTheBlock() that takes in a single parameter, move. The function uses several global variables: active_block, active_block_row, active_block_col, and active_block_index.
    global active_block,active_block_row,active_block_col,active_block_index

    #The function first checks if active_block is None, and if so, returns immediately.
    if active_block is None:
        return
    
    #If move is "right", the function checks if it's valid to move the block one column to the right, and if so, it updates active_block_col and calls the draw_block() function. 
    if move == "right":
        if is_valid_block(active_block, active_block_row, active_block_col + 1, active_block_index):
            active_block_col += 1
            draw_block()
            
    #If move is "left", the function checks if it's valid to move the block one column to the left, and if so, it updates active_block_col and calls draw_block().
    elif move == "left":
        if is_valid_block(active_block, active_block_row, active_block_col - 1, active_block_index):
            active_block_col -= 1
            draw_block()
    
    #If move is "rotate", the function updates active_block_index to the next index in the list of tiles in active_block, but only if the new index is valid. It then calls draw_block().
    elif move == "rotate":       
        new_block_index = (active_block_index + 1) % len(active_block.tiles)
        if is_valid_block(active_block, active_block_row, active_block_col, new_block_index):
            active_block_index = new_block_index
            draw_block()
            
    #If move is "drop", the function repeatedly moves the block down one row at a time until it's no longer valid to do so, and then calls draw_block().
    elif move == "drop":
        while is_valid_block(active_block, active_block_row + 1, active_block_col, active_block_index):
            active_block_row += 1
        draw_block()
    elif move == "pause":
        pause = not pause
```

The hardest part of this is the **rotate** design. I was initially limited by the previous idea of moving left to right functionality. I wanted to start with the index of the block, but I found it very complicated because there are so many shapes of blocks, and each index is different, which makes it very troublesome to manipulate.Then I discovered that I could do this directly by drawing new shapes of block, rather than transforming on the original shapes.This is a good inspiration for me. Sometimes, if I consider a problem from a different perspective, it is more easy to solve the problem.

#### Design advanced functions

When designing the function of eliminating rows to get points and increase the difficulty of the game level, I initially intended to split the implementation into two functions. But I found that playing separate levels with different difficulty levels could not help but make the player feel a bit bored. It would be more interesting to increase the difficulty of the game as the number of rows eliminated increases. Designing the function to increase the score by eliminating rows was relatively simple, but how to increase the difficulty as the score increases was another problem I encountered.

#### Design function of restarting game

When designing the function of restarting game, I  firstly considered clearing the entire screen and then redrawing the screen, which was the simplest and most convenient method I could think of. It was relatively easy to implement.

```
def realTimeRun():
    global active_block,active_block_row,active_block_col,active_block_index
    
    newdata = 0
    if active_block is None:
        make_new_block()
        if not is_valid_block(active_block, active_block_row, active_block_col, active_block_index):
            active_block = None
            newdata = -1
            #showGameOver()
            #return
        draw_block()
    else:
        if is_valid_block(active_block, active_block_row + 1, active_block_col, active_block_index):
            if not pause:
                active_block_row += 1
                draw_block()
        else:
            set_block_on_map()
            active_block = None
            newdata += remove_completed_rows()

    return newdata
def drawnewgame():
    global map_turtle,block_turtle,game_map,active_block
    map_turtle.clear()
    block_turtle.clear()
    game_map = [["" for _ in range(map_cols)] for _ in range(map_rows)]
    active_block = None
    
#realTimeRun() is the main game loop, and drawnewgame() is a function that resets the game state and clears the screen.

#realTimeRun() starts by checking if the active_block variable is None or not.  
  If it is None, a new block is created using the make_new_block() function. The new block is then checked to see if it is a valid block using the is_valid_block() function. If the block is not valid, the active_block variable is set to None and the function ends. Otherwise, the block is drawn on the screen using the draw_block() function.
  If active_block is not None, the function checks to see if the block can be moved down one row. If it can, the block is moved down and redrawn on the screen. If it cannot be moved, the block is set on the game map using the set_block_on_map() function, and active_block is set to None. The function then checks for completed rows and removes them using the remove_completed_rows() function.

#drawnewgame() is a simpler function that clears the screen, resets the game map, and sets the active_block variable to None. This function is used to reset the game state and start a new game.
```

#### Custom modules

At first I put all my code in one ```main.py```, which seemed very redundant. Then I started assigning different files to the code based on their different functions.

Previous code:

<iframe src="https://trinket.io/embed/pygame/bbba5b20ea" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>  


Of course some parts of the code could be more optimized. For example, in the function ```remove_completed_rows()``` One potential improvement for this function would be to return the updated score and game update interval values instead of modifying them as global variables. This would make the function more modular and easier to test.



# Conclusion

Looking back on the whole project, there were various difficulties, but they were successfully solved with the help of related materials and classmates. This project helped me understand that designing a Python program or a small game requires a lot of time to design the interface and various functions in the early stage, so that some unnecessary troubles can be avoided when writing the code formally. In addition, during this project and this semester's course, I also learned more about the features of Python, such as its simple code writing style and many mature libraries to call and implement very easily. I have also learned Java before, and there is a big difference between python and it. In the future, I would like to learn more about the application of Python in the field of machine learning, and of course I hope I can use Python more in the back-end field.








<div align=center><img width=200 hight=200 src="https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg"/></div>
