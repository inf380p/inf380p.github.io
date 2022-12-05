---
layout: post
author: atUtexas
title: “Final Project for atUtexas”
---


Final Project

I decided to create a data processing project for my Visual Arts Club. I had collected 100 names, phone numbers, email addresses and volunteer status for the club and needed help sorting through volunteers. I created an options menu that allowed the user to print rows, columns and volunteers. The option to print email and phone numbers was also incorporated. This was a challenging task because I didn't have a coding background. When I finally finished my project, I felt a sense of accomplishment.


Reflection

I was very apprehensive when I decided to take this course because I lacked coding experience. Luckily, Professor Hauser helped make my experience less stressful due to his excellent tone and teaching style. The online course textbook was very helpful, especially when working with chapter exercises, because it's so interactive. Although I was stressed out and overwhelmed in this class, I am still glad I took this course because I have learned so much. I now have a good understanding of Python and feel comfortable with general coding basics. 

When I began to contemplate my final project, I had big hopes to gather my user research survey results and develop a database containing all my questions and participant answers. It became too complicated for me. I decided to go with a simpler project I felt more comfortable completing in the time we were allocated. 

Debugging

What was debugging so hard for me? I really had to think through lines with errors. I had to analyze the situation and find possible solutions. Narrowing things down is key. Sometimes fixing things creates new errors so it's important to think ahead and try to use as many print statements as possible. When I fell into a rut during my final project, I really focused on trying not to fall into a pattern of “random walk programming” which was discussed in Chapter 1. Making random changes until the program provides the correct output can be time-consuming. It’s better to have a hypothesis and actually think things through. Chapter one also discusses the four R’s to keep in mind while debugging: reading, running, ruminating and retreating. There were two other R's that I saw on a debugging blog post which included: Rubber duck and Rest. This includes making sure you ask someone else if you get stuck. Another person’s perspective could add a lot of value. Resting and taking a break can freshen your mind. All of these Rs really helped me during my final project. Initially, with my original idea, I was clearly overwhelmed. I decided to Retreat and take a step back with the code. I made the decision to go a different direction which worked out well in the end.

When researching debugging, I came across several debugging software solutions. This appears to be such a great idea because it saves time and pinpoints where the errors are located. I became intrigued by all the solutions out there in the market like LambaTest and Airbrake. Because companies focus on agile and lean methodologies, it’s crucial to be able to find solutions quickly during scrum testing. Programmers have only weeks, not months to turn in their work. Maintaining schedules and deadlines is critical for programmers and is the ultimate goal for a product manager. 

Additionally, understanding the type of error makes a difference. Logic errors seem to be the hardest to pinpoint. Because I am not strong in math, semantic errors frequently occurred for me. It's important not to stop coding in the middle of a section. Sometimes I found myself distracted and stopped in the middle of a thought to read an email, but this resulted in losing focus. Also, making sure I don't forget colons and closing my parenthesis is so important. A habit I was not able to fulfill is writing comments throughout my code. To me it seemed very distracting and I felt overwhelmed by an overload of data. It just seemed so much easier for it to look as simple as possible for me to understand where I was actually at in the coding process. I did use minimal comments during my stopping points to remind myself where I had left off in the process. I learned about text expanders and how it makes life so much easier for coders, especially for those working in agile environments. Being able to type less, coupled with making fewer mistakes, is a plus. 

Also, I typed everything which was probably time-consuming but it was good for me to practice. I tried not to copy and paste. However, I understand and see the value of getting into good coding habits which will be crucial in helping to save time and write code with fewer errors.
Chapter 3 in our textbook indicated that to be a successful programmer, one must learn how to debug well. It all starts by starting small and working your way up to more complicated programs. This tidbit of information stood out to me when deciding to change my initial final project idea. I didn't want to feel trapped and overwhelmed with a non realistic plan that I would probably need several months to achieve. I'm glad I changed my project to a more realistic scope based on my limited coding skillset.

Frustrating

I did find my lack of coding knowledge very frustrating. I was hoping to pick it up much faster than how things currently ended up for me. Another thing I found frustrating was understanding the indentions. I found myself making indentation errors while coding my final project. I know that indentions make coding easier to read and debug. I did feel very grateful for the python documentation which I found to be very helpful after searching youtube video after youtube video for answers. 

Conditional Statement with loops seems like an awesome concept to me but I had difficulty trying to code it properly. I understand the concept but making sure it was orderly and indented correctly was a bit challenging at first for me. I also learned that having too many if else statements in my sequence can create issues. I learned about the importance of narrowing things down.

Even though I may be feeling frustrated now, I read that learning python first is best because it's not as complicated. It can strategically help set me up for success when learning the next language. I’ve had friends tell me they learned Java rather quickly after learning Python first.

Something I found to be frustrating about Python is that it's not meant to be run on a mobile device and is considered a weak language for mobile devices. Most of the projects I see myself working on in the future are mobile apps. Being able to collaborate with programmers is essential to me. I know that I must continue learning other languages to fully collaborate comfortably with data engineers.



Final Project Wins and Issues

It was easy for me to get started on my final project because data processing was fresh on my mind. We had gone through a live coding exercise in class when I had an ah-ha moment. I rewatched the class lecture again at home and it helped so much with retaining information. I used an interface Professor Hauser used, which made my life so much easier. In my initial project, I was trying to make my own interface which was really difficult for me.

It took me some time to get my commands working. I wish I was as quick as other people in my class. My option menu is pretty basic but it took me a while to actually get it fully functional. It was a bit stressful at times. Especially when I was not able to get my columns to print. Also frustrating was the fact that I was not able to delete the last comma in my row. Luckily, I signed up for tutoring at the Sanger Center and I got help with resolving my option 3 issue. I am so grateful for having tutoring resources at UT. I was beginning to panic because it had been over a week and I had spent hours and hours troubleshooting on my own. It was clear that things were not working out for me. I was feeling defeated because I had not been able to resolve it on my own. The tutor was nice and patient. We isolated the points of error and he threw out some hints. He watched me code and struggle a bit until, finally, I was able to make things work. Hurray!


Option 3 (columns to print) was where I spent the most time trying to fix:

```
def get_columns_to_print():
  columns = []

  for header in headers:
    selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
    if selected:
      columns.append(header)
    
  return columns

columns_to_print = headers
```
Some of my print statements were working well early on and that was very exciting for me. In the past, I had never seen myself taking a programming course. My background is high tech sales and I have often collaborated with various technical customers. Now that I am making a career change, I'm so glad I took this class which is helping set up my programming foundational skills which will help me achieve my upcoming programming goals ( SQL, HTML, CSS, and Java).

Here is my code to view my final project:
https://trinket.io/python3/3b589afe9e


<iframe src="https://trinket.io/embed/python3/3b589afe9e" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>





Thank you for reading!

