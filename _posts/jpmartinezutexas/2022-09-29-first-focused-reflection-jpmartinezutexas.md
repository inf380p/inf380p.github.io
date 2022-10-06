---
layout: post
author: jpmartinezutexas
title: "JP's first focused reflection"
---

# Introduction
Hello, this is my first focused reflection, where I will be focusing on code and how that specific code has helped me learn throughout the class. 

## Let's get started

The  example I will use is from this trinket. 

<iframe src="https://trinket.io/embed/python/13465b094e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

```python
math_time = input("Math time, what is 2+2")
print(math_time)

print("4 is the answer")
print(input == 4)
```
I wanted to make something that would check if your answer to the math question was correct, but this would just input 4 on the run screen. I wasn't really sure what to do for this, so I consulted w3schools. 
I have used w3schools before when learning web dev so I knew it to be a reliable and helpful source. 
https://www.w3schools.com/python/python_conditions.asp
Using the conditions I learned here and through the book, I created a series of if statements that gave answers based on the input of the user. You can see this below.

```python
math_time = input("Math time, what is 2+2")
print(math_time)

if math_time > "4":
  print ("You're over. the answer is 4")
  
if math_time < "4":
  print ("You're under. the answer is 4")
  
if math_time == "4":
  print ("You're correct. the answer is 4")
```

I give the user multiple different answers based on if their answer is over or under. I want to make a text adventure game in the future, or possibly for the final, so I could instead of having it be math questions, I have it be for picking a class for your character, like so.

```python
class_selection = input("Choose a class for your hero, 1, 2, or 3. 1 is knight, 2 is mage, 3 is archer.")
print(class_selection)

if class_selection == "1":
  print ("You have chosen the knight.")
  
if class_selection == "2":
  print ("You have chosen the mage.")
  
if class_selection == "3":
  print ("You have chosen the archer.")
  
else:
  print("hit 1, 2 or 3")
class_selection = input("Choose a class for your hero, 1, 2, or 3. 1 is knight, 2 is mage, 3 is archer.")
```

Here I used an else statement if 1/2/3 were not typed. That way, if somebody answers it wrong, they are able to try again.
I will continue learning new things and trying to apply them to making my text adventure. 
Next step will be to have the classes assign stats to the user. 
