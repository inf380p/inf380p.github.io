---
layout: post
author: hannahmoutran
title: "Hannah's Extra Credit Update to Recipes Program"
---

I decided to go back and revise this code because it felt unfinished.  I was pretty happy with it at the time, but I couldn't figure out how to give the user random choices from a list without having them repeat.  Before I get into what I did, I will say that I accidentally changed the original Trinket-my bad!  I'll explain exactly what I changed, which wasn't much.  It did make it a lot better, though, so that's good.  

The first thing is that I put in a ```while``` loop.  It's just ```while True:```.  I want it to basically just repeat in case the user puts in something over the number of recipes in the list, which is ten.  

The second thing I changed is that I made it so that recipes wouldn't repeat.  I found a blog post that talked about different methods for removing items from a list (https://note.nkmk.me/en/python-list-clear-pop-remove-del/).  The plain old ```list.remove()``` made the most sense to me, so that's why I chose it.  

The third thing I changed is that I put in this code, so that if the user enters a number greater than 10, it will give them an error message that explains the problem: 
```python
elif cooking_time >"10": 
    print ("\nMaybe that number was too high.  There are only ten recipes.  No worries, try again!")
```
The last change was that I made the random choice into a variable, so that I could print it and then remove it from the list.  The for loop with the range was already in the program.  

Here's the revised version of that section of code: 
```python
else:
    for x in range(int(cooking_time)):
      print("\n-----------\n\nRecipe #"+str(x+1))
      r=random.choice(recipes)
      print(r)
      recipes.remove(r)   
```
One thing that I'm really understanding these days is that the user needs to understand what is happening.  If something doesn't work, you don't want some random error to show up, you want something that makes sense and that explains the problem.  That said, the remaining issue that I have with this program is that the list is permanently altered when something is removed.  On the one hand, that's fine because once the ten recipes have printed, that's all, folks.  On the other hand, now that I have a never ending while loop, it could be a little confusing.  I'm happy with it for now, but maybe I'll look for a solution for that another day.  Always something more!

##Either 15 or 50 minutes later, it's honestly hard to tell...

Okay, I had to find a solution for this, because it wasn't working for the error message to have the number of recipes as a string.  You can't do greater than with a string.  The program wasn't working.  So, I had to make that into an integer (with ```int```).  Then I had the idea to change the while loop to a len(recipes) like so: ```while len(recipes)>0:```.  That way, the loop would stop.  Then, it made sense to make the error message only pop up if the number that the user asked for was greater than the number of recipes left in the list.  Then, it got a little bonkers, but if they only have 3 more recipes that they can access, I want them to know that.  So, I had to change the input prompt so that it uses the length of the list as the second number.  And, I had to translate that to a string (```str```) to concatenate with the rest of the input prompt.  

The new while loop and user input: 
```python
while len(recipes)>0: 
  #input from user 
  cooking_time = int(input("\nLet's meal plan.  If each recipe would take you 1 hour to complete (not including eating and doing dishes), how many recipes do you have time for this week? Enter a number 0-"+str(len(recipes))))
```

And the new elif statement that triggers a printed "this number is too high" message for the user: 
```python
elif cooking_time>len(recipes):
```

In the end, the problem of the remove method permanently altering the list remains.  I think it works well, though, for this program, now that the parameters are updated according to the number of items left in the list.  

## Here's the full revised Trinket:
<iframe src="https://trinket.io/embed/python/264f891808" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
