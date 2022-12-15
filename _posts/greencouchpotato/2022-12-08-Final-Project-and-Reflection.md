---
layout: post
author: greencouchpotato
title: "Final Project and Reflection"
---

##Introduction about me

I'm a first year grad student at School of Information and I've coded for the first time in this class. I've always viewed coding as a super cool skill that requires a lot of mental power and assumed it to be out of my scope. However, as a UX design student, I know it's inevitable for me to work with software development professionals in my career. So my main goal of taking this class was to understand how coding works, how I can keep learning this skill even after the class and to understand the scope and limitations of programming.

##Project Introduction

Coming to the project, throughout my childhood, I've always played Hangman on a piece of paper with my friends back in India. I thought it would be pretty cool to write a code for it. Althought it seemed to be simple, this code was the most challenging and most rewarding piece I've ever written. I can't wait for you to play the game and see for yourself!

##Trinket Link

<iframe src="https://trinket.io/embed/python/65d7dc2d54" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

##My Process

This hangman game is both text-based and turtle-based code. I began my process by listing out the different features I wanted to include. In hindsight, I had quite a lot of ambitious goals for the project. Although seemingly simple, the code had a lot of parts which need to work together (simultaneously) to update the interface and also the console to provide a live update to the user. My goals for the project were - 
- To design a simple and minimalistic interface that highlights key parts of the game
- Include elements like : status update of game level, hint field, a stationary animation, moving animation that reacts to the user's input, blanks that are automatically filled when the user guesses a letter
- In the back-end I needed a few more elements like: tutles for animation, possible error mitigating scenarios and messages, levels, instructions and other game related messages, help and exit buttons


###Interface

Because the code had so many parts that need to be referenced in other sections of the code, I started at the beginning because the logic got too complicated too quickly in my mind. I began with importing the relevant modules into python trinket using the code below -

```
import animations
import random
import turtle
import time
```

I imported these in different combinations in both my 'main.py' and in another screen that I created named 'animations.py'. These helped me import the relevant pre-built functions into my trinket before I began writing code. Once imported, I write down the code for 'Introducing the game'. It was a straight forward turtle command chain which went to different positions on the screen and write some sentences. I write the def setup(): function for this purpose.
  
  Once the set up was done, I also imported a picture into the trinket file to set the background for the code. Once I uploaded the picture, I passed it as an argument to 'myscreen.bgpic' to set it as the background. This part was straightforward since Trinket provided the documentation on how to set an image as the background. 
  
###Onscreen clickly turtle

I then used the onscreen clicky turtle command to enable the user to click anywhere on the screen to first clear the screen (which contained the introduction information) and then also defined some "buttons" on the top right corner that act as a help & exit buttons to provide options for the user through out the app.

At first it took me a while to figure out how to introduce buttons. From the internet I noticed that one needed tkinter function inbuilt to draw buttons. Because it wasn't the case, I took the best alternative which was to define an area using a set of coordinates on the screen. Once the area was defined, I passed a function which tells python to listen to any clicks within this area and then perform a set of actions based on it. I called the function within each set of command for a level to populate the screen each time the screen was cleared.

This took a while for me to figure out because although I had defined the button which worked, it only worked for introduction screen and disappeared with the click to start new level. I immediately realised that the order was the issue and moved it within the function which populates the screen elements for level 1. This worked!! But to ensure this repeated for all levels, I called this function within the other functions that populated the screen for each new level. Here's the code for designing the help and exit buttons - 

```
def helpIcon(x,y):
 sally.goto(x,y)
 if (120 < x < 160) and (180 < y < 200):
   print("To play the game, please read the below instructions")
   print ("1. Read the hint and count the number of blanks you see on screen.")
   print ("2. Try to guess the word by entering a single alphabet in this textbox")
   print ("3. If you make 6 incorrect guesses, the game is over and you can start again")
   print ("Click here and enter your guess now.")
 elif (160 < x < 200) and (180 < y < 200): 
   print ("You just exit the game")
   break
 ```

###Hangman animations

Once the screen was set up, I proceeded to create turtle positions and movements which will draw the hangman animation at each stage. It was tricky to figure out how to pass these as arguments or reactive execution to something else, so although I designed these functions and called them to test them, I didn't have an idea as to how and when I would use them. So I created the animations and parked them.

###Main code

Coming to the main function of the code. This was tricky and I tried a few methods to design the interface. Here I had to first figure out how to make blanks appear on the screen when the random function chooses a word from the list at random. Then I had to figure out how the program would check and validate the guessed letter and fill the blanks accordingly. Things I had to keep in mind here were:
- let the user guess an alphabet
- the program should validate if each entered character is an alphabet and not a special character or number
- the user needs to enter only one alphabet at a time and an error message should be shown when the input is not an alphabet. All the while ensuring that the input loop doesn't break.
- the number of guesses shouldn't exceed the maximum incorrect guesses limit (which is 6 guesses)
- if the user re-enters an alphabet within the same level, an error message should be shown without making the user lose a chance.
- and at the end, the hangman animations should be executed whenever an incorrect letter is guessed. 

Here's the code I've written for the fitst 3 specifications -  

```
def getGuess(alreadyGuessed):
  gameIsDone=False
  while True:
    guess = input("Guess a letter: ")
    if len(guess) != 1:
        print('Please click in the text-box (console) and then enter a SINGLE letter.')
    elif guess in alreadyGuessed:
        print('You guessed this letter already. Choose a new letter.')
    elif guess not in 'abcdefghijklmnopqrstuvwxyz':
        print('Please enter a LETTER.')
    else:
        return guess
 ```
 
 The most important thing for me to figure out was how to ensure the correct alphabets reflected on the screen. I've tried multiple methods by assigning a number to each alphabet by converting the word into a list, but then I remembered the 'for' function which basically works similarly but is more straightforward and uncomplicated. Here's my most favourite part of the code -
 
```
for i in actualWord:
      if i == guess:
        sally.write(guess.upper() + ' ', True, font=("Courier", 14, "normal"))
      elif i != guess:
        sally.write('_ ', True, font=("Courier", 14, "normal")) 
```

 
For the animations, it took me a day to figure it out, but then I realised that the length of the incorrect words could be inline with the number of hangman part to be drawn. So I've used an if function that identifies to the number of incorrect alphabets to execute the animation.

```
if len(incorrectGuess) == 1:
        picture1(myscreen,sally)
```

But the problem was the incorrect alphabets had to be tracked. When I first created incorrect alphabets, the function just printed the incorrect alphabet if it was incorrect. With the next incorrect alphabet, the previous one vanished and the new one was printed. So I had to inform the program to not re-initiate the string and to store the alphabet as a list instead. This allowed me to refer to the number easily and the function worked now. 

```
while (incorrectCount > 0):
      incorrectLetters = []
       if guess not in actualWord:
        incorrectGuess += [guess]
        print ( 'Incorrect Guesses: ' , incorrectGuess)
```

From then on, it was simple enough for me to introduce levels and play again options by defining a function for these and calling them when a game ends with the appropriate messages.


##Reflection

One thing I realised was coding is all about how to solve a problem in the most creative way possible by using logic. There were many instances throughout my code where I've written a tedious long code which complicated things very quickly and I had to delete it to find a creative way to write a much shorter code by using the inbuilt functions. 
This program tested my patience and will. There were days when I couldn't make something work and I had stayed away from the project for a few days before coming back to it and trying again. In some cases I was able to look at the problem from a new lens and was able to find a solution. In others, I repeatedly tried but couldn't change things. For me because I'm not familiar with any other programming language, I didn't know what caused the error -
- it was a simple one like indentation or forgetting a character
- in other cases, the function I'm using or the way I'm approaching the problem was incorrect
- and in some cases the sequence where I called a particular function was not logical and therefore even when the code was right, it couldn't be executed.

It was through a lot of help from the modules in the trinket and google, I was able to try a different combination of iterations to finally complete my hangman game that is simple, straightforward and largely bug-free!

I'm very proud of my program and am happy with the progress that I've made in the class so far. From not being able to even read code to understanding how to develop a simple game, in my opinion I've done good progress

##Next Steps and Conclusion

Having completed one project, it's the method of thinking creatively to solve a problem that makes me love coding. I want to try and continue to develop this game with more complexity. I read about code challenges in an article somewhere, I would like to keep trying those challenges to further develop my skill and design thinking. Overall, I had a great class and I'm proud of how far I've come and all the things I've learnt.
