---
layout: post
author: emmtm
title: Emmalee's Clicky Turtle!
---

Here's the program I'm embedding: 
<iframe src="https://trinket.io/embed/python/6f833bb7d6" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Disclaimer: this code is not fully functioning yet and I would appreciate some help! :)
Update: Professor Elliot helped me figure it out! Full game coming soon<3

For my clicky turtle hack I decided I wanted to make a color guessing game in which the player can choose one of 8 colors. The program would then give the user 20 shades or tones of that color (the example you will see in my code is pink) alongside a one word hint that would help the user guess which shade of pink the program was thinking of. 

To accomplish this I turned the turtles themselves into buttons like so:

```
def pclick(x,y):
  draw_square(p,"white",200,-200,-200)
  p.hideturtle()
  r.hideturtle()
  o.hideturtle()
  ye.hideturtle()
  g.hideturtle()
  b.hideturtle()
  v.hideturtle()
  br.hideturtle()
  pinkclick()


p = turtle.Turtle()
p.speed(20)
p.penup()
p.hideturtle()
p.color("white")
p.goto(-85,30)
p.showturtle()
p.onclick(pclick)
```

This code brings users to the pink tones if they choose the pink guessing game option. 
I then defined each tone alongside its own corresponding turtle button, and had the program choose one of the 20 colors using the random.choice module. Here is an example of how I have each of the pinks set up- all 20 of them are set up this way and the code is at 400 lines so I don’t want to put it all in here, but hopefully this will give an idea of what I am trying to accomplish and where it is going wrong.

```
def pinkclick():
  pinky = turtle.Turtle()
  pinky.speed(20)
  pinky.hideturtle()

def rose():
   print("your hint is 'Rose'.")

  
  list1 = [barbie,rose,fuscia,punch,blush,watermelon,flamingo,rouge,salmon,coral,peach,strawberry,rosewood,lemonade,taffy,bubblegum,balletslipper,crepe,magenta,hotpink]
  random.choice(list1)() 

def rosec(x,y):
    if random.choice(list1) == rose:
      roset.onclick(rosec) == True
      print("That's Right!")
    elif random.choice(list1) != rose:
      roset.onclick(rosec) == False
      print("Try again!")


draw_square(pinky,"#FC94AF",30,-100,80)
  roset = turtle.Turtle()
  roset.speed(20)
  roset.penup()
  roset.hideturtle()
  roset.color("white")
  roset.goto(-65,110)
  roset.showturtle()
  roset.onclick(rosec)
```

So the idea here is if that random.choice chooses the color tone “rose”, it would give users the hint “Rose”. Then the corresponding turtle click “roset.onclick(rosec)” would return the prompt “Thats Right!” when the player clicks on the roset turtle, and would return the prompt “Try again!” if the player clicks on any other corresponding pink color turtle. Everything in the code works pretty much exactly how I was hoping, but I’ve had some trouble getting the click prompts to return the correct printed responses. Currently, the code I have now returns the “Try Again!” text, even when the player is clicking on the correct button. 

I have posted on a couple of help boards with no luck, and I have spent hours trying to correct this! The biggest thing I have learned from this project is that keeping a code journal of failed debugging would have saved me not only an immense amount of time as I definitely wasted time trying things that had already failed to fix it- but also it would be valuable in me being able to show my peers things I had already tried that hadn’t worked. I plan to in the future keep a detailed code journal of each project that details where I went wrong so I can save time in my own debugging and when asking for help. 

I also learned while working on this project that trinket.io is a paired down version of turtle & python and is missing some features that would have made this code a little more elegant- for example in trinket.io I am unable to change the size of the turtle- which forced me to draw colored text boxes around each turtle button instead of just being able to send each turtle to the correct place on the board(while I could have done this, the current turtle size is a bit too small in my opinion for users to see the differences in color tone). 

I didn’t realize how ambitious this program would end up being, and I suspect a knowledge of code looping would help me out a lot in executing this program without so many lines of repeat code. Once I am able to resolve the bug that keeps users from being able to guess correctly, finishing this game will be pretty easy as all I will need to do is repeat the format for the pink guessing game for the other 7 color options. 

This project also made me realize that I love programming and would like to continue my learning of it beyond this class- and even pursue the computer science specialization certificate at the ischool. As frustrating as this process has been to figure out, I never stopped trying. I have spent 30+ hours working on this and felt exhilarated the entire time. In my undergraduate I was getting a graphic design degree, and never understood how my peers could sit down and work on a piece of design for hours at a time. Now that I have started coding I understand that they felt a love for what they were doing that I simply didn't, and I have instead found this love, patience, and perseverance within programming.
