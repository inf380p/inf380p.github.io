---
layout: post
author: Rowan-Loft
title: "Rowan-Loft's reflection on the class so far"
---

So far, our programming class has been an uphill learning experience, but nonetheless a lot of fun. I think one of the foremost interesting personal things that we haven’t discussed a lot so far is just how much of an open-source endeavor all of Python has been. We did, in part, talk about organizations and academics who have largely contributed to Python’s inception and development, but I’m looking forward to our future projects that involve working with strangers online or in-person to contribute to a range of different projects. I’ve enjoyed looking through repositories on Github and seeing how many people have created forks of projects to add their own touches to projects or to attempt to resolve issues with projects. 

Our class has also been a good example as to how much of a collaborative effort Python is. Adding more “turtles” to accomplish different pieces of code, identifying colors in python using RGB values and hex code instead of conventional color-names, and working through ideas of how 

`“dog” > “Dog”` 

And  

`“dog” < “elephant”` 

have all been discussed by many different people trying to understand and put together the same logic puzzle. String comparison and letter values set off the lightbulb moment for me as to just how in-depth Python has constructed to be, which has caused me a bit of confusion in terms of universal accessibility. I’m still wondering how a language like Python can be crosswalked to other languages with the assumption that different languages apply different rules and values to similar inputs, like when we tried comparing emojis. So far, Googling and looking at lessons by other programmers has begun to help lead me to some answers, such as Unicode with letter values. 

The same has so far applied for problem solving in code for me. When I was working on a trinket that involved defining functions, I kept returning an error that informed me that a line of code was “taking exactly 5 arguments (1 given),” but by looking up the issue on stackoverflow.com and looking over runestone, I was able to ascertain that I had to define more values in the string of code in order to get it to execute correctly. Here's the code in question, which generates stars in a random space mutiple times.

<iframe src="https://trinket.io/embed/python/3c5345e913" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

Here's the `stars_in_space` function:

```
def stars_in_space():
  draw_star(random.choice(s), random.choice(c), (random.choice(t)), random.randint(-200, 200), random.randint(-200, 200))
  ```
 Originally, I thought I could just use the random.choice(s) feature of the function to allow the code to execute, but the remaining values (random.choice s & t, and the randints) also had to be included before the definition was considered correct. 
 
 ![Turtle Image](https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg)
