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

# ✏️ An Update After Class ✏️

After discussing with my project partner, I reevaluated some of my goals. I realized that it's a little too ambitious to try to do natural language processing, so I might go off of a data menu as we did in our .CSV file project. Another thing my project partner put on my radar was that I probably need to use an inventory. He suggested making an inventory by using a list, and then appending different objects when the player "picked them up."

The final piece of advice that my partner gave was not biting off more than I can chew. I had grand ideas about escape rooms and multiple endings, but my partner suggested to start by creating a main loop that the player can go through, and then adding on other branches later once I am successful with that main loop. In light of that, here are my goals:

> 1. Create an inventory with ways for players to add to inventory
> 2. Create a main menu that players can go through
> 3. Map out conditionals that require players to puzzle their way through and get the right items in the right order
> 4. Bonus: create a move counter that makes the player lose if they don't solve the puzzle quickly enough

# ✏️ An Update From Notes I Took During Thanksgiving Break ✏️

During Thanksgiving break, I tried to take a relaxed attitude with the project, so that I could get some work done but still have a break. This is where I started doing my mastermind mini-game: the player knows that the power is off, and they have to guess which lightswitches to turn on. This game was amazing practice for understanding lists and changing integers to strings and vice versa through `.append()`. Here's a bit of my progress:

I created a binary key through randomly generated numbers and split the key with spaces and removed the extra space at the end:

```python
import random

# function for creating a random binary string
def master_key_string():
  
  # store string in master variable
  master = ""
  
  # loop for range of four
  for i in range(4):
    master_binary = str(random.randint(0,1))
    
    master += (master_binary + " ")
    
  return(master)

generated_key = master_key_string()
stripped_key = generated_key.rstrip()

# print(generated_key)
print(stripped_key)
split_key = stripped_key.split(" ")

print(split_key)
```
Then, I converted the split key from 1's and 0's to X's and O's:

```python
letter_key = []
for entry in split_key:
  s = ""
  conversion = {"0":"O", "1":"X"}
  for i in entry:
    s+=conversion[i]
  letter_key.append(s)
```

Here is me struggling through trying to get the user's input of X's and O's to transform back to 1's and 0's:

```python
  mydict = {"O":"0", "X":"1"}
  valueslist = list(mydict.values())
  print(valueslist)
```


```python
  mydict = {"O":"0", "X":"1"}
  list_user_key = []
  for key in mydict:
    list_user_key.append(mydict[key])
  print(list_user_key)
```

Finally, I realized I could just switch out individual letters instead of outright converting them:
```python
# This took me way too long to figure out

  testlist = ["X","O","X","O"]
  newlist = []
  
  for letter in testlist:
    if "X" in letter:
      newlist.append("1")
    elif "O" in letter:
      newlist.append("0")
  
  print("newlist",newlist)
```

I did all of this around 11/21-11/23, took a break for Thanksgiving, and then returned to clean up the code, make the code "compare" user input to the "master key," and add an inventory for the overall game. Those changes are noted in my next update :)
