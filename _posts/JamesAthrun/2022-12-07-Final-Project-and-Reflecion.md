---
layout: post
author: JamesAthrun
title: "JamesAthrun's Final Project and Reflection"
---

#### Tic-Tac-Toe Game


## Rules:
The game is played on a grid that's 3 squares by 3 squares.
You are X, your friend (or the computer in this case) is O. Players take turns putting their marks in empty squares.
The first player to get 3 of her marks in a row (up, down, across, or diagonally) is the winner.
When all 9 squares are full, the game is over.
 
Custom Functions:
Two modes can be chosen: player versus player and player versus computer
In the player versus computer mode, two levels can be chosen: easy and difficult.
 
## Milestones:
Create a base chessboard and a normal player versus player mode game
Create a easy computer mode to compete with player
Create a difficult computer mode to compete with player
Finish the other functions of the game to make it satisfied with user experience requirements and the requirements of the final project
 
## Reflections:
In the first milestone, I have a better understanding of how to use turtle.py to make a chess board and the whole background from scratch. 
In my first approach, I use the exact position of the screen to draw the chessboard. It takes me to calculate all the dots of the chessboard to draw the whole background. 
When I search on the Internet, I have found a new way to deal with the problem. The turtle package provides a function called screen.setworldcoordinates to create a coordinate axis on the background. In this case, I created the background like this:
screen = turtle.Screen()
screen.setworldcoordinates(-5, -5, 5, 5)
Then I no longer need to use the accurate position to draw the chessboard. What I need to do is just to let the turtle go to the corresponding position on the coordinate axis I have created to start drawing the chessboard.
I have added a csv file for users to choose what background they would like to use for the tic tac toe game. Instead of using a hard-coded dictionary, the reason why I choose to use csv file to finish my goal is that I hope the users can add whichever background they would like to in the game. It is very easy for users to add new background pictures. All they need to do is to upload a gif file to the library and then add a line with index and the picture name in the csv file. 

'''
filename = "backgroundImg.csv"
dict_from_csv = {}
with open(filename, mode='r') as inp:
    reader = csv.reader(inp)
    dict_from_csv = {rows[0]:rows[1] for rows in reader}

mode = get_menu_choice(dict_from_csv)
pic = dict_from_csv.get(mode)

screen.bgpic(pic)
screen.update()
'''
For the menu part, I have used the template from the class. I have really learnt a lot from that part and as a result, I use that as a template and implement it into my code. I have created three menus corresponding to three different stages.
The first menu is used to create the choice of background.
The second menu is used to choose the game mode.
The third menu is used to choose the level of the game if the user decides to play against the computer.
'''
	def get_menu_choice(choices_dict, prompt_str="Make a selection"):
    assert all([isinstance(x, str) for x in choices_dict]), "Keys to choices_dict must be strings"

    valid_choices_list = list(choices_dict.keys())

    print("Main Menu")
    for label, description in choices_dict.items():
        print(f"{label}: {description}")

    user_choice = input(prompt_str)

    # Check if it's a valid choice. If it is, loop is skipped.
    while user_choice not in valid_choices_list:
        # User's choice was invalid; loop until it is
        print(f"{user_choice} is not a valid selection.")
        user_choice = input(prompt_str)

    return user_choice
'''

Then it comes to the most difficult part of the game: let the players play on the chess board. 

For the object of the chess board, I use a 2D list to record it. If the position is 0, that means there is no chess in that position. 1 means the first player and 2 means the second player/computer. 

For me, I think the mode of player versus player is comparably easy. The computer does not take part in the game itself. What a computer needs to do is just to judge whether one player has won the game or not. 

The way to judge the winner of the game is rather simple. First, the computer needs to decide whether one has three chess pieces in a row.
'''
	def evaluate(b):
    for row in range(3):
        if (b[row][0] == b[row][1] and b[row][1] == b[row][2]):
            return b[row][0]

    for col in range(3):
        if (b[0][col] == b[1][col] and b[1][col] == b[2][col]):
            return b[0][col]

    if (b[0][0] == b[1][1] and b[1][1] == b[2][2]):
        return b[0][0]
    if (b[0][2] == b[1][1] and b[1][1] == b[2][0]):
        return b[0][2]

    return 0
'''
Another function is to judge whether there are still empty positions on the chess board.
'''
def isMovesLeft(b):
    for i in range(3):
        for j in range(3):
            if (b[i][j] == 0):
                return True
    return False
'''
With these two functions computers can decide whether the game has ended.
'''
def gameover(b):
    if (evaluate(b) != 0):
        return evaluate(b)
    if (isMovesLeft(b)):
        return 0
    else:
        return 3
'''
The output has four options.
If the output is 0, it means that the game can continue.
If the output is 1 or 2, it means that some player has won the game.
If the output is 3, it means that the game ends with a tie.


Then I am able to construct the prototype of the game.
'''
def play_pvp(x, y):
    global turn
    i = 3 - int(y + 5) // 2
    j = int(x + 5) // 2 - 1
    if i > 2 or j > 2 or i < 0 or j < 0 or b[i][j] != 0:
        return
    if turn == 'x':
        b[i][j], turn = 1, 'o'
    else:
        b[i][j], turn = 2, 'x'
    draw(b)
    r = gameover(b)
    if r == 1:
        print("Game over!", "X won!")
        turtle.clear()
        turtle.bgpic("win.png")
        return
    elif r == 2:
        print("Game over!", "O won!")
        turtle.clear()
        turtle.bgpic("win.png")
        return
    elif r == 3:
        print("Game over!", "Tie!")
        return
'''
To construct the AI logic of the computer is the most important part in the project. I find this very challenging, but also very interesting. 
I decided to divide my game level into two stages, easy and difficult, just like most of the other games.
For the easy mode, I use the random module to let the computer automatically get the empty position and randomly place the chess.

For the hard mode, I search on the Internet and find there are two strategies. 
One strategy is to follow the player’s intuition. The computer will first look into the place where they can win the game. If there is no such position, the computer will then look into the place to avoid the players winning the game. If neither of these positions exist, the computer will first look into the center of the board, then to the corner of the board, and eventually to other places. 
The second strategy is called the minmax strategy. The computer will evaluate which move will benefit the most. This is a rather difficult task so I choose the first strategy.

I set up a module called the best choice for the computer to get the position.
'''
def getWinPoint(b, cur_player):
    position = [-1,-1]
    for row in range(3):
        if (b[row][0] == b[row][1] and b[row][2] == 0 and b[row][0] == cur_player):
            position = [row, 2]
        if (b[row][0] == b[row][2] and b[row][1] == 0 and b[row][0] == cur_player):
            position = [row, 1]
        if (b[row][1] == b[row][2] and b[row][0] == 0 and b[row][1] == cur_player):
            position = [row, 0]
 
    for col in range(3):
        if (b[0][col] == b[1][col] and b[2][col] == 0 and b[0][col] == cur_player):
            position = [2, col]
        if (b[0][col] == b[2][col] and b[1][col] == 0 and b[0][col] == cur_player):
            position = [1, col]
        if (b[1][col] == b[2][col] and b[0][col] == 0 and b[1][col] == cur_player):
            position = [0, col]
 
    if (b[0][0] == b[1][1] and b[2][2] == 0 and b[0][0] == cur_player):
        position = [2, 2]
    if (b[0][0] == b[2][2] and b[1][1] == 0 and b[0][0] == cur_player):
        position = [1, 1]
    if (b[2][2] == b[1][1] and b[0][0] == 0 and b[2][2] == cur_player):
        position = [0, 0]
 
    if (b[0][2] == b[1][1] and b[2][0] == 0 and b[0][2] == cur_player):
        position = [2, 0]
    if (b[0][2] == b[2][0] and b[1][1] == 0 and b[0][2] == cur_player):
        position = [1, 1]
    if (b[2][0] == b[1][1] and b[0][2] == 0 and b[2][0] == cur_player):
        position = [0, 2]
 
    return position
 
def getEmptyCorner(board):
    corner_list = [[0,0], [0,2], [2,0], [2,2]]
    available = []
    for i in range(4):
        cur_pos = corner_list[i]
        if (board[cur_pos[0]][cur_pos[1]] == 0):
            available.append(i)
    if (len(available) == 0):
        return -1, -1
    res = choice(available)
    return corner_list[res]
 
def computer_round_random(b):
    # randomly choose a position
    pos = 0
    vacant = []
    for i in range(3):
        for j in range(3):
            if b[i][j] == 0:
                vacant.append(pos)
            pos += 1
    if (len(vacant) == 0):
        return -1,-1
    target = choice(vacant)
    i = target // 3
    j = target % 3
    return i, j
 
 
 
def findBestMove(board):
    # find win point
    bestMove = getWinPoint(board, computer)
    if (bestMove[0] != -1):
        return bestMove[0], bestMove[1]
 
    # find player's win point
    bestMove = getWinPoint(board, player)
    if (bestMove[0] != -1):
        return bestMove[0], bestMove[1]
 
    # find center
    if(board[1][1] == 0):
        return 1, 1
 
    #find available corner
    bestMove = getEmptyCorner(board)
    if (bestMove[0] != -1):
        return bestMove[0], bestMove[1]
 
    bestMove = computer_round_random(board)
    return bestMove[0], bestMove[1]
'''

I also extend a turtle class to let the turtle write a 'happy game' in the centre of the chessboard. 

'''
class WordTurtle(turtle.Turtle):
    def welcome(self):
        self.color('cyan')
        self.write("Happy Game!", move=True,align='center',font=('Arial',55,'bold'))
'''
 
## Future Improvements:
The background picture is not fit for the whole size of the background. In my original design, I think the picture should fit the size of the background and give the users a feeling of putting the chessboard in the background for them to play. However, it turns out that the size of the picture differs from each other, and I’m not able to set the background size of the turtle screen.
I’m using the turtle.mainloop() function to ensure that the game will go in a loop until someone wins the game or the game reaches to the end. However, I do not know how to add the whole game into a loop to let the player play again after one game ends. I try to put the whole code into a big while loop but that does not work. 
 
<iframe src="https://trinket.io/embed/pygame/9bf065053b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
