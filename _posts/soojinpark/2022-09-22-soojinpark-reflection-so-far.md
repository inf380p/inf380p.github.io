---
layout: post 
author: EnglandHam
title: "soojinpark's reflection on the class so far"
---

# What’s a lightbulb that has gone on for you? Give an example.
I used to find conditional statements very overwhelming. I would read the whole thing and feel lost on what meets the conditions or not and when the code will stop running. However, it wasn’t until I started from just one “if” statement to “if” and “else” all the way to “if,” “elif,” and “else” that I realized that I don’t have to read the entire conditional branches, seeing the bigger picture. For instance, in the example below, I’d look at the value and start one line at a time. I just stop whenever the condition is true/met, if not, I move on. Python, just like me, is a child trying to figure out what meets the requirement and doesn’t meet the condition– one line at a time.

# Describe some confusion you’ve experienced. Did it help you learn?
In the past, I found variables and functions very confusing. I couldn’t differentiate between them and didn’t know why certain names for them worked without writing extra codes to instruct what they should do. Through the readings and related practice, I was able to learn the concept of each type, pre-designated variables and functions, and the difference between “int” and “input” (their similar spellings confused me because I never knew what “int” stood for). 
```
current_time_string = input("what time is it right now?")
waiting_time_string = input("how many hours do you have to wait")

current_time_int = int(current_time_string)
waiting_time_int = int(waiting_time_string)

hours = (current_time_int) + (waiting_time_int)
timeofday = hours % 24

print(timeofday)
```

After practicing some codes and reading the fundamentals of the terms, I know why the variable name is “var_string” and why “input” and “int” have different formatting. I felt confident explaining to anyone what is happening, line by line, and how all the lines work together to “print(timeofday)”. 

# What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness? 
We have discussed how important it is to know how to print and debug. I am getting more familiar with the print function, but the whole concept of debugging and the necessary tools that help you spot an error faster go over my head. How do I spot an error efficiently? What exactly is a syntax error (to someone that is not familiar with coding, all the contents feel like syntax)? What if I use “try” and “except” in the wrong way, how will I ever know?
This hesitation and questions are most likely to remain throughout the whole coding journey I have. However, I know I have to push beyond my comfort zone and learn these debugging skills so that I can utilize them when codes get more complicated and dependent on other lines in the program. Instead of erasing what I did or un-doing changes, I will assess the situation whenever I get an error and use debugging strategies rather than going back to my old habits. 

# What problem-solving strategies have been working for you? Give an example.
Whenever I hit a roadblock and I couldn’t figure out why the error keeps occurring, I used to (and even now) rewrite the codes that were more familiar to me. Even though that would make functional codes, I knew I was wasting a lot of time and learning opportunities that I didn’t know how to seek and achieve. Now I use the “print” function to see if I am on the right track. The “print” function keeps track of where I am, if my codes are doing what I want them to do, and if not, giving me visible signs that things I wanted to happen didn’t occur. 

 <iframe src="https://trinket.io/python/3f6709f629" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
 
For instance, here I have three conditions where the user’s input could determine the outcome of Sooj the turtle. In the past, I wouldn’t put the “print(“Invalid Input Try again :(“) line and would suffer if users didn’t write in an input box what I expected them to write. Now, if there are input errors, I know the conditions weren’t met but the codes still worked because it would print out “Invalid Input Try Again :(.” The visibility of my progress puts me at ease and allows me to try more things outside of my comfort zone. 
