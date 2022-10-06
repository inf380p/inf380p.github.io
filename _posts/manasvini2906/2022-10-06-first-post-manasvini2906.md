---
layout: post
author: <yourgithubname>
title: Manasvini's first post!"
---

Hi everyone ! 
I am Manasvini Karthkeyan and I am a second year graduate student at UT. To be very candid, I have self taught a lot of programming since I am pursuing Data Science, but I have always wanted to strengthen my foundation in Python. 
 I am very glad I took this course since the textbook is **EXTREMELY** good. (I am a reading/writing learner and the textbook is really out of this world)
  The class has been great, and it has given me a very healthy perspective on how to view programming and programmers. Code tends to look very overwhelming without knowing the context
  and this class taught me to take context into account and not feel overwhelmed. It is also humbling to see the professor deliberately making mistakes while coding to normalize it.

The **best** part about this course would be my new found appreciation for de bugging. While coding on python before, I used to get errors like NameError and ParseError but I used to get frustrated since I didnt even notice them!
  After learning about debugging, now I find myself identifying way faster, where I might have gone wrong.

  I have also always struggled with functions. To be honest, it is still a little fuzzy for me. I have tried a lot to understand functions and arguements, but when faced with a problem I rarely know how to use a function to make my code more efficient.
  I feel unless the question demands in words "Define a function that.." I still would know how to proactively use a function in a code. I think I need to work a little more on how I visualize the problem.

  One problem stretegy that I have now incorporated in my coding journey, is to check for which kind of error I am facing, always checking for data types and whether there is compatibility throughout the code. I have also noticed that
  when stuck in a rut while coding, taking a walk helps gain your clarity! 


  ```
  I recently used this if else statement to gauge if the number is positive or negative
  
num = float(input("Enter a number: "))
if num >= 0:
    if num == 0:
        print("Zero")
    else:
        print("Positive number")
else:
    print("Negative number, get the row and drop it!")
  
  ```


   ```
  I understood (after all this time!) the significance of dot notation.
  
  
import matplotlib.pyplot as plt
#creating a new figure
fig = plt.figure()
#adding axes to the figure
ax = fig.add_axes([0,0,1,1])
crude_oil = [12, 17, 14, 15, 20, 27, 30, 38, 35, 30,28,15]
plt.fill_between(np.arange(12), crude_oil ,
                 color="skyblue", alpha=0.5)
plt.plot(np.arange(12), crude_oil , color="black",
         alpha=0.6, linewidth=2)
plt.title('Year 2016')
plt.tick_params(labelsize=12)
plt.xticks(np.arange(12), np.arange(1,13))
plt.xlabel('Month', size=12)
plt.ylabel('crude-oil(in metric tonnes)', size=12)
plt.ylim(bottom=0)
plt.show()
  
  ```
