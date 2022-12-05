---
layout: post
author: JULIIRA
title: "Turtle Final"
---

Embedded trinket for turtle final:

<iframe src="https://trinket.io/embed/pygame/076d59cf51" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# What program did I choose for this final and why?

For my final, I decided to make a turtle game because I am more familiar with using turtle. In addition, I am a visual and creative person
so creating games sounds more ideal than doing data analysis. I’m bad with numbers and I was struggling with the CSV files 1 exercise so I 
realized that I should probably not do a final on something I am not good at.  Even though I had some difficulty with creating turtle games too,
I feel more confident executing my codes using turtle. Also, most of the semester we were working with turtle and when we started doing data analysis 
coding, nothing clicked for me despite hours of trying to understand and incorporate the code. 

#  What was the process like? Skills and Attitude during the process?

The overall attitude during this final was defeat and acceptance. There were a lot of codes I had hope to incorporate in my game but was unable to do so
due to my lack of experience and skills. I have accepted this fact that I couldn’t do everything I wanted in my code, but I did not let that fact discourage me.
I tried to use whatever skills I had to still do what was needed for the final, but at the same time gave myself creative freedom. 

For this final, I decided to use pygame since I am creating a turtle game. It was a bit difficult at first because I have never used pygame for prior codes. 
In addition, I couldn’t get my codes to show up on the screen at first so I did my code on python3 for my interface draft. After talking with Professor Hauser
after class, I realized that python3 is for more text-based coding and that the reason why my code wouldn’t show up on the interface was that I forgot one important 
code at the end: 

```
turtle.done()
```
Once I realized my error and after receiving assistance, I moved my code from python3 to the pygame. Prior to moving my code, I had made some codes to create
my turtle avatars:

```
class car(turtle.Turtle):
  def __init__(self):
    car = turtle.Turtle()
    car.shape("square")
    car.color("blue")
    car.penup()
    car.goto(-200, 0)
    car.speed(1)
    car.forward(400)
    car.backward(400)
  
while True:
   car()
```
In my car code, I learned how to set the car into a loop so that it would continue to go back and forward on the screen to make it look like it was moving. 
I am still struggling with making loops but now I am slightly more experienced in making loops. 
I learned how to code a custom turtle class and somewhat incorporate them into my code. I had successfully made a custom turtle class for my apple avatar, 
but I deleted the code because I couldn’t do what I wanted if it were in a class, same with my snappy turtle avatar. 
This was my code for the apple avatar before I deleted it in the final code:

```
class apple(turtle.Turtle):
   def __init__(self):
      apple = turtle.Turtle()
      apple.shape("circle")
      apple.color("red")
      apple.penup()
      apple.speed(7)
      apple.goto(-150,0)

apple = apple()
```
My snappy turtle code was similar to the apple code, but whenever I put snappy into a class, it wouldn’t allow me to move snappy with my keys or clicks 
so I decided to take snappy out of class. I also used the .onkey code to create a help dialog that was available anytime and so that the apple can hide
when users tap the spacebar.

```
def eat_apple():
  apple.hideturtle()
  prompt = 'You win!'
  print(prompt)
  
def help_screen():
  prompt = 'Collect the apples without getting hit by the car. Use keys or mouse to move 
Turtle. Tap space to get apple' 
  print(prompt)

```

```
screen.onkey(help_screen, 'h')
screen.onkey(eat_apple, 'space')
screen.listen()

```
The only downside of having the players use the space bar to get the apple is that players can cheat by simply tapping space without doing anything. 
I had tried making a collision code, but I feel as though it is outside my skillset, so I gave up (but not after trying multiple times and using different 
codes--in the end, I failed to make a collision code). But at least my game lets players know they had won. 

Unfortunately, I could only make one level as I had difficulty setting up the window as you can see at the beginning of my code, I had commented out my code 
for the window as it wasn’t working. 

```
#pygame.init()
#screen = pygame.display.set_mode((0,0),pygame.FULLSCREEN)
#pygame.display.update()
```

I had plans to make a start window, level windows, and you win screen but I couldn’t figure out the code and also realized this was outside my skill. 
I had tried multiple times to make a cool screen for my game but I kept failing or the screen wouldn’t show my code so I decided I would keep this code
instead for my screen setup:

```
def instructions():
  tina.hideturtle()
  time.sleep(2)
  tina.clear()

tina.write("Snappys Adventure!", font=('Arial', 18, 'bold'), align='center')
instructions()

tina.write("Level one!", font=('Arial', 18, 'bold'), align='center')
instructions()

tina.write("Collect the apples without getting hit by the car", font=('Arial', 14, 'bold'), align='center')
instructions()

tina.write("use keys or mouse to move turtle", align='center', font=('Arial', 18, 'bold'))
instructions()

tina.write("type h for help",font=('Arial', 18, 'bold'), align='left')
instructions()

tina.write("tap space once you reach the apple", font=('Arial', 18, 'bold'), align='center')
instructions()
```
Also, fun fact I created the background screen on paint for my minigame and imported it into the screen, somehow, haha. 

```
screen = turtle.Screen()

screen.bgpic("snappys adventures.png")

```
In conclusion, I think I was able to complete 6/8 requirements for my final:

X Have a graphical user interface, responding to key and click events

X Have a constantly available help dialog. This can take many forms but should allow the user to learn what they can do in the program at any time.

X Display information about the program’s state such as score or level

__ Have at least 3 levels, increasing in difficulty

X Extend a custom Turtle Class

X Have a ‘win’ screen

__ Have an iterative interface. That is, the user should be able to perform any number of   supported actions (such as playing the game over and over)

X Use one or more custom images




