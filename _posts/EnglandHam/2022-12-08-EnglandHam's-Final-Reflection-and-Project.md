---
layout: post
author: EnglandHam
title: Soojin Park's Final Reflection and Project
---

## Looking back to the beginning of the project :open_mouth:
When I first started this project, I was set on making a turtle project but wasn't sure in which direction I wanted to partake. In class, we have previously discussed what each IDLE (Integrated Development and Learning Environment) and Python 3 provide with their possibilities, but it made me feel more overwhelmed to learn how to adapt to the new system. Since I was most familiar with standard Python used in our Trinket, I decided to take this final project as an opportunity to utilize two things I had the most fun exploring: a story-telling video game and using the `#!/bin/python3` shebang to implement Python 3 capabilities to make my game happen (which I later discuss more in-depth).  

My game first started as a role-playing game where the princess turtle Tina was lost and stuck in a pond. In this [game](https://trinket.io/python/1be9239cce), the heroic turtle was going to look for the lost princess and fight enemies. However, I wanted to challenge myself to make a more complex `clicky` function and have multiple turtles interact with each other using `while():` and `for` loops rather than a linear hero's adventure game. So I followed through my *soft* milestones and converted the game into an interactive cooking game called [Danny's Turtle Restaurant Game!](https://trinket.io/python/620f82fb56) :fork_and_knife: 

### (soft initial) Milestones:
- [x] Reflect back on all the Trinkets and homework problems that stood out to me (week 1) <sup> For me, I had the most fun with Clicky TurtleHeck and `Strings` and `Loops` homework sections so I wanted to center my game around those three things </sup>
- [x] Narrow down the project idea into one and set another milestones that's do-able for me; discuss with the professor to see the possibilities (week 1) <sup> Setting up the storyboard helped me narrow down to one idea, the cooking game. </sup>
- [x] Set up storyboard and Python concepts I want to incorporate into the game (week 1) 
- [ ] Try to focus on building the basic and external file, specifically for level 1 (week 2) I am a bit scared this will lead me to focus more on the front-end visualization <sup> Told myself, it's all about the coding process more than anything! Do not be scared to fail! :tophat: </sup>
- [ ] Wrap up the project, fix minor bugs, try to get it play-tested; contact the professor if any major issues rise (week 4/5)
- [ ] Show off my game to my awesome classmates through Github(week 5/6)

Setting these big milestones for the overall game helped me stay on track and not fall behind. I was already on Week 2 and ready to focus deeper on the coding part of the game. I initially felt super frustrated because I had so many things I wanted to code first but wasn't sure which parts to tackle first and which parts will work without me having the rest of the game made in conjunction. Luckily, we learned about *debugging* tools such as the `print` function, allowing me to analyze which part of the code worked and which didn't.


## My [first version](https://trinket.io/python/620f82fb56) reflection :satisfied:
Now that I have a direction for my game, I set up game-specific milestones to keep my progress in check while meeting the final project requirements.

- [ ] create a game menu that takes you to the game or tutorial (CSV external file for tutorial?) 
- [x] create background for level 1 
- [ ] create ingredients using class or dictionary 
- [ ] have a customer turtle that shows what kind of burger it wants
- [ ] see the list of the ingredients Danny the chef has picked 
- [ ] be able to serve the burger to the customer turtle 
- [ ] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [x] have a win screen 
- [ ] create level 2 after meeting all those requirements
- [ ] create level 3 after meeting all those requirements 
- [ ] be able to exit out of the game whenever or go back to the menu screen 
- [ ] have a help icon at the top where the user can access at any time 

One of the biggest struggles I had when getting to this version was uploading the custom image. It wasn't so much of incorporating the image into the code, I didn't know how to get Python to read my local image file saved onto my computer. I couldn't figure out how to upload an image with a standard Python Trinket. I have tried downloading custom libraries, importing `urllib.request` , visiting the Trinket custom modules page, and even trying Tkinter by inputting this code:

```python
Import tkinter
from tkinter import *
from PIL import Image, ImageTk

image1 = Image.open("<path/turtle_background.png")
test = ImageTk.PhotoImage(image1)
```
I kept running into an error for unsupported module. It wasn't until I saw the other Trinket example like the [Space Game](https://trinket.io/python/c744c2b3e2) in my library that there was an image upload icon for the Trinket. Afterwards, I  could either use the `turtle.addshape()` for buttons and do this for my background: 

```python
screen = turtle.Screen()
screen.bgpic("turtle_background.png")
```
Now that I figured out how to get the game background going, I can set up ingredients where the plates are and have Danny pick them up using `myscreen.onkey()` and `clicky` function. I am very excited to get started on it! 


## My [second version](https://trinket.io/python/9d286ceaf3) reflection :sweat_drops:
By this point, I successfully had the menu option running in the console where it could start the game and use an external `tutorial.csv` file when prompted. I was able to utilize `#!/bin/python3` shebang to import the `tutorial.csv` file by looking back to our [CSV assignment](https://github.com/inf380p/inf380p.github.io/blob/main/_posts/EnglandHam/2022-11-03-Revised-CSV-Code-Reflection-EnglandHam.md). I struggled a lot when I started having multiple modules and learned that the custom modules can't import from `main` module. I had to move my actual restaurant game content to `game.py` and have the `menu()` on the `main` module. 

With all the ingredients being drawn by Sally the turtle, I wanted Danny to be able to get on the ingredient and "pick up" the ingredients like :tomato: or :leafy_green: by setting the limitation range in coordinates where the `turtle.pos()` will trigger an event once it's inside the range. At first, I tried to code it so that Danny automatically picks up the bun the moment he is in the location of the bun by initially writing the code like this: 

```python
 danny_location = danny.pos()
  bun_location = (-170,-260)
  print(int(danny_location[0]))
  print(range (bun_location[1],bun_location[0]))
  
  while int(danny.pos()[0]) in range (bun_location[1],bun_location[0]):
    print("danny found bun")
 ```
 
Even though the code detected Danny's location and printed `print(range (bun_location[1],bun_location[0]))` it wasn't successfully printing out the location of the bun. Rather, it printed out the range of coordinates between Danny's initial position to the bun's position. I realized automatic detection of the coordinates using arrow keys is going to be difficult. To tackle this issue, I resorted to using the `clicky` function to activate the event once the turtle lands on the range of the coordinates where the specific ingredient is... and it worked! :star2: Here is my code below: 

```python
 #when danny touches the bun, it prints out danny found bun. Also, sally puts it on the customer plate 
 danny_location = danny.pos()
  bun_location = (-170,-260)
  print(int(danny_location[0]))
  print(range (bun_location[1],bun_location[0]))
  
  while int(danny.pos()[0]) in range (bun_location[1],bun_location[0]):
    print("danny found bun")
 ```
 
By this point, I learned that it's more realistic to have smaller milestones that are more doable and not so much dependent on the prospect of completing the final requirements. ~~I have cried multiple times~~ It is more important for me to really learn during this process of trial and error rather than just trying to get the game delivered. Yes, grades are important, but what the professor and I really care about is **making individual progress and implementing all the Python concepts we have learned over the semester.** Thus, I set up different types of milestones that help me focus on smaller goals and personal growth as a programmer without feeling narrow-sighted by end goals.

- [x] create a game menu that takes you to the game or tutorial 
- [x] create background for level 1 
- [x] create ingredients using class or dictionary 
- [ ] have a customer turtle that shows what kind of burger it wants
- [ ] see the list of the ingredients Danny the chef has picked 
- [x] be able to serve the burger to the customer turtle 
- [ ] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [x] have a win screen 
- [ ] create level 2 after meeting all those requirements
- [ ] create level 3 after meeting all those requirements 
- [ ] be able to exit out of the game whenever or go back to the menu screen 
- [ ] have a help icon at the top where the user can access it at any time 
- [ ] have a menu icon at the top where the user can access it at any time

With this new milestone list, I can focus better on individual aspects of the game without getting ahead of myself with big-picture goals. For example, creating the serving food as a milestone helps me gauge further my next to-do tasks related to completing that goal. The next step was to create the serve button with a custom function, `clicky` function, and `print` input that lets the player know food has been submitted. I got reminded from our last project update reminded me how important it is to set up goals that are realistic and doable (while still challenging yourself, of course). :punch:


## My [third version](https://trinket.io/python/0fb1eb79e1) reflection :notes:
By the end of the second version, Danny the turtle and the `clicky` function only worked if Danny is on top of an ingredient or the "serve" text. Through playtesting, even with the help of the tutorial, this specific trigger interaction is a bit wonky and hard for players to get used to (perhaps only if the trigger interaction worked that way with the ingredient– like Cooking Mama or Overcooked mechanics :shipit:). Using what I realized from my first iteration, I uploaded the button images and put them on the screen using the built-in `screen.addshape` function. I actually learned a few more interesting things when it comes to images being used on Trinket: 
- Images work better as PNG and JPEG on Trinket compared to other formats like GIF (requires different coding input than standard flat image), JPG3, HEIC
- Moving the location of the image to a specific spot on the canvas may require different coordinates depending on that PNG image's amount of negative space
- Despite PyGame Trinket requiring similar upload method as normal Python Trinket, the code to input the image is very different 

It was satisfying to see all the buttons and backgrounds I drew worked together to make the game look complete. Having specific milestones helped me gauge what kind of buttons are needed, allowing me to focus on creating specific functions for each button for my next iteration. However, I ran into a very odd issue where `turtle.shape()` wasn't working properly inside the `game()` function in `game.py` module– specifically when I tried to use `turtle.shape("turtle")`. All the other built-in turtle shapes worked. I ended up moving `danny.shape("turtle)` to the `animations.py` module. I am still not sure why this happened, but it must be something to do with how Python reads the order of importing files and top of all the images being loaded onto the canvas.

Since the `main` module cannot be imported onto other custom modules, I had issues trying to make the menu button bring the menu up. When I tried to move the entire `menu()` script below into the `game.py`, ~~it basically broke the entire game~~ it caused the `clicky` function to not work properly which in return, broke Danny's trigger interaction and the overall game mechanics. :weary:

```python
def menu():
    print("Welcome to Danny's Turtle Restaurant Game")
    print()

    choice = input("""
                      A: Start Game
                      B: Tutorial
                      C: Exit

                      Please enter your choice: """)

    if choice == "A" or choice =="a":
      game()
    elif choice == "B" or choice =="b": #uses tutorial csv
      filename = "tutorial.csv"
      
      # Get a list of dictionaries from CSV file
      
      def tutorial():
      
        txtfile = open(filename)
        
        
        with txtfile as f:
          game_lines = f.readlines()

        # Sample the data to get a sense of what it is (done)
        print(game_lines[0:4])
 
      tutorial()
    elif choice=="C" or choice=="c":
        #sys.exit
        print("Please try again")
    else:
        print("You must only select either A, B, or C")
        print("Please try again")
```

I wasn't sure why the menu was breaking the game, but I can guess it has something to do with updating the game over and over again and perhaps the menu needs to be on `while` loop. On the positive side, the iterative menu was *technically* working as the `print()` statements were printing over and over again depending on what the player picked. However, the canvas wasn't properly loading. After struggling for a few hours, I decided to go take a shower and walk my cute dog to refresh my mind. I decided to do some research and jot down any functions related to canvas and menu updates including but not limited to `turtle.tracer()`, `clearscreen()`, `turtle.update()`, `exitonclick()`, `screen.reset()`, etc. I am very excited about where this will lead me to! :satisfied:


## My [fourth version](https://trinket.io/python/2a18656c75) reflection :notes:
I still coudn't figure out why the screen wasn't updating properly when a player selects the menu again. However, by this version, **all the buttons were working!!!** :clap: :clap: :clap: Here is what I have completed so far: 

- [x] create a game menu that takes you to the game or tutorial 
- [x] create background for level 1 
- [x] create ingredients using class or dictionary 
- [ ] have a customer turtle that shows what kind of burger it wants
- [x] see the list of the ingredients Danny the chef has picked 
- [x] be able to serve the burger to the customer turtle 
- [x] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [x] have a win screen <sup> not yet implemented into the game for testing purposes </sup>
- [x] create level 2 after meeting all those requirements
- [x] create level 3 after meeting all those requirements 
- [ ] ~~be able to exit out of the game whenever or go back to the menu screen~~
- [x] have a help icon at the top where the user can access it at any time 
- [x] have a menu icon at the top where the user can access it at any time
- [ ] have a custom turtle class


Practicing the `clicky` function throughout previous iterations prepared me to use `def function(x,y)` in various manners. I initially designated a turtle for each button and then assigned custom functions for each button's role. For instance, when it comes to serving the ingredients, I used `Servy.turtle` to do:  

```python
  def serve(x,y):
    if ingredients == hamburger:
      print("Hamburger succesfully served!")
      screen.resetscreen()
    else:
      for ingredient in ingredients:
        ingredients.remove(ingredient)
      print("Oops, try again!")

  servy2.onclick(serve)
  ```
Here, the coordinates of the "SERVE" button are measured so that when the player clicks within the range of the button coordinates, it checks the hamburger ingredients and prints them out accordingly. The same thing can be seen with `checky.turtle` for checking ingredients: 

```python
  def check(x,y):
    print("Here are your current ingredients in order:" + str(ingredients))
        
  checky.onclick(check)
 ```
I used similar logic to make sure the turtle reads the coordinates of the "CHECK INGREDIENTS" button and prints out the ingredients that are in `string`. This logic was applied to other buttons as well. I am really proud of how far I have gotten with this game! :v: The fact that Danny can make a normal hamburger, cheeseburger, and deluxe burger while being able to do multiple functions surprises me. I am barely scratching the surface of the capacity of Python! Unfortunately, I am still struggling with the iterative `menu()` function so my next goals before the final deadline are to check off all the in-game milestones (win screen, customer turtle, iterative menu) and the big goal initial milestone (custom turtle class, bug-free, cleaning up the codes)! 


## My [fifth aka last version](https://trinket.io/python/bdac6c001e) reflection :notes:
With this last version, I activated the win screen (try playing my game, I *love* my win screen, very cute! Inspired by the ClickyTurtle exercise), customer turtle coming in and asking for the order, and the game menu that's constantly running for a player to choose from. I began to spend the rest of my day cleaning up my codes and re-writing the comments to be more elaborate for other programmers to read and follow. This version completed the following milestones: 

### in-game milestones
- [x] create a game menu that takes you to the game or tutorial 
- [x] create background for level 1 
- [x] create ~~ingredients~~ menu using class or dictionary 
- [x] have a customer turtle that shows what kind of burger it wants
- [x] see the list of the ingredients Danny the chef has picked 
- [x] be able to serve the burger to the customer turtle 
- [x] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [x] have a win screen <sup> not yet implemented into the game for testing purposes </sup>
- [x] create level 2 after meeting all those requirements
- [x] create level 3 after meeting all those requirements 
- [ ] ~~be able to exit out of the game whenever or go back to the menu screen~~
- [x] have a help icon at the top where the user can access it at any time 
- [x] ~~have a menu icon at the top where the user can access it at any time~~ have a iterative menu the user can access it at any time
- [x] have a custom turtle class

### big milestones (combined with the two initial milestones)
- [x] Reflect back on all the Trinkets and homework problems that stood out to me (week 1) <sup> For me, I had the most fun with Clicky TurtleHeck and `Strings` and `Loops` homework sections so I wanted to center my game around those three things </sup>
- [x] Narrow down the project idea into one and set another milestones that's do-able for me; discuss with the professor to see the possibilities (week 1) <sup> Setting up the storyboard helped me narrow down to one idea, the cooking game. </sup>
- [x] Set up storyboard and Python concepts I want to incorporate into the game (week 1) 
- [x] Try to focus on building the basic and external file, specifically for level 1 (week 2) I am a bit scared this will lead me to focus more on the front-end visualization <sup> Told myself, it's all about the coding process more than anything! Do not be scared to fail! :tophat: </sup>
- [x] Wrap up the project, fix minor bugs, try to get it play-tested; contact the professor if any major issues rise (week 4/5)
- [x] Show off my game to my awesome classmates through Github(week 5/6)

Being able to check off most of the goals on the milestones made me really proud of myself. I couldn't have come this far without all the help and references from my classmates, family, and professor. :relieved: I especially wanted to thank my final project update Github partner and her beautifully explained [final project update post](https://github.com/inf380p/inf380p.github.io/blob/main/_posts/alm7468/2022-11-30-Final-Game-Since-Last-Class-alm7468.md), April @alm7468 .
Through her game code and explanation of her hard work, I was able to figure out how to make the menu iterative by incorporating the `while` loop. I was also able to implement `screen.reset()` function to fix the screen update issue when running the game twice or more in a row. Professor Hauser gave me some insights into why the issue was happening in the first place. 

> "You might need to set 'screen.tracer(True)' or call 'screen.update()' earlier on, because after you set 'screen.tracer(False)', none of the things that were drawn the first time around will get drawn without either of those. i.e. the first time through you're assuming the tracer is on. Once you turn it off, it stays off for that screen." -Professor Hauser 

With the help from these two + discussing the code with several of my programmer friends, my menu was iterative and working! Here is the code below: 

```python
#creating dictionary for game options
food_dict = {
    "1": "Level One: Hamburger",
    "2": "Level Two: Cheeseburger",
    "3": "Level Three: Deluxeburger",
    "4": "Help",
    "5": "Exit",
}
 
print("Welcome to Danny's Turtle Restaurant Game! Make a burger by having Danny hover the ingredient and clicking on the ingredient, and serve the food.")
print(food_dict)

#lays out menu options

while True:
    
    
    choice = input("Pick menu options")

    screen=turtle.Screen()
    screen.reset()
      
    if choice == "1":
      screen=turtle.Screen()
      screen.clearscreen()
      game()
    if choice == "2":
      screen=turtle.Screen()
      screen.reset()
      screen.update()
      game2()
    if choice == "3":
      screen=turtle.Screen()
      screen.reset()
      game3()
    elif choice == "4":
      print(instructions)
    elif choice== "5":
        print("Ending Game - Thanks for cooking with us!")
        exit()
    #else:
     #   screen=turtle.Screen()
      #  screen.reset()
       # print("You must only select 1-5")
        #print("Please try again")
```
and for my in-game, I used: 

```python
def game():
  #open the custom image
  
  screen = turtle.Screen()
  screen.tracer(True)
  setup(screen)
  screen.update()
```

Unfortunately, I was running into a similar issue while trying to get the "MENU" button to work. Even though the console displayed all the `print()` correctly, it had similar issues where the canvas wasn't loading properly despite having `screen.reset()` and `screen.update()`. However, I am still happy that the player still has the iterative menu to choose from. With more time, I want to improve these things about my game: 
- make the "MENU" `clicky` button work with proper `screen.update()` and `screen.reset()`
- learn more in-depth about `class` and `dict` and utilize them more into the game to make the codes more efficient and flexible
- make `clicky` function work more accurately where the buttons work without printing out `danny = turtle.Turtle()` if he is hovering on the ingredient
- have error screen message 
- implement the menu to be on the canvas and clickable 

Overall, I am really happy with the progress I have made so far! I barely knew about anything about Python at the beginning of the class, so being able to see all these codes work together where I can make a game out of Turtle library makes me quite proud. :grin: :grin: Here is the embedded Trinket of my final game: 
<iframe src="https://trinket.io/embed/python/bdac6c001e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe> 

:warning: **Attention:  My game fully works only if it's on the full-screen!!**  :warning:

## End of the semester conclusion :page_with_curl:
***Takes deep breaths*** Where to even begin... This semester has been a long journey for me, personally and academically. I struggled with this class the most since this is the first time in years I took a course outside of the UX/UI field and learned that I don't have the best aptitude when it comes to coding. Programming often doesn’t provide automatic visual guidance and user feedback that keeps me on track of my progress and verifies whether the outcomes are positive or not (I got way too comfortable with UX/UI work haha). Being able to code is a slow journey that can be rewarding when it truly reflects all the effort you put in each hour and every struggle. 

I always overheard my friends talking about Python becoming one of the most popular languages in the tech fields, so curiosity and desire to understand other programmers led me to start this class, but throughout the semester, I learned that coding requires you to think, reflect, and tackle the problems in different ways than our conventional methods of solving problems. This class challenged me to use my overwhelming fear of the unknown by breaking them down and tackling them one by one without letting myself get lost. I also learned the importance of resetting your mindset by taking a mental break to see the bigger picture. I came out of this class feeling more confident in my own abilities and to be a better version of myself by diving deeper into scary yet powerful knowledge like Python. 

Even though I am not pursuing programming as a professional degree, I found the joys of coding in my own style and thinking like a programmer. I want to continue learning in Runestone and take on other coding exercises that will help me become more comfortable with Python. In addition to that, I really liked that the class familiarized everyone with GitHub markdowns, push/pull requests, and `config.yml` which all come in handy when working with developers and programmers. 


## Credits :shipit:
I couldn't have come this far without all the help and advice from my classmates, family, and professor Hauser who have pushed me to work harder and continue this class. I am lucky to have this experience surrounded by intellectual people. 
Thank you for everything. Go Turtles!! :turtle: :turtle: :turtle:
