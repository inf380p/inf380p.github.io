---
layout: post
author: haley-triem
title: "Haley's 8-ball Reflection"
---

# My reflection is interactive!
<iframe src="https://trinket.io/embed/python/298ba6a0ac" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# Here's my original 8-ball ...
<iframe src="https://trinket.io/embed/python/39d9721689" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# Here's the improved version!
<iframe src="https://trinket.io/embed/python/8869c9de4e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

# Transcript-ish of my interactive reflection:
We've learned a lot using `turtle` in class so far . . .

>  like programming shapes `turtle.circle()`,  
>  color changes `turtle.color()`,  
>  and written messages `turtle.write()`.  

We've also learned some functional commands:

>  we can change speed `turtle.speed()`,  
>  reorient ourselves `turtle.right()`,  
>  and draw using angles and lines `turtle.forward()`.
  
A huge breakthrough for me was figuring out how to randomize printed strings. I wanted to play around with making a sassy magic 8-ball, so I fumbled through importing `random` from the Python library, tested a few routes like assigning random integers to strings, and then realized I could generate a random string from a list:  

``` python
input("What do you wish to ask?")
list1 = ["Ur mom.", "None of your business!", "Why would I know that??"]
y=random.choice(list1)
print(y)
```

Because the strings are randomized (and because I included more string options in the final code), you likely won't get the same answer each time. But even if you didn't ask a question, you still got an answer. I wanted to play with conditionals to try to vet out non-questions. To do this, I had to define the `input()` and check it against some conditions.

``` python
question = input("What do you wish to ask?")

if "?" in question:
  list1 = ["Ur mom.", "None of your business!", "Why would I know that??"]
  y=random.choice(list1)
  print(y)
else:
  print("That's not a question!")
```

I realized though that people suck at punctuation, so I tried to add more options that could be in a question for it to count as a question. 

``` python
question = input("What do you wish to ask?")

if "who" in question or "Who" in question or "what" in question or "What" in question:
  list1 = ["Ur mom.", "None of your business!", "Why would I know that??"]
  y=random.choice(list1)
  print(y)
else:
  print("That's not a question!")
```

It's not perfect by any means. If someone, for example, inputs "I don't know what to ask" a random string will be generated because "what" was still inputted, even though "I don't know what to ask" isn't a question.

The question-vetting isn't foolproof and I'd like to learn more skills to counteract that. Additionally, I'm excited to go further into boolean operators, functions, and debugging. I want to learn how to repeat sections of code so that the user can ask the 8-ball as many questions as they'd like.

Finally, my code is outright messy! I can't wait to practice streamlining, optimizing, and oranizing code.

I'm excited to practice more! Cheers to learning! :)
