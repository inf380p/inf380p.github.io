---
layout: post
author: atUtexas
title: “Nov 3 CSV Reflection for atUtexas”
---

 Reflection
 After reading chapters 7, 8 and 9 in our interactive online textbook these last several weeks, I felt optimistic about the content. However, I encountered a setback with the in-class exercise on Oct 20th and the CSV File to dos on Oct 27th. I thought I was keeping up well at this point in the semester, but after the last class CSV iSchool file exercise, I left the class with a headache. During my first group interaction, my partner got through further and we discussed his issue with no resolution. When we got into group 2, someone else was in the same boat as me. Their confusion made me feel better about my confusion. Unfortunately, I was not able to save my python 3 trinket link. So I started over and again when I arrived home which seemed like good practice.
 Additionally, the CVS Files assignment has some tasks that I found challenging, but once Elliott explained what to do, it made more sense. I hope the Oct 27th zoom video is posted soon. Rewatching our zoom videos have been very helpful for me. 

 Debugging

 I need continuous debugging practice. With some of these errors I was getting, I needed help to resolve them. While in my group, we resolved errors together, so I value the power of group work in this instance.
 I would quickly resolved indent errors but then got errors like this one NameError: Name “ “ is not defined. Another error I was getting was “NameError :function is not defined. But when I looked at my code, it thought it was defined. So I checked to make sure that I was not a) calling a function that did not exist b) calling the function before it was declared c) misspelling the name of the function. So not sure what else I should do. So at this point, I was stuck.


 Trying Again
 I watched the Oct 27 class video and attempted to rework the code again. The second time around was much better for me, however, I was still not able to resolve the quotation deletion . I felt like I could understand the concept better and found myself a few steps further along and closer to solving it. I decided to try and use the remove() method to remove the quotes from the list. I also tried pop () and clear() without any luck. An issue I resolved was understanding that if the loop goes through only once, I must check to ensure the return statement is appropriately indented so that the loop will go all the way through. It’s essential to make sure that the return statement is outside of the for loop in order for it to go all the way through. See the code below for clarification.

 ```
   for cell in cells:
     print (cell, cell.startswith('"'))
     
   return pretty_line 

 ```
 Here is my code for attempting to use the Remove () from the list. 

  https://trinket.io/python3/54381a1da3

 <iframe src="https://trinket.io/embed/python3/54381a1da3" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>



 Study Habits 
 I recently talked to a counselor at the UT Sanger Center regarding study habits for coding because I want to improve my coding skills. He informed me that I needed to write fewer notes during class because it does not help me retain the information. He said to listen and retain as much information as possible while in the moment. The next day, try writing out everything I remember and listen to zoom recordings sooner. He indicated that if I wait too long, for each day that passes, the brain will forget most of the information if it's not retrieved as soon as possible. He also recommended the book "How We Learn" by Benedict Carey, which I was able to find at the PCL . It ties in nicely with the methods he mentions. 

 CSV Files
 While attempting to refactor and creating the row_dicts_list into a function, I simply followed the same pattern as the refactor for selecting columns_to_print a function. However, I am not sure if I called it properly due to the function type error I received back. I think I need to make a Len and fix rows. Here my code for that section:
 ```
 def row_dicts_list():
   list=[]
   
   for list in lists:
     selected = interface.input_is_yes(f"Do you want {list} in simplified print view?", default = 'y')
     if selected:
       lists.append (list)
       
   return list
   
 list_to_print = list
 ````

 Here is the link : https://trinket.io/python3/3c431f8b6c

 <iframe src="https://trinket.io/python3/3c431f8b6c" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


 Thank you for reading.
