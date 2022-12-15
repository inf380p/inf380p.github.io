---
layout: post
author: rabouti
title: "Rabouti's Final Project"
---

## Final Game: Real Housewives of Beverly Hills Edition  

<iframe src="https://trinket.io/embed/pygame/18382cbf9b" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

 
## Reflection
For my final project, I chose to make a Python Turtle game, for I saw the game option as a great creative outlet and as an opportunity to exemplify my abilities. I went from being a complete novice (i.e., zero experience writing code) to being able to writing my own game with code. 

I am very happy with how my project turned out, considering that I had a lot of difficulty just deciding the official concept of my game. Originally, I had visions that were entirely too ambitious and above my current fluency in Python. I realized I needed to start by making everything simple, then add more detail later. It was very important to me that my concept and my code were as original as possible. I also wanted my game to be somewhat humorous – hence, the theme.   

Since I was having a hard time finalizing my concept and organizing my code, I read multiple articles about Python Turtle games and watched an exorbitant number of tutorials on YouTube for advice and insight. I realized I needed to make connections on areas that were fuzzy for me (i.e., extending a Turtle Class, incorporating external files, loading images, and order of operations). Hence, I started by writing code that was within my realm of fluency and managed my areas of fuzziness one at a time, eventually incorporating them throughout my program to satisfy the project guidelines.  

## My Final Concept 

My game’s theme is “Real Housewives of Beverly Hills.” The objective of the game is for the player, Lisa Vanderpump, to collect as many Giggys (Lisa Vanderpump’s dog from the show "Real Housewives of Beverly Hills" – rest in peace) as possible as they fly around the screen. Lisa’s movement is controlled by the left and right arrow keys – her speed increases upon clicking the up-arrow key. As you collect more Giggys, your score increases and updates on the screen. Moreover, as you collect a specified number of Giggys the level increases. There are three levels. The complexity of each level increases in that your score must increase at a higher rate than the previous level in order to proceed. For instance, in level one you need to collect 5 Giggys to proceed to level two, in level two you need to collect 10 Giiggys to proceed to level three, and in level three you need to collect 15 more Giggys to win. It’s very simple.  

In level 3 there is an “enemy” (I.e., Kyle Richards) to add to the level of difficulty as well. If you pass level three (by collecting 10 Giggys), you “win” the game and a win screen appears - allowing you to go back to the main menu to start over.  

## My Process 

To be honest, my entire process was pretty random and chaotic. To reign in my random and chaotic nature, I invested a lot of time researching how to be more organized while making a game with Python Turtle.  

The problem-solving method that never fails me is the 4 Rs (i.e.,reading, running, ruminating, and retreating). On our previous assignments, I realized that I spent too much time ruminating – which can be very counterproductive. For the final project, I took more time to read, run, and retreat. I believe that by not spending too much of my time ruminating like I have in the past – I've improved.  

Throughout crafting my final project, I tried to maintain calm and positive. I wanted this experience to be fun...so why not include characters from a reality TV show to add some drama and humor? Honestly, the "theme" I chose made this project more enjoyable to work on. I tend to overcomplicate assignments, so my goal for this assignment was to create something that was unique and fun - yet within my abilities of writing code.  

In order to initiate writing the code for my game and fulfilling all of the project requirements, I started by writing code in a format that was very digestible. To keep things simple, I made a screen object, player object that responded to keypresses, and a While loop to ensure movement. Next, I created another turtle object (“mypen”) to draw a square (using a definite for loop) that set boundaries to ensure the player would stay within a certain range and not leave the screen window. To check the location of the turtle and ensure the boundaries were in place, I added “boundary checking” in the main game loop (by checking the x and y coordinate of the player and using the player.right() function to make the player bounce off the boundary line). 

To create more than one “goal” moving around on the screen, before they were shaped like Giggy, I created multiple goals by putting them into a list to hold the maximum number of goals (i.e., Turtle object) and a loop to append the objects in the list. For the player to collect the goals and add to their score, I wrote a function to define collision detection. As I tweaked my game, I added more detail to the main game loop.  

To get the Giggys to "float":

```
goals[count].setposition(random.randint(-200, 200), random.randint(-200, 200))
```
 

## Challenges 

After my game was more developed, I loaded images to change the shape of the player, goals, and background screen, and then started tackling the other requirements for my game. All of the images included in my game were custom made by me. I cropped the images on my phone and resized them (so they would be they right size – pixels by pixels) on an online image editor. It was challenging to get the game screen to state the level and getting the main menu and win screen to run in the correct order. Additionally, it was challenging to get the enemy to function without freezing the entire game! 

Since my game is very simple, I was very concerned with how I was going to implement an external file and dictionaries. However, I created an image dictionary and used a dictionary to construct the main menu. 

Turtle Classes are still vaguely fuzzy for me and I'm not entirely confident in my ability to initiate a Turtle class. Looking back, I should have extended my custom turtle classes when I originally started writing the code for my game.    

Moreover, my ability to write about code and articulate exactly “what I did” throughout my process is rather difficult for me. For I’m unsure when I’ve included too much or too little detail, and my ability to accurately and effectively phrase all of the terminology is a challenge for me. However, I know continually writing about code in this class has helped me make major improvements in my reflections and ability to think and talk about code.  

## Improvements 

I know there are aspects of my project that are not perfect. I’m certain I could refactor and that there are more efficient methods that could be in place. However, I have improved so much throughout the semester. I am proud of my current abilities in writing code and desire to continually learn. Previously, “functions” were fuzzy for me, but now I’m able to write my own functions and implement them in the correct order. Additionally, understanding the order of operations of a program was “fuzzy” for me, but through all of my research, tutorial binging, and writing this final program – I definitely have a better understanding of how a program should flow for it to run as expected, and I’m more organized while writing code. I also understand that code is not always "chronological," or organized chronologically, or organized in the same order that it runs/executes.  

I can humbly admit that I have a lot to learn and there are still connections I have yet to make regarding writing proper Python code (that will probably seem so obvious one day). However, considering that I had zero experience upon my enrollment in “Introduction to Programming,” I am proud of my progress and improvements.   

I’m excited to become more fluent in code and continually make connections to resolve my knowledge gaps. In the future, I plan to allow myself to embrace learning/improving/challenging myself – opposed to putting too much pressure or expectations on myself.  

Personally, the final project was an enjoyable and gratifying experience.
