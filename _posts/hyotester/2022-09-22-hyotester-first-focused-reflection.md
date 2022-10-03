---
layout: post
author: hyotester
title: "Hyo's First Focused Reflection"
---

# Introduction
Hi, I'm hyojeong! This posting is my first focused reflection, where I am exploring and focusing on code and how that specific code has helped me learn throughout the class. 

## Let's get started to understand Functional Turtles

September is my birthday!! So I tried to learn how to write the Happy Birthday Python Program during Turtle. Also, I use input function to know that How many friends will come to my birthday party?. 

You may be wondering that who invited to my birthday party. So, I used function to iterate variable name inside loop. This function let you know the people  invited to my birthday party.

<iframe src="https://trinket.io/embed/python/4103681aad" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# User Input to Calculate Birth Year and Number of Friends

```python
for name in ["Joe", "Amy", "Brad", "Angelina", "Zuki", "Thandi", "Paris"]:
    print("Hi", name, "Please come to my party on Saturday!")
        
```

# Input 
```python
import turtle

window = turtle.Screen()
window.bgcolor("lightgreen")

shape = turtle.Turtle()
shape.color("blue")
shape.pensize(3)

sides = int(input("How many friends will come to my birthday party? "))

def polygon(sides,length):

    for x in range(sides):
        shape.forward(length)
        shape.left(360/sides)
        
        
from datetime import datetime
today = datetime.today()
age_str = input('What is your age?\n')
age = int(age_str)
birth_year = today.year - age
print("You were born in " + str(birth_year) + " or " + str(birth_year - 1))

```

# Creating a Cake with Topping and a Plate

```python
# initializing a variable for co-ordinating
y_coordinate = -125

def draw_candle_for_cake(fill_color, border_color, x, y):
    my_turtle_cursor.penup()

    # Changing color of our cursor
    my_turtle_cursor.color(border_color)
    # Changing fill color of the cursor
    my_turtle_cursor.fillcolor(fill_color)

    my_turtle_cursor.goto(x, y)
    my_turtle_cursor.pendown()
    my_turtle_cursor.begin_fill()

    # Drawing the first side of our Candle
    my_turtle_cursor.forward(25)
    my_turtle_cursor.left(90)

    # Drawing the second side of our Candle
    my_turtle_cursor.forward(60)
    my_turtle_cursor.left(90)

    # Drawing the third side of our Candle
    my_turtle_cursor.forward(25)
    my_turtle_cursor.left(90)

    # Drawing the fourth side of our Candle
    my_turtle_cursor.forward(60)
    my_turtle_cursor.left(90)

    my_turtle_cursor.end_fill()

    my_turtle_cursor.getscreen().update()

# Creating a Function to draw stick on the candle
def draw_stick_on_candle(fill_color, x, y, cursor_size):
    my_turtle_cursor.penup()

    # Changing color of our cursor
    my_turtle_cursor.color(fill_color)

    # Changing fill color of the cursor
    my_turtle_cursor.fillcolor(fill_color)
    my_turtle_cursor.goto(x, y)
    my_turtle_cursor.pensize(cursor_size)
    my_turtle_cursor.begin_fill()
    my_turtle_cursor.pendown()
    my_turtle_cursor.right(90)
    my_turtle_cursor.forward(12)
    my_turtle_cursor.end_fill()
    my_turtle_cursor.getscreen().update()

# Function to draw topping of our cake
def draw_toppings_on_cake(fill_color, border_color, x, y, radius):
    my_turtle_cursor.penup()

    # Changing color of our cursor
    my_turtle_cursor.color(border_color)

    # Changing fill color of the cursor
    my_turtle_cursor.fillcolor(fill_color)
    my_turtle_cursor.goto(x, y)
    my_turtle_cursor.pendown()
    my_turtle_cursor.begin_fill()

    # Drawing a circle using circle function
    my_turtle_cursor.forward(10)
    my_turtle_cursor.left(90)
    my_turtle_cursor.circle(radius, extent = 180)
    my_turtle_cursor.left(90)
    my_turtle_cursor.forward(10)
    my_turtle_cursor.end_fill()
    my_turtle_cursor.getscreen().update()

# Creating a Function to draw different layers of a cake
def draw_layer_of_the_cake(fill_color, border_color, cursor_size, x, y, width, height):
    my_turtle_cursor.hideturtle()
    my_turtle_cursor.penup()

    my_turtle_cursor.pensize(cursor_size)
    # Changing color of our cursor
    my_turtle_cursor.color(border_color)
    # Changing fill color of the cursor
    my_turtle_cursor.fillcolor(fill_color)
    my_turtle_cursor.goto(x, y)
    my_turtle_cursor.pendown()

    # Starting the cursor to fill color
    my_turtle_cursor.begin_fill()

    for i in range(2):
        my_turtle_cursor.forward(width)
        my_turtle_cursor.left(90)
        my_turtle_cursor.forward(height)
        my_turtle_cursor.left(90)

    my_turtle_cursor.end_fill()
    my_turtle_cursor.setheading(0)
    my_turtle_cursor.getscreen().update()



# # Creating an empty list of different parts of our cake
parts_of_cake = []
parts_of_cake.append(["#A020F0", "#000000", 3, 30])
parts_of_cake.append(["#55FF55", "#000000", 3, 20])
parts_of_cake.append(["#B87333", "#000000", 3, 60])

# drawing an plate for our cake using draw_layer_of_the_cake() function
draw_layer_of_the_cake("#FFC0CB", "#000000", 3, -220, y_coordinate - 70, 400, 10)

# Drawing different parts of our cake
for parts in parts_of_cake:
    draw_layer_of_the_cake(parts[0], parts[1], parts[2], -135, y_coordinate - 60, 240, parts[3])
    y_coordinate += parts[3]


# drawing top topping of our cake
draw_toppings_on_cake("#C20067", "#000000", -120, y_coordinate - 60, 10)
draw_toppings_on_cake("#FFFF00", "#000000", -80, y_coordinate - 60, 10)
draw_toppings_on_cake("#FF0000", "#000000", 25, y_coordinate - 60, 10)
draw_toppings_on_cake("#0000FF", "#000000", 59, y_coordinate - 60, 10)

# drawing middle topping of our cakes
draw_toppings_on_cake("#FFA500", "#000000", -135, y_coordinate - 80, 10)
draw_toppings_on_cake("#E4E6EB", "#000000", -135, y_coordinate - 100, 10)
draw_toppings_on_cake("#FFA500", "#000000", -135, y_coordinate - 120, 10)
draw_toppings_on_cake("#181A18", "#000000", -80, y_coordinate - 80, 10)
draw_toppings_on_cake("#0000FF", "#000000", -65, y_coordinate - 110, 10)
draw_toppings_on_cake("#FFD700", "#000000", -95, y_coordinate - 140, 10)
draw_toppings_on_cake("#181A18", "#000000", 10, y_coordinate - 80, 10)
draw_toppings_on_cake("#E4E6EB", "#000000", -20, y_coordinate - 110, 10)
draw_toppings_on_cake("#181418", "#000000", 35, y_coordinate - 140, 10)
draw_toppings_on_cake("#FFA500", "#000000", 75, y_coordinate - 80, 10)
draw_toppings_on_cake("#E4E6EB", "#000000", 75, y_coordinate - 110, 10)
draw_toppings_on_cake("#FFD700", "#000000", 75, y_coordinate - 140, 10)

# Drawing candle on of our cake using draw_candle_for_cake() function
draw_candle_for_cake("#FFF44F", "#000000", -40, y_coordinate - 60)

# Drawing stick on top of our candle
draw_stick_on_candle("#000000", -26, y_coordinate + 15, 7)
```

