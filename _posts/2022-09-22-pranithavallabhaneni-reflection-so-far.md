---
layout: post
author: pranithavallabhaneni
title: "Pranitha's Reflection on the Class So Far"
---

__1. What’s a lightbulb that has gone on for you? Give an example.__
- As a beginner  my  first inclass exercise helped me get comfortable with experimenting in python. My first in-class exercise is the basics of turtle. This one looked really interesting to me initially, as we can give turtle directions to move and can create different shapes and fill colors. This made me realise that with programming the possibilities were endless.
I understood that this Python is a command driven language which made me feel in control of the problem and empowered me to create solutions to the problems by applying logic using programming.
As an example I would like to show a piece of code that I have written which is plain, straight forward and perfectly describes the above.
    ```
    TotalMinutes = 270
    numMinutes = totalMinutes % 60
    numHours = (totalMinutes - numMinutes) / 60
    print(numHours)
    print(numMinutes)
    print (str(totalMinutes) + " is " + str(numHours) + " hours and " + str(numMinutes) + " minutes.")
    ```

__2. Describe some confusion you’ve experienced. Did it help you learn?__
- In the beginning I found it a little confusing to apply the mathematical functions while writing code,  especially because my background wasn't engineering. However I was able to quickly understand how to troubleshoot the issues once I went through the lecture notes and textbook lessons.
In order to clarify things I have played around with the Turtle code and functions to better understand how each function works. Eventually I noticed that a lot of coding is based on logical reasoning and applying the logic accurately via programming to solve a problem.
The following is one of the trinkets where I used different functions to better understand the functionality.

  <iframe src="https://trinket.io/embed/python/c1317ae09e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


__3. What’s still fuzzy for you? What will you do to make sure you can resolve your fuzziness?__
- In the beginning I was a bit fuzzy on the commands like : using if and elif clauses with conditions, dealing with multiple brackets and with indentation since I'm a beginner. It took me a few trials to experiment with ‘if‘, ‘elif’,  and ‘else’ and now I am used to it and am  pretty confident now while using them in code. When I face an issue understanding a concept I would review the lecture and go through the Runestone academy textbook lessons to clarify my fuzziness.
 
__4. What problem solving strategies have been working for you? Give an example.__
- When I try to solve a problem, I look at the logic that needs to be applied and then put the logic in code based on my understanding from the lecture and lessons. If I face an error, I try understanding the error and the reason behind it. I trying playing around the code with different approach to solve it. If I am still unable to solve it, I refer the the previous code samples on the specific topic and textbook lessons to compare the differences. 
For example, I was trying to take a user input for inches and covert the inches to feet. I didn't realize that the input value would be a string and I divided the input value with 12 which gave me an error. I tried understanding it and then referred the lesson related to input() and realized that the input value will be a string and I need to convert it to an integer. 
    ```
    inches = input("Enter the value for inches")
    feet = int(inches) / (12)
    print(feet)
    ```
