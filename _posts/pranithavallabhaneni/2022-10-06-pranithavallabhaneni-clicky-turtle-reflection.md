---
layout: post
author: pranithavallabhaneni
title: "Pranitha's clicky turtle reflection "
---
For this clicky turtle hack my thoughts was to create a different trapeziums by click and to change back ground colors by using arrow keys. 

**Difficulties:**
First difficulty I faced was during asssigning colors to the arrow keys. I initially don't know where to start and later I used *myscreen.onkey* function and tried multiple times to get it.
```
myscreen.onkey(pink_trapezium, 'left')
myscreen.onkey(blue_trapezium, 'right')
myscreen.onkey(violet_trapezium, 'up')
myscreen.onkey(red_trapezium, 'down')
```
Second difficulty was during creating multiple trapeziums by clicking and here the mistake I made was that I gave the clicky function to (x,y) co-ordinates but I forgot to give to trapezium the clicky function and later on I corrected my mistake and did it in the correct way.you can see the code below.
```
def clicky(x, y):
 trapezium(x,y)
 ```
 Finally after many attempts I managed to get the code that I required without any errors. I listed my clicky turtle program down below in the link you can have a look in to it.
 **Looking forward to code more...**
 <iframe src="https://trinket.io/embed/python/bd547e75df" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
