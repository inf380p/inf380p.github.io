---
layout: post
author: mchakerautexas
title: "Mufaddal's Final Project Reflection"
---

# Final Project Reflection - Astroman
### Introduction
My purpose for taking this class was two fold: To gain an essential skill that would help me in my career, and to learn programming so that I could develop games. Being a frequent video game player, I have always been fascinated by the skill and nuance that goes into creating games, and have wanted to learn how to make some of my own someday. So, I chose to build a game for my final project. The game I built is based of the same concept as Flappy Bird: A revolutionary game that changed the landscape of mobile gaming. It is a skill based game, where the task is to keep the bird afloat and not hit any poles on its endless journey. The concept was so enthralling, that they had the  developer of the game take it down because it was generating overwhelming amounts of revenue.  I wanted to create something similar, but not exactly the same, so I went with Astroman. The idea behind my game is to create a setting with an astronout floating in space, trying to avoid asteroids as he speeds faster into the abyss. I thought that this design was simple enough to be able to pull of, while also having enough to do, to keep me occupied while also letting me put the skills I gained this semester to test.

### The Game
The idea for the game is pretty simple, creating an endless forward moving astronaut, and have asteroids be thrown at them with random speeds and random directions: As long as it is headed on a collision course, it would make the game challenging. I chose not to put any collectibles like coins in the game, as there was nothing the player could do with those coins, and also it would add extra complexity without making the game more enjoyable. The score then, would just increase proportiante to the amount of time you can survive in game. I also set up checkpoints within the game, that would increase the difficulty of the game exponentially the more you survive. With this initial design ready, I decided to embark on the journey for creating this game.

### The Process
Right off the bat, I had no idea how games work (from a development point of view). I felt like I had set out on a mission without a plan. The easy way out would be to cheat, as apparently, this is not the most unique idea out there, but I wanted to test my intuition and challenge myself, so I limited myself to the number of code examples I would see online. I did feel like I had to understand the key concepts of game development to create something like this though, so I made a simpler game before instead. For my Turtle Game assignment, I created air hockey. It was a simple enough game, with the player capable of controlling two paddles, and have to prevent the puck from exiting from the two vertical ends of the screen. I did end up successfully creating a game, but I made some key mistakes in doing so, here are my main takeaways from it:

 - Games need to draw the same things over and over super fast (ideally upto 60 frames per second). To do this, everything needs to be an endless while loop, and the things that are being drawn need to be updated in terms of their position and shape, to give the effect of animation and interaction.
 - Using turtle to draw each one of the frames above, over and over causes weird stuttering. This 'refresh' as it is called in the game dev lingo, is not what turtle is made for. For my air hockey game I drew everything on the screen with a turtle, including the actors, actionable items and non-actionable items as well, which made in every iteration of my loop, I had to call turtle.clear() which led to a blinking effect in my game.
 - Advanced mouse controls like drag events seemed not to work for me, and I didn't spend much more time debugging the issue, so I chose to restrict myself to keyboard type events to interact with the game.
 - The air hockey game I created used native shapes drawn in Turtle. This made the development process cubersome, it would have been cool if I could use images to draw stuff rather than have to make them with turtle (Spoiler alert, that's exactly what I did).

Based on the learnings above, I made sure to:

- Design the game keeping in mind the infinite loops. Designing modules that have functions that can be called over and over to draw key elements on the screen.
- DO NOT DRAW everything. Instead use turtles themselves as actors. It is much easier to control a turtle (they already move like video game characters), and they don't flicker when the loop updates over and over.
- Leave out mouse controls. I never got around to figuring that out. Keyboard controls only.
- Later in class we covered how to draw images in turtle. I used that knowledge extensively, and did not chose to draw a single native shape. Everything images.

With the above learnings, I set out to create my game.

### Milestones
I settled on the following milestones for the game development process:
<table>
<tr>
	<th> Milestone </th>
	<th> Status </th>
</tr>
<tr>
	<td> Create a functional menu, with selectable menu items.</td>
	<td> Done</td>
</tr>
<tr>
	<td> Create a shape for the actual astronaut, and have them animate flying up and down in the menu.</td>
	<td> Done </td>
</tr>
<tr>
	<td> Create shapes for obstacles and background landscape objects(extra!)</td>
	<td> Discarded</td>
</tr>
<tr>
	<td> Implement the start game, and have the person just float up and down based on the user input.</td>
	<td> Done </td>
</tr>
<tr>
	<td> Implement obstacles populating on the screen|Done| |Implement motion.</td>
	<td> Done </td>
</tr>
<tr>
	<td> Implement object collision</td>
	<td> Done </td>
</tr>
<tr>
	<td> Implement scoring</td>
	<td> Done </td>
</tr>
<tr>
	<td> Implement the high score section</td>
	<td> Done </td>
</tr>
<tr>
	<td> Display score and game over splash</td>
	<td> Done </td>
</tr>
<tr>
	<td> Implement saving scores to a file</td>
	<td> Done </td>
</tr>
<tr>
	<td> Add increasing difficulty levels.</td>
	<td> Done </td>
</tr>
</table>

### Challenges
As with any project (and especially software engineering ones), one comes accross many challenges. Here are some of the ones I want to call out:

#### Animating Motion
I had a hard time wrapping my head around the concept of having the player move. I kept thinking in the direction of wanting my player to move forward, but then also have the screen move forward with it with the same speed? But then how would anyone see any motion? The lightbulb moment was to have a background moving back instead. It gives the good illusion of the character moving forward. Relative motion!

#### Okay, but how do you infinitely scroll a backgroud backwards?
From one hurdle onto another, once I had figured out I had to scroll the background backwards, I got stuck on actually figuring out how to do it. The first problem was that (as far as I know), you could only draw images by making them shapes of turtles. To draw a background image (even a static one), I would have to set it to a turtles shape. As it turns out, a you cannot draw over turtle shapes, which meant if I had to use an image as a background, I could not draw anything over it. Then I remembered that turtles have a .stamp() function. So I just hid the turtle and called .stamp() every iteration of my while loop. This made a background appear which I could draw on. But how do I scroll it backwards? To do that, I created two copies of the background image, and had them scroll backwards one after the other. Once the first one scrolled out of the screen, I would place it in front of the second one again. This would go on and one, with the images getting swapped out everytime they go off screen. This created an endless scrolling background.

#### Changing game screens
The next thing was not a challenge, but was a big pain to deal with in terms of code organization. A game has many screens or scenes, and I needed a way to be able to switch off some components and swap them with other components. I came up with a nifty solution for that: Make each screen a Class of its own, with functions of the same name in each module. This 'update' function would be called from the main module, and depending on which module it is being called from, it would swap out the screens.

#### Game difficulty
Another thing that I struggled with was to figure out how to spawn the asteroids and increase difficulty. I experimented with many schemes, and settled on having the asteroids come from the top and bottom of the screen, at random angles gravitating towards the player. The difficulty of the game would then be scaled with the velocity of these asteroids. The faster the asteroids, the harder to avoid them, and the more difficult it becomes to survive.

### Code Organization
As touched on above, I organized the code using Classes. Each screen of the game (Menu, Game, High Score Screen) were made of classes, that had the 'Update' function exposed. Then, it was as simple as just calling the update function of the correct module to display the screen.

Example of a Module:
```
class GameOver:
  astronaut_sprite = 'astronaut_small.png'
  background = 'bg.png'
  
  def __init__(self, screen, change_scene, score, high_score):
    self.screen = screen
    self.change_scene = change_scene
    self.score = score
    self.high_score = high_score
    
    self.bgs = [turtle.Turtle(), turtle.Turtle()]
    self.t = turtle.Turtle()
    self.pointer = turtle.Turtle()
    self.bgpos = (0, 0)
    
    self.bgwidth = 1000
    self.bgmove = 0
    for bg in self.bgs:
      bg.shape(self.background)
      bg.setpos(self.bgpos)
      bg.seth(90)
      bg.speed(0)
      bg.hideturtle()
    
    self.pointer.shape(self.astronaut_sprite)
    self.pointer.seth(90)
    self.pointer.setpos(-5, 100)
    self.pointer.penup()
    
    self.t.hideturtle()
    self.t.color('white')
    self.t.speed(0)
    
    screen.onkey(self.return_to_menu, "Return")

  def write_at_pos(self, text, pos):
    pos[0] -= len(text) * 2.5
    self.t.penup()
    self.t.setpos(pos[0], pos[1])
    self.t.pendown()
    self.t.write(text)
    self.t.penup()

  def draw_menu(self):
    self.t.clear()
    gameOverText = ""
    if(self.score == self.high_score[0]):
      gameOverText = "YOU SET A NEW HIGHSCORE!!! : " + str(self.score)
    else:
      gameOverText = "Game over, you scored :" + str(self.score)
    self.write_at_pos(gameOverText, [0, 10])
    self.write_at_pos("High Score " + str(self.high_score[0]), [0, -10])
    self.write_at_pos("Press Enter to Restart", [0, -30])

  def return_to_menu(self):
    self.change_scene('Menu')
  
  def update(self):
    speed = 10
    if(self.bgmove >= self.bgwidth):
      self.bgpos = (0, self.bgpos[1])
      self.bgmove = 0
      self.bgs = [self.bgs[1], self.bgs[0]]
    self.bgpos = (self.bgpos[0] - speed, self.bgpos[1])
    self.bgmove += speed
    self.bgs[0].setpos(self.bgpos)
    self.bgs[1].setpos(self.bgpos[0] + self.bgwidth, self.bgpos[1])
    for bg in self.bgs:
      bg.stamp()
    self.draw_menu()
```

I also passed in the change_scene function from `main` so that each screen could switch to a different scene. 
This is how the modules are then used:
```
def change_scene(which_scene, update_score=0):
  global scene, high_score
  screen.reset()
  del scene[0]

  if(update_score > high_score[0]):
    write_to_file(text = update_score)
    high_score[0] = update_score
  
  if which_scene == 'Game':
    scene.append(Game(screen, change_scene))
  if which_scene == 'Menu':
    scene.append(Menu(screen, change_scene, high_score))
  if which_scene == 'GameOver':
    scene.append(GameOver(screen, change_scene, update_score, high_score))
  
scene = [Menu(screen, change_scene, high_score)]

while True:
  if(len(scene) > 0):
    scene[0].update()

```
### The Final Product
<iframe src="https://trinket.io/embed/python/70b83865a2" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### Final Thoughts
I can say with a lot of confidence that I am a better professional after having taken this course. The knowledge I gained, not just about coding, but about organizing and reflecting will surely help me further down the line. I have a newfound passion ignited within me to write software, especially games. No matter how frustrating this project was, it taught me valuable lessons, and I will always have this game with me. I have spent a considerable amount of time playing my own game, and it was awesome to see my friends try it out and actually struggle with it's difficulty, while enjoying the gameplay. From here, it's nowhere but up. I will continue to code, write better software and hope to be a capable software engineer someday!
