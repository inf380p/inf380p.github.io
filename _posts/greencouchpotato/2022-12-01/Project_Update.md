---
layout: Post
author: greencouchpotato
title: "Final Project Update"
---

##Milestones
###Basic
1. Create a repository of words based on theme and levels
2. Add hints for each word to make it easier for the user
3. Create the hangman game based on logic (using functions, if-elif statements)
4. Create multiple levels in the game which helps the user progress to the next one after successfully completing one level
5. Create a hangman diagram using turtle as the game progresses
6. Add sections for incorrect letter, correct guess (to be integrated with the blanks) and number of chances left
7. Integrate error messages/success messages where appropriate.
8. Test all use cases and debug

###Ambitious
1. Add in a component of time based task for the higher levels.
2. Create a visually pleasing interface for the user.
3. Provide an on-screen keyboard so the user can click to choose the letter instead of typing it on their keyboard.


##Progress Update
I have written a basic code but I'm encountering errors while executing it. Currently I've troubleshot a lot of bugs which were mainly focussed on the number of chances a user had, the program I wrote initially terminated the  game with the first incorrect guess, so I had to rewrite the code. 
Another error that I'd like to discuss is, a user was able to input multiple letters at a time which again caused errors with my code. I rewrote the code as below to give out an error message to the user - 

```
if len(guess) != 1:
   print('Please enter a single letter.')
```

By far, the trickiest part I had to work on was replacing the blanks with the actual letter in case the user guessed the correct word. I took a lot of time to use the len() funtion to determine the number of the blank, and use it with the 'actualWord' funtion to replace the correct letters using string indices.

##Roadblocks
My code doesn't seem to work the way I want it to. Currently if the user guesses the 1st letter of the word correct, it directly considers the entore word to be correct and ends the game. I need to de-bug this.

##Next Steps
I want to edit my code to integrate levels into the program. As of now it's only designed to accomodate 1 level.
The next thing I'd like to work on is introducing the hints element. When a word is generated randomly, it also needs to automatically populate the appropriate hint. This seems to be more complex than I anticipated. I think I'll edit my words list in a way where a common hint would be applicable no matter which word gets chosen at random. 
After I complete the 2 things above, I want to use turtle to get started on the visual interface for the program.

Here's my trinket link: 
  <iframe src="https://trinket.io/embed/python3/26c5e1dac6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
