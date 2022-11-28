---
layout: post
author: hannahmoutran
title: "Hannah Moutran's First Focused Reflection!"
---

#Meal Planning Trinket   

Coding is hard.  I’m using everything at my disposal-the book, the lectures, Google (i.e. videos and posts), and asking for help. It just still feels like there’s so much to cover that it’s impossible to really make any significant headway.  My compromise is that I don’t have to know everything, some things I am just taking people’s word for.  

For example, for this week I made a Trinket that creates a list of recipes for people.  It contains a list of recipes and the webpage where they can be found, a function that picks a random item from that list and prints it, an input mechanism where the user states how many recipes they have time to make in a week, an if/else statement for when people enter '0', and a for loop that returns the number that the user has input.  I had so many iterations of how to pull the random item.  It got super complicated, I went through the chapter on dictionaries in the book, and I still hadn’t found something that worked.  In the end, I googled the right thing, and I found a really simple way to do it.  Which is this, on line 15 of my ‘Meal Planning’ Trinket: 

```
def print_recipes ():
    random_index = random.randint(0, len(recipes)-1)
    print (recipes[random_index])
```
(The name of the list is ‘recipes’)
To be honest, I don’t understand exactly why ‘len(recipes)-1’ is in there.  Why does this work?  But it does, and I was very happy about that. 

Later, I found another way to make this work, on the Trinket site itself.  
There’s a page called ‘Getting Started with Python,’ and on there I found ‘Randomness from a list.’  I adjusted it to my ‘Meal Planning’ Trinket thus: 
```
def print_recipes ():
    random_choices = random.choice(recipes)
    print (random_choices)
```
The nice thing about it is that it didn’t affect anything else in my code.  I mean, I didn’t have to adjust anything to make this work instead of the other def print_recipes.  I did decide to change it, as you’ll see in the embedded Trinket, because it makes more sense to me.   

The other big game-changer was putting in the for loop.  That really cleaned up the code, but it was a bit hard to figure it out.  
Here is that code block: 

```
else:
  for x in range(int(cooking_time)):
    print("\n-----------\n\nRecipe #"+str(x+1))
    print_recipes () 
```

So, the range had to be cooking_time, because that's the user input, but that had to be converted to an integer to be used in the for loop.  Then, where I wanted it to say Recipe #, x+1 had to be converted to a string because it was grouped with a string.  And, it had to be x+1 because x in the for loop always starts at 0.  

One big frustration with this ‘meal planning’ trinket is that I could not figure out how to create a link.  I searched for a long time, and in the end, I just decided to display the URL, and that I would try to ask about it in class.  The other problem is how to stop getting repeat values from the list.  I’ve tried several methods for doing this, and it always seems to break something. Random.choices is available in Python 3 I think, and would be the easy solution for this, but it's not in Python 2, so I'm going to work on figuring out how to do this for next time.  Actually, that kept coming up - I think inserting links is much easier in Python 3, as well.  

#Things I still want to work on for this Trinket: 
1. Inserting images 
2. Inserting links 
3. Repeat values   

#Here is the Meal Planning Trinket: 
<iframe src="https://trinket.io/embed/python/264f891808" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe> 
