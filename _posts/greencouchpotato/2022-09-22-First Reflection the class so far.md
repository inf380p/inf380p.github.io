
---
layout: post
author: greencouchpotato
title: "Jyotsna's Reflection on the class so far"
---

1. What’s a lightbulb that has gone on for you? Give an example.
- I realised that coding is a logical problem solving tool that takes inputs and gives outputs. It truly is a language.  And like any language, the more complex functions I learn, it’ll help me communicate more effectively in fewer lines. Complexity is inversely proportional to length. Maybe not always, but could be true in a lot of cases. At least this is my take so far.
While attempting the exercises in the textbook, I also noticed that there’s more than one way that I can approach a problem.
A simple example is - both the below codes give the same output, but the lines of code is shorter in one of them.
	
A) 
```
#example:
foot = 12
feet = input("Enter the number of feet.")
feet = int(feet)
print ((feet) * foot)
```

B)
```
#modified example:
foot = 12
feet = input("Enter the number of feet.")
print (int(feet) * foot)
```
_________________________

2. Describe some confusion you’ve experienced. Did it help you learn?
- Initial Thoughts: While writing code for the below 2 textbook exercises, I did experience some confusion as to how to frame my code. Especially when it came to the ‘int’ function that had to be added to convert a string to an integer. So far, I only faced errors with respect to this. 
Other questions helped me find a solution to this problem. I started clearly mentioning the ‘_str’ or ‘_int’ words at the end of each name. This helped me understand the value type at a glance and helped me work quicker.
Examples :

A)
```
ask = input("What time is it?")
current_time_int = int(ask)
waiting_time_int = 50
new_time_int = (current_time_int + waiting_time_int)
day = 24
hours = new_time_int % day
print(hours)
```


B)
```
inches_int = 12
feet_str = input("Enter the number of feet.")
print (int(feet_str) * inches_int)
```


- Current thoughts:

A. I've been struggling with using the import function on math modules. I was able to google some useful informatio on how to frame my code better. But I have not received any output or error with the final code that I've written. 
The below output for my code was confusing to me - 
"<function <native JS>>"

While I understood from the class discussion the reason for this output, I'm unable to find a way to fix it. Below is my embedded code. I'm still working on resolving this issue (personal challenge!!)
  <iframe src="https://trinket.io/embed/python/7cea5b28db" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

B. I've also been looking up the refactoring turtle functions. I understood that there's no one way to refactor a program and any improvement is refactoring it. I learnt a thing here!

_________________________________


3. What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness?
-I’m unclear on how to start a code. I see multiple opening lines in the classes which are confusing for me.
a) elliott@penguin: ~$
b) Turtle (import?)
c)  >>>
Especially in cases where ‘>>>’ is used, the output is very immediate. I’m unclear as to when Python would prompt me to give an instruction, when to import something, and when I can begin a program directly (the way it’s done in the textbook exercises)
I plan to google the above to get more information. I remember a wiki page that was shown in the class where a lot of information was available. I will begin with this.

__________________________________

4. What problem solving strategies have been working for you? Give an example.
-As of now, going through the textbook lessons and working on the exercises/questions has been quite helpful for me. I’ve understood the concepts well with the lessons and I didn’t yet run into any major blocks.
-Trial and error has been my approach with the exercises. Occasionally, when I’m not too clear on how a component works, or if I’m unsure of the meaning of any function, I’ve been googling them.
