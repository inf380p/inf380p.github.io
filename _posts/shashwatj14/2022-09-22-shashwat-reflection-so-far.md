---
layout: post
author: shashwatj14
title: "Shashwat's reflection on the class so far."
---

# My reflection

If I had to sum up this class in one word, it would be engaging. This course has been fantastic from the start. I had previously taken an introductory Python course, but it was not as interesting as this one is turning out to be. I am enjoying Prof. Hauser's approach to teaching Python and the materials he provided on the course website. The material is extremely useful for learning the practical aspects of programming. During my undergrad, I was assigned theoretical assignments that, in my opinion, were not very useful. It took some time for me to understand functions and how they can be used as reusable code to make a program more efficient. I used to be perplexed by parameters in a function, but with consistent practice, I was able to master it. To be fair, I really liked the structure of this class and the way Python is taught in it. So far, my learning experience has been excellent, and I hope to become increasingly proficient as the course progresses.

1. Program to check if a string is palindrome or not:

This is a problem that I tried to solve after having learned about functions and loops. Here, I am using a while loop to iterate through the string with the help of two iterators. The iteration will take place as long as the string has same characters forward and backward.

```
  def isPalindrome(x):
      
      string = str(x)
      i = 0
      j = len(string) - 1

      while i < j:

          if string[i] == string[j]:
              i += 1
              j -= 1

          else:
              return False

      return True 
```

2. Program to find out the hypotenuse of a right angled triangle 

In this code, I am finding the hypotenuse of a right angled triangle, given its perpendicular and base. I am using pythagoras theorem to do so! 

```
  def findThirdSide(side1, side2):
    
    import math
    hypo = math.sqrt(side1**2 + side**2)
    return hypo
  
```

3. Program to change tutle's color and background 

Here's something that I tried with turtle where I am basically changing the colour and background. 

```
import turtle

myscreen = turtle.Screen()

color = input('Color?')
bg_color = input('bg_color?')

tina = turtle.Turtle()
tina.color(color)
myscreen.bgcolor(bg_color)
tina.circle(10)
```
