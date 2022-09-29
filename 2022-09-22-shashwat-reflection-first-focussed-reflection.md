---
layout: post
author: shashwatj14
title: "Shashwat's First Focused Reflection!"
---

Coding can be difficult, especially when you get stuck and can't figure out how to get out of it. Conditionals, loops, and debugging have been major takeaways for me so far in this class. After learning about loops and conditionals, I became very curious and wanted to create a few more programs. As a result, I decided to write code that would take in a list of ages, iterate through each age, and return indices of all those ages that were eligible to vote.

I hadn't yet gotten used to for loops and this new data structure 'list'. So, as I was trying to iterate through the list, two very simple and silly things just slipped my mind:

1. Indices in for loops start from zero
2. Foor loops only iterate UNTIL the nth index, that is, (n - 1)th index is the last inclusive index when you're working with for loops in python 

Here's my code:

```

  def vote_eligiblity(listOfAges):
      eligibleAgeIndices = []

      for i in range(len(listOfAges)):
          if listOfAges[i] >= 18:
              eligibleAgeIndices.append(i)

      return eligibleAgeIndices

```

This code works just fine and will return you a list of all vote-eligible age indices. However, here's the code that I was trying before:

```
for i in range(1, len(listOfAges) - 1):
```

I was making two mistakes: I was starting my iteration from zero and running it until the second last element because it slipped my mind that the for loop won't iterate over the last index (which in my case was len(list) - 1).

Thus, I had to rectify the code to make sure it iterates through the whole list:

```
for i in range(len(listOfAges)):
```

Here's the link to my trinket:

<iframe src="https://trinket.io/embed/python/074a111f55" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


      
