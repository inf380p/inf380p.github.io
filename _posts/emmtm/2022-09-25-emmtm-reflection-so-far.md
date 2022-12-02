---
layout: post
authout: emmtm
title: "Emmalee's Reflection on the Class so Far"

Here's the programs I'm embedding!

    <iframe src="https://trinket.io/embed/python/31b18cd134" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
    <iframe src="https://trinket.io/embed/python/31b18cd134" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
    
One of my biggest motivators for learning code is to be able to program backend content for apps I have designed and conceptualized. I’ve been wanting to figure out how to create algorithms for my apps & thought this class would be a good starting point for me to learn how to integrate machine learning and data algorithms into my designs- but a huge lightbulb went off for me when I realized I had already learned some of the major programming skills that would allow me to do this by the fourth week of class. When creating my horoscope program I was able to get python to analyze the date range of birthdates users inputted and from that, be able to understand which star sign the user was and give them a matching horoscope for that week. 

```
# Corresponding Horo.py code
Question1 = input("Please enter your birth month. Hint: capitlize month")
if Question1 == ("January"):
  print 
  Question2 = input("Please enter your birth date.")
  #Capricorn Jan1-19
  if Question2 <("20"):
    myscreen.bgcolor("#6F7378")
    tina.color("white")
    tina.write("Capricorn",None,"center","40pt bold")
    tina.hideturtle()
    tina.color("#6F7378")
    tina.goto(0,-80)
    tina.color("white")
    tina.write("Ambitious, hardworking, and enterprising",None,"center","14pt bold")
    print('Capricorn: One of your great gifts is the ability to assess a scenario, to accurately read a room. You know how to make the most of any situation, how to bide your time until the perfect opportunity for action presents itself. But what do you do when that ideal moment never arrives? This week, don’t resign yourself to waiting forever or giving up. Though you’re skilled at playing the long game, sometimes the long game means setting your own plans in motion. It’s possible, though not easy, to create the conditions you need.')
  else:
    myscreen.bgcolor("blue")
    tina.color("white")
    tina.write("Aquarius",None,"center","40pt bold")
    tina.hideturtle()
    tina.color("blue")
    tina.goto(0,-80)
    tina.color("white")
    tina.write("Self-reliant, clever, and optimistic.",None,"center","14pt bold")
    print('Aquarius: You’ve been wondering, lately, when exactly the universe will go easy on you. It’s not that you’re feeling sorry for yourself, just that the challenges don’t ever seem to let up. You feel like you’re constantly playing defense, waiting to see what surprises and disappointments and cosmic practical jokes will come next. This week, stop hanging back. The world may not get any gentler — at least not anytime soon — but you can become a more active force in it. Reflect on what kind of life you actually need, and begin planning to make it a reality.')

```

When making this code I realized that the principles I was using to analyze the user data inputs and determine the most appropriate information to give back to them are essentially the same methods used to create algorithms that could analyze user trends in data consumption or habits to then generate suggestions back to those users based on that data. This was very exciting to me as I now feel confident that I have the skills to start experimenting with more complex algorithms for my own personal projects once I am able to more efficiently refactor code such as that placed above.

One of the biggest hurdles I faced when programming this code as well as that I expect to face throughout all of my coding adventures is that I am very, pathetically bad at math, and the mental gymnastics of getting a code to do math for me is for whatever reason even more confusing for me. This is just something I will have to get better with over time, but for this program I was able to bypass some of the computing parts of it by setting a less than conditional for a date range and then assigning the rest of the dates within the range to “else”. I think calculators and programming help boards are going to be my friend when I am dealing with more complex algorithm calculations.

Another thing that is a bit fuzzy for me is how programming is able to translate to digital graphics on my phone, I think that is something I will dive into on my own and hopefully a bit while in class so that I am able to translate my programs to a fully functioning visual experience someday. For now I have just relied on the tools I have available to me in turtle to color the screen and draw shapes, but that has not fully satisfied me. I’m sure there are much more efficient ways to achieve a full graphic- as the simple one I programed here ended up being 130+ lines of code for one image:

```
#Corresponding code
(#draw rectangle
tina.penup()
tina.backward(100)
tina.right(90)
tina.forward(80)
tina.left(90)
tina.pendown()
tina.fill(True)
tina.forward(290)
tina.left(90)
tina.forward(160)
tina.left(90)
tina.forward(290)
tina.left(90)
tina.forward(160)
tina.color("grey")
tina.fill(False)
tina.color("black")

#draw second rectangle
tina.penup()
tina.left(180)
tina.forward(150)
tina.right(90)
tina.forward(10)
tina.pendown()
tina.fill(True)
tina.forward(270)
tina.right(90)
tina.forward(40)
tina.right(90)
tina.forward(270)
tina.right(90)
tina.forward(40)
tina.color("blue")
tina.fill(False)
tina.color("black")

#an square
tina.penup()
tina.right(90)
tina.forward(260)
tina.right(90)
tina.forward(8)
tina.pendown()
tina.fill(True)
tina.forward(25)
tina.right(90)
tina.forward(25)
tina.right(90)
tina.forward(25)
tina.right(90)
tina.forward(25)
tina.color("grey")
tina.fill(False)
tina.color("black")

#text time
tina.penup()
tina.right(90)
tina.forward(18)
tina.right(90)
tina.forward(12)
tina.color("white")
tina.write("x", None,"center","20pt bold")
tina.forward(210)
tina.write("Error",None,"center","15pt bold")
tina.color("black")

#triangle time
tina.penup()
tina.left(90)
tina.forward(50)
tina.right(90)
tina.forward(20)
tina.left(90)
tina.forward(20)
tina.pendown()
tina.fill(True)
tina.left(90)
tina.forward(50)
tina.left(120)
tina.forward(50)
tina.left(120)
tina.forward(50)
tina.color("yellow")
tina.fill(False)
tina.color("black")
tina.penup()
tina.left(120)
tina.forward(25)
tina.left(90)
tina.forward(8)
tina.color("black")
tina.write("!",None,"center","24pt bold")
tina.right(90)
tina.forward(100)
tina.left(90)
tina.forward(10)
tina.color("black")
tina.write("pratice coding!!!",None,"center","15pt bold")
tina.right(90)
tina.right(90)
tina.forward(90)
tina.right(90)
tina.forward(130)
tina.right(90)
tina.forward(30)
tina.pendown()
tina.fill(True)
tina.right(90)
tina.forward(245)
tina.left(90)
tina.forward(30)
tina.left(90)
tina.forward(245)
tina.left(90)
tina.forward(30)
tina.color("grey")
tina.fill(False)
tina.color("black")
tina.penup()
tina.left(180)
tina.forward(10)
tina.right(90)
tina.forward(125)
tina.write("what do you think I'm doing",None,"center","12pt bold")
tina.forward(90)
tina.right(90)
tina.forward(40)
tina.left(210)
tina.stamp())

```

I think refactoring and custom functions will absolutely be my friend when I am undertaking more complicated visuals to accompany my programming. 

The best problem solving methods for me have been without a doubt programming forums and referring to similar problems that others have had to refactor my code and reference when I am attempting something that feels out of my depth. I honestly think problem solving is one of my favorite parts of coding so far, it’s extremely satisfying to spend 3 hours slaving over an answer and then seeing my code finally work the way I want to. 



 
