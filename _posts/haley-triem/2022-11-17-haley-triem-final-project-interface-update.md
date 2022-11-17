---
layout: post
author: haley-triem
title: "Final Project Interface Plan"
---

# 💾 Final Project Update 💾

For my final project, I am doing a text-based adventure. While I am interested in this type of game beacuse of my English / Creative Writing background, I also thought it would be productive to combine some of the techniques learned from turtle games with techniques learned from data menus (like in our CSV project).

So far, my work has been research and plotting out a vague story line (which is essentially just me figuring out how objects can be interacted with in a room). One of my biggest challenges will be figuring out how to "read" user input to allow users to do an action. For example, if a user wants to find out the contents of a book, they might `examine` it or `read` it or `look at` it.

I've started by testing using a loop statement in the beginning of the game, as well as blocking out different rooms that might be in the game. Depending on how long it takes me to develop the code, I might have to narrow down the amount of rooms and objects people can interact with for the time being. I am okay with this, however, because I know that code is iterative and can change.

I found a brilliant article breaking down how the famous text-based adventure game, Zork, processes its words. Its in a different language, and won't be able to create something so complex, but I can at least study it to learn about how code recognizes different parts of speech:

### Article: 

https://medium.com/swlh/zork-the-great-inner-workings-b68012952bdc

### I've also been looking through Zork's source code, posted on GitHub:

https://github.com/MITDDC/zork/commit/65785b482860a1e99b8d691b5e5f72c3c3bc9cc1#diff-085104a6c43f3677699abd31c36a347be2245710939a9721c94c01b4f3f7a42b

# 📷 The Game So Far 📷

Other than that, the biggest thing I'm trying to figure out is how to slice up people's inputs and understand different parts of them. Below, you can find my skeleton of a game where I figured out the basic while loop that will likely be a staple in the game, along with a testing zone where I've tried to flesh out parsing. Wish me luck!

### Game Skeleton:

<iframe src="https://trinket.io/embed/python3/ee798d9e75" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### Test Trinket:

<iframe src="https://trinket.io/embed/python3/36f076f8dd" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
