---
layout: post
author: haley-triem
title: "Haley's Text-Based Adventure"
---

# ✨👾 Haley’s Text-Based Adventure 👾✨

For the final project,  I couldn’t decide if I wanted to go the data route or the game route. The creativity associated with a game excited me, but a data analyzing project felt more applicable to my career. Instead of explicitly choosing, however, I found myself leaning into both and developing a text-based adventure. And boy did this project humble me! I am proud of the final result, but this project, more than any others, required me to revisit goals and think on my toes. Here’s how I did it.

<iframe src="https://trinket.io/embed/python3/d6b99f4d35" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### 📖 Research 📖

To research for this project, I spent a lot of time looking into text-based adventures, such as the famous “Zork.” I started by reading through source code posted on GitHub and trying to understand it. This was my first road bump: “Zork” was created by MIT students at the forefront of natural-language processing, and contains thousands of lines of complex code. Developing an understanding of NLP and implementing it was unlikely to happen in a few weeks. This was my first wake-up call to scale down my project into something more digestible that I can use as a stepping stone for more complex text-based projects in the future.

I decided to limit myself in two ways:

* I would ditch NLP and instead use menu options. The reasons for this decision were twofold. First of all, I knew that it wasn’t wise to tackle NLP for a final project given that I have no background in it. Secondly, I struggled with the menu options during our CSV file unit, and thought this would be a perfect way to round out my knowledge on them.
* I would reevaluate the scope of my project. Zork contains thousands of lines of code, a large map, and an entire dungeon system. I decided to keep my adventure within one room, so that I could achieve a fully playable game.

Practicing setting reasonable goals early on was a big metric of personal growth, because I have a history of biting off more than I can chew. I’m proud of myself for thinking through my options and choosing a route that challenged me, but was not impossible.

### ✏️ Concept ✏️

Once I gave myself a reality check on the scope of my project, I began to plan the concept and layout. The game would take place in a single room where users could interact with objects and find a way to escape. I wanted a mixture of random luck and puzzles, so I designed the game to have three digits the user had to “find” in order to guess a keycode. The digits came from three different minigames:

* A digit earned from beating a logic-based game (“mastermind”)
* A digit earned from beating a word-based game (“computer”)
* A digit hidden in a lockbox unlocked by a randomly hidden key (“lockbox”)

Because I decided to have three separate tasks, I had to tackle how to build minigames into the main loop. For the most part, I relied on functions, because they were the most reliable way to call a minigame mid main game loop.

### ⏰ Timeline ⏰

Here's a rough timeline of the entire project:

* 17 November 2022  - Develop an interface
* 24 November 2022 - Figure out mastermind and continue to develop main game loop
* 1 December 2022 - Create two more puzzles to solve alongside mastermind
* 8 December 2022 - Clean up code and reflect

# ✨🎯 Minigames 🎯✨

### 🧠 Mastermind 🧠

I coded mastermind first, and boy was it hard: I practically spent my entire Thanksgiving break on it! I wanted the game to generate four digits of binaries, and then have the user guess those digits. The game would then give feedback to the user to influence their next guess. It was easy to generate a random string of 1’s and 0’s, however I wanted to keep in mind that this would eventually fit into the larger game. In the main game loop, mastermind is used to turn on a generator. Because of this, I wanted to use “X’s” and “O’s” to represent on and off switches, respectively. This caused a whole issue of changing “1’s” to “X’s” and “0’s” to “O’s” and vice versa. Here are some iterations that I saved of me trying to solve this issue:

First I had to figure out how to split the string of “1’s” and “0’s” apart; here are my notes to myself:
```python
#Now trying to split it so that I can convert to X and O
#This initial one doesn’t work because there isn’t a space between each number

# function for creating a random binary string
def master_key_string():
  
  # store string in master variable
  master = ""
  
  # loop for range of four
  for i in range(4):
    master_binary = str(random.randint(0,1))
    
    master += master_binary
    
  return(master)

generated_key = master_key_string()
print(generated_key)

print(generated_key.split())
```
I had to print a lot of variables to test if they worked; here, you can see me getting excited about being successful finally!
```python
#Printing the stripped and unstripped key works, but why cant i split it from there?

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

print(generated_key)
# print(stripped_key)

# print(stripped_key(" ",3))
# s = strip(generated_key.split(" ",3))

# print(s)

# IT WORKS!!!!!!
```
Eventually, I began trying to convert integers into strings into other strings.

```python
letter_key = []
for entry in split_key:
  s = ""
  conversion = {"0":"O", "1":"X"}
  for i in entry:
    s+=conversion[i]
  letter_key.append(s)
    
print(letter_key)
```

I was finally able to generate a string of four binary numbers, strip the extra space after the end, split the numbers into a list, and convert them using a dictionary:

```python
# replacing binary values in the list with letter values

letter_key = []
for entry in split_key:
  s = ""
  conversion = {"0":"O", "1":"X"}
  for i in entry:
    s+=conversion[i]
  letter_key.append(s)
    
# Go from a list to a string of letters

letter_str = " ".join(letter_key)
print(letter_str)

# Get rid of those extra spaces
print(letter_str.replace(" ",""))

# victory!!!
```
This took me a long time, and by the time I realized I needed to convert user input into a string to compare with the generated string, I had thought of a new method to test:

```python
# This took me way too long to figure out

  testlist = ["X","O","X","O"]
  newlist = []
  
  for letter in testlist:
    if "X" in letter:
      newlist.append("1")
    elif "O" in letter:
      newlist.append("0")
  
# printing to see if it works  
print("newlist",newlist)

```
This one was way faster and easier, which feels like the perfect metaphor for how programmers often develop skills that “shortcut” larger issues and make their code more efficient. It’s interesting to me that I used different methods to change strings to variables and variables to strings. I honestly could not fully articulate how this discrepancy came about, other than that I did what felt natural. Once I got both sets of conversions to work, however, I was nervous to try to make them agree with each other. Perhaps that is a good future goal.

To give users feedback on their guesses, I used math. I’m actually really proud of this system, because it makes sense to use binaries to compare different strings using operators. I simply can add up the number of “1’s” in the generated code and compare the sum to the number of “1’s” in the guessed code. With an `if` / `elif` statement, I can give the user feedback on how well they guessed.

Here’s the sum of the generated key:
```python

  integers_generated_key = [eval(i) for i in list_master_key]
  win_sum = sum(integers_generated_key)
```
Here’s the sum of switches on in the user guess:
```python
    guess_sum = sum(inputlist)
```
Here’s the comparative key:
```python
    if user_input == master_key_letters:
      lights = 1
      print("\nThe generator comes to life! "+master+" lights turn on.")
      break
    elif user_input == ("EXIT"):
      lights = 0
      print("\n")
      break
    else:
      if win_sum > guess_sum:
        print("\nYou haven't turned on enough switches, try again.\n")
      elif win_sum < guess_sum:
        print("\nYou've turned on too many switches, try again.\n")
      elif guess_sum == win_sum:
        print("\nYou have the right number of switches turned on, but in the wrong spots.\n")
```

### 🚀 Computer 🚀

My idea for the computer was that a) it had to be turned on using mastermind in order to work and b) you had to beat it in hangman in order to earn a clue.

This minigame was a struggle; I was having trouble generating an interface that displayed spaces where users hadn’t guessed yet. Here are some examples of my failures:

This one displayed a never ending loop of blanks because of my overall loop set up:
```python
def displaycomputer(missedletters, city_list, city):
  print("Missed letters:", end=" ")
  for letter in missedletters:
    print(letter, end=" ")
    print()
  blanks = (" "*len(city))
  for i in range(len(city)):
    if city[i] in city_list:
      blanks = blanks[:i] + city[i] + blanks[i+1:]
```

This one had trouble joining blanks together:
```python
# clue = ["__ "*len(city)]
# # correct_city = False

# blanks = "__"*len(city)

# for i in range(len(city)):
#   if city[i] in city_list:
#     clue = clue[:i] + city[i] + clue[(i+1):]

```

I spent a long time trying to figure out how to make the game work cosmetically, and finally realized that I could put effort into a clean and reliable game similar to hangman instead of rushing a sloppy but visually pleasing hangman. I once again had to learn to scale back. I decided to have users guess from a themed list of words, and gave them hints related to the word the longer they guessed. 

I chose a list of cities with the largest populations and the prompt “Shall we play a game,” in reference to 1983’s WarGames. Users can guess cities given a prompt, and are rewarded with another number code when they guess the correct answer.

A function in `interface.py` selects a city from a filed list:
```python
file = open("cities")
  cities = file.readlines()
  cityanswer = ""
  while True:
    cityanswer = random.choice(cities)
    cityanswer = str(cityanswer).strip("\n")
    cityanswer = str(cityanswer).strip("\r")
    break
  cityanswer = cityanswer.lower()
  return cityanswer
```

Then, the main game selects a city, calculates the length of that city, and sets an initial `guess_number` equal to zero.
```python
 guess_number = 0
  city = interface.selectcity()
  city_length = len(city)
  
```
The game tells the user how many characters are in the city, takes user input, and makes it all lowercase for easy comparison.
```python
  print("I'm thinking of a U.S. city with ",city_length," characters, including spaces. Take a guess. Type EXIT to leave.")
  guess = input("")
  guess = guess.lower()

```
Finally, a series of `if` and `elif` statements compare the guess to the answer. Hints are progressively given as the user guesses more.

```python
while True:
    if guess == "exit":
      break
    elif guess == city:
      print("You are correct! Your prize is the number "+computer+" !")
      computerdone = True
      break
    elif guess != city:
      guess_number = guess_number + 1
      print("guess",guess_number)
      if guess == "exit":
        break
      if guess_number <= 3:
        print("Hint 1: your city has",city.count(" "),"spaces in it.")
        guess = input("Try again")
        guess = guess.lower()
      elif 3 < guess_number <= 5:
         …
      elif 5 < guess_number <= 7:
…
      elif 7 < guess_number <= 10:
        …
      elif 10 < guess_number <=20:
        print("Last Hint: your city starts with",city[:3])
        guess = input("try again")
        guess = guess.lower()
      elif guess_number > 20:
        print("Come back and try with a different city, maybe...")
        break

```

Once the user wins, the `computerdone` variable is set to `True`, so the game can check if the computer has been beaten or not.

The computer functions a little differently than mastermind. Mastermind’s binary key is generated at the beginning of the game, so the key will be the same for the whole playthrough. The computer, on the other hand, selects a new city each time the function is called. Because of this, if you quit the minigame or do not guess in time, you have to restart with a new city.

### 🐣 Egg 🐣

I added my very first game easter egg into this project! I know it’s simple, but it was weirdly thrilling. If the user types `“The only winning move is not to play.”` whenever the computer asks `“Shall we play a game”`, the computer responds `“Touche.”`. This is in reference to WarGames!

### 🔑 Key 🔑

The key was the easiest minigame to code. I decided to randomly hide a key in one of the non-minigame locations, and let users stumble upon it while they poke around. The key is assigned a digit 1-7 at the beginning of the game, which corresponds to a different zone in the room. When the user goes to each zone, the game checks if the key is there. If the key is there, it gets added to the user’s inventory, which allows them to access a lockbox under the bed. The lockbox contains a digit.

Here’s where we “hide” the key at the beginning of the game:
```python
key = random.randint(1,7)
```

Here’s a function that grabs the key and is called whenever the user stumbles upon a key:
```python
def keygrab(x):
  if key == x and ("key") not in inventory:
    print("\nYou found a key! You put it in your pocket for safekeeping.\n")
    inventory.append("key")
  elif key == x and ("key") in inventory:
    print("You found a key here a while ago.")
  else:
    print("")
```
Calling the function while searching the mattress on the bed, for example. The user selects to search the mattress, and `keygrab(1)` specifies that if the key was hidden in the `1` integer, the user will grab the key. If there is no key, only the `print()` statement will be executed.
```python
 if bedchoice == "1":
      keygrab(1)
      print("It's simply a mattress on a bedframe, no sheets.\n")

```

Once the user has the key, they can unlock the box with a randomly generated digit on it:
```python
    elif bedchoice == "3":
      if ("key") not in inventory:
        print("\nThere's a box under here, but it's locked.")
      elif ("key") in inventory:
        print("\nYou've unlocked the box! Inside is a piece of paper with the number "+lockbox+" on it.")
```

# ✨🎲 Putting it all together ✨🎲 

### ➰ Loops ➰

The game starts with an initializing loop that leads into the main game loop. From there, different menu options lead to different functions which lead to other menu options; here’s an example of a route one could follow:


```python
# An initial input
x = str(input("You wake up in a dark room to a loud crash and the sound of rain. Was that lightning? Seems like the power is off ...\n"))

# A small loop to break out of before the main game
while True:
  
  userchoice = input("This is the beginning of the game. What would you like to do?\n1: Move\n2: Look Around\n3: Quit\n")

  if userchoice == "1":
    print("\nYou can move a number of places.")
    gameloop()
    break
  elif userchoice == "2":
    print("\nYou look around the room. It is dark and bleak: just a bed, closet, desk, and door.\n")
  elif userchoice == "3":
    quit_choice = str(input("\nAre you sure you want to quit the game?\n1: Yes\n2: No\n"))
    if quit_choice == "1":
      break
    elif quit_choice =="2":
      gameloop()
  else:
    print("\nThat is not a viable selection.\n")

```

The user goes through the initial loop, and selects option choice `”1 : Move”`. Thus, `gameloop()` is initialized, and the main loop kicks off.

`gameloop()` is mostly comprised of different functions that define other menu options. This is `gameloop()` in entirety.
```python
def gameloop():

  while True:
    roomchoice = interface.menu_selection(interface.room)
    
    if roomchoice == "1":
      bedchoice()
      
    elif roomchoice == "2":
      closetchoice()
      
    elif roomchoice == "3":
      deskchoice()
      
    elif roomchoice == "4":
      doorchoice()
      
    elif roomchoice == "5":
      quit_choice = str(input("\nAre you sure you want to quit the game?\n1: Yes\n2: No\n"))
      if quit_choice == "1":
        break
      elif quit_choice =="2":
        print("")
      break
```

Here’s how we ask for `roomchoice` which will inform which loop path to take:
```python
def roomchoice():
  roomchoice = interface.menu_selection(interface.room)
  if roomchoice == "1":
    bedchoice()
  elif roomchoice == "2":
    closetchoice()
  elif roomchoice == "3":
    deskchoice()
  elif roomchoice == "4":
    doorchoice()
  elif roomchoice == "5":
    print(" ")    

```
All menus are pulled from `interface.py`. For example, here is the menu when the `roomchoice()` function is called:
```python
room = {
  "1" : "Walk to bed",
  "2" : "Look in closet",
  "3" : "Examine desk",
  "4" : "Walk to door",
  "5" : "Quit"
}
```
If the user chooses option 1, a different menu will be pulled up:
```python
bed = {
  "1" : "Examine mattress",
  "2" : "Examine quilt",
  "3" : "Look under the bed", 
  "4" : "Look behind the bed", 
  "5" : "Move"
}
```
All of these menus can be navigated between, because there is always a `“Move”` option that brings the player back to the `room` dictionary menu. To win, the user must navigate to the door and input the keycode.

### 💎 Checking 💎

Throughout the game are series of checks to test if the power is on, if the computer has been beaten, and if the key has been found. These checks are immune to the issue of being looped over, because the main loop consists of smaller functions within. In other words, once the lights are on they stay on. It doesn’t matter where the player travels in the room.

Here are examples of checks:

When using the generator, if the lights are already on (`lights == 1`), the secret digit is returned:
```python
 elif closetchoice == "2":
      if lights == 0:
        playmastermind()
      elif lights == 1:
        print("\nThe power is already on! You see "+master+" lights on the generator.")

```
It’s a similar situation with the computer:
```python
elif computer_choice == "1" and computerdone == True:
          print("\nWe've already played! Your number is "+computer+" !")
        elif computer_choice == "2":
          roomchoice()
        elif computer_choice == "The only winning move is not to play.":
          print("\nTouche.")

```
The key is only added to the inventory if it is not already there:
```python
def keygrab(x):
  if key == x and ("key") not in inventory:
    print("\nYou found a key! You put it in your pocket for safekeeping.\n")
    inventory.append("key")
  elif key == x and ("key") in inventory:
    print("You found a key here a while ago.")
  else:
    print("")

```

### 💥 Exit Keycode 💥

In order to escape, users have to input a three-digit code based off of digits they found in mastermind, the computer, and the lockbox. I didn’t want the game to be the same every time, so I made the order in which these digits appear random. The user loses if they type in the wrong code, which discourages people from just guess-and-checking the digits. The order in which the digits are inputted is stored in a journal on the desk. Here’s how I set up the random order at the beginning of the code:

First I picked three digits, one to correspond with each of the hiding places:
```python
# Digit hidden in the lockbox
lockbox = random.randint(0,9)
lockbox = str(lockbox)

# Digit hidden in the mastermind game
master = random.randint(0,9)
master = str(master)

# Digit hidden in the computer
computer = random.randint(0,9)
computer = str(computer)


```
Then, I wrote options for the order in which the digits can be arranged. These options show up in the journal on the desk.
```python
code_key = [lockbox+master+computer, lockbox+computer+master, master+lockbox+computer, master+computer+lockbox, computer+lockbox+master, computer+master+lockbox]

random_code_key = random.choice(code_key)
```
Finally, I made the chosen key into a readable string of words so that the player can figure out what order the keycode is in.
```python
book_list = []
while True:
  for string in random_code_key:
    if lockbox in string:
      book_list.append("lockbox")
    elif master in string:
      book_list.append("master")
    elif computer in string:
      book_list.append("computer")
  break

book_answer = " ".join(book_list)

```

At the end of the game, the user can choose to input three digits that they’ve found, in the order specified in the journal. If they input the correct digits, they win! I currently am using an undefined `crash()` function to crash the game after it ends, because I was struggling to break out of the main loop when other loops were still nested inside of it. That just leaves room for improvement, though!

```python
if escape_question == "1":
        final_guess = input("Type three digits and hit enter.")
        if final_guess == random_code_key:
          print("\nThe door swings open, and you walk out of the room.\n")
          input("")
          crash()
        else:
          print("\n Wrong code. Game over.\n")
          input("")
          crash()
```

# 🌟 Final Thoughts 🌟

### 💫 What did I accomplish? 💫

I’m so proud of the end result. I made a fully playable and fairly complex adventure game with multiple minigames coded. This project genuinely excited me, and I plan to continue playing around with text-based games. There’s a lot to improve upon, and plenty of room to grow as a coder, but I’m shocked by the difference in my coding skills compared to the beginning of the semester.

### 🐛 What can I work on? 🐛

My undergraduate degree was in English. Even though I am proud of this version I have turned in, I have begun to realize that coding is like writing essays. There is no perfect version, and I always find myself brainstorming ways my code can be better. Some main things I’d love to implement in this code include:

* A timer to raise the stakes, or some sort of moves counter that limits the number of guesses the user has
* A way to put the mastermind and computer minigames into their own modules ... originally I had them in individual modules, but the variables were not pulling into `main.py`, so I abandoned that issue in order to tackle more pressing problems
* A better way to end the game ... right now, I force-quit the loop through calling an undefined function. This creates an error at the end of my game, which I hate, but I truly was stumped on how to end a loop called by a function within another loop
* I genuinely want to learn NLP and develop a naturally processed text–based adventure!

# 💖 Here are a few examples of game iterations 💖

### "Final Project 1.0"

<iframe src="https://trinket.io/embed/python3/ee798d9e75" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### "Mastermind 1.0"

<iframe src="https://trinket.io/embed/python3/67c4d229d1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### "Final Project 4.0"

<iframe src="https://trinket.io/embed/python3/1d0975a300" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

### "Final Project 5.0"

<iframe src="https://trinket.io/embed/python3/a272155658" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
