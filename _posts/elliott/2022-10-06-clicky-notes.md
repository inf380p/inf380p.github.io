---
layout: post
author: elliott
category: notes
title: "Clickhack!"
mode: In Person
published: true
inprogress: false
---

# Announcements

* If your program "doesn't work", begin describing exactly how. As you write this down, you'll get new ideas and you might solve the problem
* If your program often "doesn't work", perhaps you need to **Run** your code more often. 
* If your posts aren't showing, don't worry. We'll clean them up soon.

# Vocab + Q&A
* What should I make sure to cover?



# Part I: Merge a partner's Clicky turtlehack

You know the drill.  Pair up, merge up, confirm the file is visible on the site. If not, work together to determine why. Take a break once all partners' work is displaying on the site. Reconvene at the agreed-upon time.

**If you have changes requested on your other pull requests, address them during a break**

## Clicky Turtle Discussion

First, let's review the [starter code]({{ site.baseurl }}/exercise/clicky-turtles.html).

Then, in _new_ pairs, play with and discuss each other's work!


**If you have changes requested on your other pull requests, address them during a break**



# Part II: Peer Reviewing

Time to review a *different* partner's program.

Here are the github names that

~~~
# Pairs
Stuks : [Absent]
Alm7468 : Mchakerautexas
Englandham : Atutexas
Manasvini2906 : Rabouti
Zengjilie : Hyo9292
Prakash-sa : Juliira
Emmtm : Inf380pcoder
Scdai9 : Nathanstern93
Eros11on : Simon871028
Rowan-loft : Jpmartinezutexas
Pranitha vallabhaneni : Haley-triem
Johncbmeyer : Shashwatj14
Rosalindbradshaw : Greencouchpotato
Iliekatz : Martsale
Hannahmoutran : Unixenthusiast
Jamesathrun => Amptex101
Amptex101 => nemothefish260
nemothefish260 => Jamesathrun
~~~


# Part III: Group up & Make a Name For Yourself

(Moved to next class)


# Looking Ahead

## Optional Feedback Form

On the materials page or at [this link](https://docs.google.com/forms/d/e/1FAIpQLSczNMwnoX0ObUHGP1LcoB-UPmcheqaHfx668UUPWx4pWAggkw/viewform?usp=sf_link), for things you want me to know.

## Return of the Textbook

Textbook time! Chapter 6 is on **Loops**.

This is a *definite* loop:

~~~python
for i in range(5):
    print("This will definitely print 5 times.")
~~~

This is an *indefinite loop:

~~~python
import random
while True:
    if random.random() > 0.5:
        break
    else:
        print("There's a 50% chance this will print each iteration of the loop ")
~~~