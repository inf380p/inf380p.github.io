---
layout: post
authour: emmtm
title: "Emmalee's User Interface Draft!"
---

my trinket embed:
<iframe src="https://trinket.io/embed/python/bd6b4e9d02" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

My project is coming along really nicely, I haven't run into any roadblocks yet and was able to successfully create a working interface that 
1. Asks users questions that will be saved to a list & later pulled out so their name, relationship status, astrological sign, etc can be infused into the reading template for a more personalized feel
2. Sets up the reading template function to output readings based on cards pulled
3. Began thinking about how I will organize each card, the facing of the card, the meaning & the context for each type of reading (romantic, career, personal).

I think the actual programming goals were slightly less ambitious than I hoped, getting it to work the way I wanted will not be too hard. 
The ambitious part is wanting to make the program respond to both user input and cards pulled so that the readings will not come out too generic, and will
offer actual output based on the answers.

If I am unable to achieve this the way I want, I am confident I will at least be able to make a reading output template that feels personalized enough along
with the matching card graphics. 

I was able to keep to my plan easily and for the next class I will be working on inputing all of the card defenitions into my dataset (which right now I am planning to use nested dictionaries for),
working on the copy for the output template & working on the .random functions that will be picking the cards out of the dataset. 

Here is the code I have so far for the questions:

```
answer_list = []

while True:
  yes_options = ["yes", "y", "Y", "Yes"]
  no_options = ["no", "n", "N", "No"]
  start_reading = input("Would you like a Tarot Reading? Y/N")
  if start_reading in yes_options:
    print("Great! First, I will ask you a few questions.")
    break
  elif start_reading in no_options:
    quit()
    break
  else: 
    print("Please type a yes or no answer.")
    continue 
  
ask_name = input("What is your name?")
answer_list.append(ask_name)
  
while True:
  signs = ["Aquarius", "Pices", "Cancer", "Taurus", "Sagittarius", "Virgo", "Leo", "Libra", "Aries", "Gemini", "Capricorn", "Scorpio"]
  question1 = input("What is your astrological sign?")
  if question1 in signs:
    print("Okay, so your sign is " + str(question1) + "." )
    answer_list.append(question1)
    break
  else:
    print("That is not one of the 12 astrological signs. Please try again! Remember to capitalize.")
    
while True:
  rel_inputs = ["1", "2", "3", "4"]
  question2 = input("What is your relationship status? \n1. Single \n2. In a Relationship \n3. Married \n4. It's complicated") 
  if question2 in rel_inputs:
    if question2 == "1":
      print("Got it, so you are single.")
      answer_list.append("Single")
    elif question2 == "2":
      print("Got it, so you are in a relationship.")
      answer_list.append("In a relationship")
    elif question2 == "3":
      print("Got it, so you are married.")
      answer_list.append("Married")
    elif question2 == "4":
      print("Got it, so it's complicated.")
      answer_list.append("It's complicated")
    break
  else:
    print("That is not an option, please try again!")
    
while True:
  car_inputs = ["1","2","3","4"]
  question3 = input("In terms of your career or academic persuits, are you:  \n1.Happy with your career \n2.Unhappy with your career \n3.Would like to persue new oppurtunities in your career \n4.Trying to figure out your career goals")
  if question3 in car_inputs:
    if question3 == "1":
      print("I see, so you are happy with your career.")
      answer_list.append("happy with your career")
    if question3 == "2":
      print("I see, so you are unhappy with your career.")
      answer_list.append("unhappy with your career")
    if question3 == "3":
      print("I see, so you would like to persue new oppurtunities in your career.")
      answer_list.append("would like to persue new oppurtunities in your career")
    if question3 == "4":
      print("I see, so you are trying to figure out your career goals.")
      answer_list.append("trying to figure out your career goals")
    break
  else:
    print("That's not an option, try again!")
    
while True:
  self_inputs = ["1","2","3","4"]
  question4 = input("How have you been feeling in your personal life lately? \n1.Happy or Excited \n2.Restless or Bored \n3.Anxious or Sad \n4. At Peace or Content")
  if question4 in self_inputs:
    if question4 == "1":
      print("I will take note that you have been feeling happy or excited lately.")
      answer_list.append("feeling happy and excited")
    if question4 == "2":
      print("I will take note that you have been feeling restless or bored lately.")
      answer_list.append("feeling restless and bored")
    if question4 == "3":
      print("I will take note that you have been feeling anxious or sad lately.")
      answer_list.append("feeling anxious and sad")
    if question4 == "4":
      print("I will take note that you have been feeling at peace or content lately.")
      answer_list.append("feeling at peace and content")
    break
  else:
    print("That is not an option, try again!")
    
  

while True:
  tarot_options = ["1", "2", "3"]
  question5 = input("What type of Tarot Reading would you like? \n1. Romantic \n2. Career \n3. Self")
  if question5 in tarot_options:
    if question5 == "1":
      print("Okay, I will give you a Tarot reading about your romantic past, present, and future.")
      readings.romantic_reading()
      break
    if question5 == "2":
      print("Okay, I will give you a Tarot reading about your career past, present, and future.")
      readings.career_reading()
      break
    if question5 == "3":
      print("Okay, I will give you a Tarot reading about your personal past, present, and future.")
      readings.self_reading()
      break
  else: 
    print("That is not an option, try again!")
  
```

And here is the draft of the reading output template:

```
def romantic_reading():
  
  print(__main__.answer_list[0] + ", your past was represented by " + ("[card picked & definetion will go here]" + ", which is facing " + ("[card direction will go here]") + "." " This tells me that your past relationships brought " + (["card reading for reading type context here"]) + " into your life.")

```

