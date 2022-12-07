---
layout: post
author: iLiekatz
title: "My Final Snake Game!"
---

## My Final Snake Game Project 
### Introduction 
I really enjoyed the process of working on this project. In prior weeks, I had been working on my own to better understand the concepts we learned during the Turtle section of the class. Because I spent a lot of time going back through the concepts and gaining a better understanding of them in practice, I was able to utilize all of those skills in creating my final project game. 

In the past I was very ambitious with what I wanted to undertake in our programming assignments. For this final project I made sure I chose something that was going to be manageable. I decided to go with creating a Snake game because I thought it would be well within my skill set but still challenging. I was able to break the entire project down into digestible pieces to focus on each week, and this helped me make good progress towards my almost completed game. 

I am extremely proud of the program I created. Unfortunately I wasn’t able to complete all I wanted and what was required of me. A multilevel snake game is a big undertaking. But what I was able to accomplish this past month exceeded my expectations of myself coming into this class.

Because I have written detailed posts about each week's process, I am going to skip going into details with my final update. The following sections outline my last weeks progress, as well as next steps if I had more time to work with this program.

### Final Week of the Process

#### Creating the Food
For the next steps I needed to have the users actually do something productive with the snake. So first I focused on creating the food that snake would be eating. This was relatively easy for me. I knew that I wanted to create a piece of food, and when the snake hits it a new food piece would move to a random location. The random module is one of my favorites to use, so I was excited to use it here.

I created the Food by using a class extension, with inheritance. I had recently spent a lot of time understanding these concepts because they were relatively new to us in this class. I wanted to define functions for the food class, but I also wanted it to have all the functionality of the turtle class. So I used the super method to do so. 

Once I had generated the food, I decided to place the food at random x and y coordinates that were a small distance from the wall so that the snake could actually eat it without hitting the wall and losing. 

#### Detecting food collision 
I wanted to be able to tell when the snake was within a certain distance from the food so I used `turtle.distance(x,y=None)` to do this. It would allow me to compare the distance from the snake turtle to the food turtle. To make sure the code was going to do what I was intending, I first tested this with a print function `print(“nom nom nom”)`.It worked!

#### Creating a Scoreboard
For the scoreboard I knew I wanted to use another turtle. I remembered `turtle.write()` from a previous assignment so I planned for that. After playing around with it some, I realized that I needed to define a score variable set to 0. Each time that the snake hits the food it would update the score with +=1, and the turtle.write() would include the updated score variable. 
Update each time hitting a new piece of food. I haven’t defined levels yet, so I kept this part just with the Score.

#### Game Over
There are two ways to end the snake game. Either by hitting the wall, or hitting the snakes own tail. I knew that either way the game ended then  `game_is_on=False` and this would trigger the for loop of the game to end. I was able to successfully program the game to stop when either of these 2 things happened. I was unsuccessful at getting the “Game Over” to display at the center of the screen. Still at this point I'm unsure why it is not displaying. 
Detecting collision with the wall
600 by 600 screen, x goes from -300 to 300. Y goes to -300 to 300
Create an area that. Can not figure out why it doesn’t display properly

### Next Steps
I wish I had more time to work on this program! It is something I may continue to mess around with over break to try to get an even more completed game, or possibly try to build others. If I had more time there are several things I would like to do.

#### Ideas for Food
Instead of having a circle dot for the food, I thought it would have been really cool to have a list of food PNG icons such as apples, bananas and oranges. I even considered on the final level to have a poison apple that must be avoided or else the snake dies. 

#### Increasing Levels
I didn’t have time to begin defining new levels because my current program took me the entire month to get as far as I had. For different levels I have considered adjusting the speed, using different foods as mentioned, or building extra walls that the snake has to avoid. 

Alas, here is my final snake progr
<iframe src="https://trinket.io/embed/python/5087b50a72" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>am!
