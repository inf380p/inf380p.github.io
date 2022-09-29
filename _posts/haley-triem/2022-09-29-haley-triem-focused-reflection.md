---
layout: post
author: haley-triem
title: "Haley's First Focused Reflection"
---

# Here's what I've learned so far ...
I am someone who is a self-proclaimed perfectionist, so coding has both been incredibly rewarding and frustrating. As graduate students, it is increasingly rare for us to come across something that is utterly new ... most of my current coursework is built on at least some basic scaffolding of prior knowledge. I will be the first to admit, however, that I knew absolutely nothing about coding--or even how computers worked--at the start of the semester. I would not say that I've mastered coding by any means, but the topic at the very least feels more digestible.  

One of the surprising side effects of learning to code was gaining more insight into my personhood by examining my workflow and problem solving strategies. For example, I already knew that I tend to find most success when giving myself a specific goal. In week two I tried to harness this by deciding to draw an elaborate turtle with a party hat that said "380P = Party!" ... I was not ready for that. I found myself sitting in front of my computer at 3 am, admittedly in tears of frustration, stumped over how to fix the sad misshapen hexagon I had created. Coding most certainly did not feel like a party in that moment.  

<iframe src="https://trinket.io/embed/python/61c0bb37d4" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>  

And although some of my notes from that day read ...

>ANGRY TURTLE  
>Gave up on turtle  
>Tried to do geometry for heart  
>Gave up on geometry  
>Got frustrated with how slow the turtle was moving  
>Realized that i literally had control over turtle  

... I still learned some important lessons.

# I learned to set smaller goals and celebrate even the smallest of victories. 

For example, when looking back at my notes, I found that I had wrote “`tina.delay(600)` is a game changer for animation!!!”  

While I had not specifically written `tina.delay(600) = Party!` in my program itself, the energy was there.  

## Some of my other favorite notes that seem to capture my rollercoaster relationship with coding include:
>`turtle.right()` is rotation !!!!!!!!!!!! Not mmovement !!!!!!!!!!!!!!!
>
>Degrees are better than coordinates for drawing things so you don't HAVE TO MOVE LITERALLY EVERYTHING  
>
>MOST OF MY MISTAKES ARE FORGETTING TO SET END FILL; DONT FORGET END FILL

## I've also come across a lot of interesting questions from past Haley:
>How do you animate stuff at the same time?  
>
>What if I wanted to have an oblong shape ... how do I make curved lines?  
>
>HOW DO I PUT LIMITS TO SYNTAX IN THE SAME WAY THAT PYTHON DOES  
>
>How can I be sure that the question has an answer?  
>
>Why do I have to import random ...  

## I realized how crucial it was to be thorough and double check syntax in order to make debugging easier later ... 

When making my 8-ball, I forgot to "end" the fill function, and could not get the circle to even begin the fill to start with:

```
#black circle
turtle.penup()
turtle.color('#0F0A46')
turtle.goto(50,-120)
turtle.pendown()
turtle.fill(True)
turtle.begin_fill()
turtle.circle(150)
# missing turtle.end_fill() here !
```

# Throughout the semester, I've developed some problem solving skills.

While I am admittedly behind on textbook readings ( a big catch-up goal for this weekend ), I have found myself problem solving by searching for functions on GitHub, Reddit, and god knows where else on the internet. If I get stumped, I Google "how to assign random strings," or "how to import multiple Turtles in Python," or even end up reading through library documents on the language itself. I have started figuring out how to synthesize all of the clues I find from these resources into solutions for my own code. This skill feels like what we were talking about at the beginning of the semester: a beginner level coder with an expert level skill. I distinctly remember trying to teach myself Python over the summer and not having the right tools to solve a problem even *with* an exact walkthrough. Now, I can use vague hints and guides to figure things out on my own--it's empowering!

## Those problem solving skills got used a LOT for my 8-ball ...

My 8-ball, which culminated in a small interactive reflection, felt like a solid mini-project: I saw that thing through from start to finish. The idea was to make the familiar predictive 8-ball--except that this one would only have sassy answers. And although at face value it is completely elementary, I’m weirdly proud of it. I felt like it scratched the creative and problem solving and storytelling parts of my brain all at once. I am excited by the skills I got to learn from this mini-project, because it took many iterations for me to implement user inputs, then random strings, then conditionals, and finally, to generate my interactive reflection. I hope to continue searching for these feelings of creativity and curiosity going forward. 

While I am proud of the final product and felt like I had a breakthrough specifically on random strings / conditionals (as mentioned in my interactive reflection below), I also think I had a huge breakthrough by just learning that you could import random strings in the first place. This was the moment I can think back on most clearly when things started clicking. I had been struggling to figure out how to get the 8-ball to produce random answers, when I realized I could just `import random`. This opened up a large number of functions, and gave me the opportunity to play with random functions and conditionals, which I can use as groundwork for more experimentation in the future. The possibilites seem endless when you can build upon imported material ... my coding notes from that day are 32 pages long because I couldn't stop copying over chunks of code that excited me!

## Some examples of me trying to figure out how to produce random answers with conditional inputs:

One of the earlier iterations where I inputted an initeger to see if I had figured out a proper "if" statement:
```

input("What do you wish to ask?")

#want to insert a statement that says something like "if input does not have
# a ? mark, print [that's not a question, loser]"

a = "that isn't a question"
Print(a) if input() is int()

list1 = ['Ur mom.', 'None of your business.', 'Absolutely not.', 'Why would I know that???', 'No.']
x = random.choice(list1)
print(x)

```
A later iteration where I honestly have no idea what I was trying to do, but I think the `#commentary` shows a good example of my headspace:
```

question = input('What do you wish to ask?')

print(type(question))

#maybe this isn't working because we need conditionals to be set to an integer??
#maybe i have to set certain aspects of the input to integers
#and if those integers are true other than the random integers it'll work

if(type(question))!=('<class'str'>'):
  print('This is not question!')

#want to insert a statement that says something like "if input does not have
# a ? mark, print [that's not a question, loser]"

  #would this be a boolean??

a = "That isn't a question."

list1 = ['Ur mom.', 'None of your business.', 'Absolutely not.', 'Why would I know that???', 'No.']
x = random.choice(list1)
print(x)

#how do i make sure that the question has an answer?

```
Jumping forward to the final product where I realized I could set a random list, make a random choice from said list, and then use an if / else statement to have the program either choose from one of the random answers if certain conditions are met or print "That's not a question!" if the conditions are not met:
```

question3 = input(">>> Now try saying a statement, instead of a question.")
print("")
if "who" in question3 or "Who" in question3 or "what" in question3 or "What" in question3 or "where" in question3 or "Where" in question3 or "when" in question3 or "When" in question3 or "why" in question3 or "Why" in question3 or "how" in question3 or "How" in question3 or "which" in question3 or "Which" in question3 or "whose" in question3 or "Whose" in question3 or "does" in question3 or "Does" in question3:
  list1 = ['   Ur mom.', '   None of your business.', '   What do you want already...', '   Why would I know that???', '   No.', '   Why would you ask me?!', '   Who am I ... your babysitter?', '   Figure it out on your own.', '   Why are you pestering me??', '   >:(', '   Do I seem like your mother?', '   IDK man, figure it out on your own time.', '   This is waaaaaaaay below my paygrade...', "   Frick you!"]
  b = random.choice(list1)
  print(b)
else:
  print("That's not a question!")

```

## The "final" product:

<iframe src="https://trinket.io/embed/python/8869c9de4e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## 8-Ball reflection:

<iframe src="https://trinket.io/embed/python/298ba6a0ac" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

It sounds weird, and cheesy, but after two years of burnout and high-stress at the end of a quarantined undergrad, coding feels like a breath of fresh air. It isn’t always easy, and can be infuriating at times, but in the moments where I finally figure out a frustrating bug or finally get the code to do what I want, I feel that lighthearted pride we all get as children when we want to show off our coloring skills or how good we are at jumping off the playground. I don’t want to sound naive and pretend that I am anywhere near holding my own in the professional world from a coding standpoint, but at the very least, I am proud of what we’ve learned so far and am excited to see where this trajectory takes us!
