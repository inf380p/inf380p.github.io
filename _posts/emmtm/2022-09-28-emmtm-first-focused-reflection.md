---
layout: post
author: emmtm
title: "My First Focused Reflection"
---

Original Copy of Horoscope Program:
<iframe src="https://trinket.io/embed/python/58322e1cc5" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


Revised Copy of Horoscope Program:
<iframe src="https://trinket.io/embed/python/745502aaad" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>



When working on our functions exercise I found myself a little confused on the best possible use for creating functions, especially in relation to the programs I have created during this class so far. My most complex code that I’ve worked on is a piece of code I have already discussed a bit- one that will give you a weekly horoscope when you input your birth month and day. The code get pretty long, so using my knowledge of functions I decided to just create a module that the main code could pull from that would feed it the screen colors, horoscopes etc so that I can later add in more graphics and hopefully program it to update weekly. 

In short, my code went from looking like this:

```
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
```

To looking like this:

```
Question1 = input("Please enter your birth month. Hint: capitlize month")
if Question1 == ("January"):
  print 
  Question2 = input("Please enter your birth date.")
  #Capricorn Jan1-19
  if Question2 <("20"):
    capricorn()
  else:
    aquarius()
```

With the functions capricorn() etc pulling from the separate module. While this cleaned up my code nicely, and helped me to understand how functions WORK, I guess in this context I don’t quite understand the… function of functions. I feel like either I am not seeing the full potential here, or that this piece of code was not the best piece for me to be practicing them on. Our assignment told us to use a piece of code that has lots of repetitive actions that change a little bit, but still essentially do the same thing. That is why I picked this piece of code, because for each star sign I basically have it change the background color, write the astrological sign name, write traits of that sign, and then print the horoscope.

```
myscreen.bgcolor("#6F7378")
    tina.color("white")
    tina.write("Capricorn",None,"center","40pt bold")
    tina.hideturtle()
    tina.color("#6F7378")
    tina.goto(0,-80)
    tina.color("white")
    tina.write("Ambitious, hardworking, and enterprising",None,"center","14pt bold")
```

But I feel like really I just moved over some of the code into another spot, this function doesn’t really benefit me in any way now besides the fact that I can easily change aspects of what I want to show up for each horoscope without messing with the code that actually makes it show up. I guess I am just looking for some insight as to how I could refactor this code best, and am looking forward to viewing other students' examples of functions to better understand their true potential. I feel like I’ve had a very enjoyable time picking up conditionals, but functions really make my brain hurt! I feel like in programs that run more mathematical algorithms this would be really helpful, but I am also super interested in how I can use them for programs that rely more on visual cues and feedback. 
I think I can do a lot more than I am realizing with functions and would love advice if anyone has any!
