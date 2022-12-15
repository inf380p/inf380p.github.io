---
layout: post
author: mchakerautexas
title: "Muffu's Air Hockey and Reflection"
---

For this week's exercise, I took on the challenge of creating a game with Turtle(A big reason I am in this class is to learn game development eventually). This turned out to be a much more complicated thing to do, I ran into many hurdles that I will list below, but I was able to come up with a game after A LOT of research and time spent.

I got super excited learning about interactive controls in Turtle/Python. As I aspire to learn how to make games, I always asked myself: How do I get the user to click the screen or use a keyboard without using the boring `input` function? Well this week, my question was answered. So I chose to make a game. The simplest (yet still fun) game I could think of was Air Hockey. Here's my thought process: I am not artsy, so I wanted to make a game that involved little drawing/art. But I love to do game logic and math, so I thought it might be an interesting challenge to get a ball to bounce off of walls. Little did I know that this challenge would be overshadowed by so many others.

Challenges I faced and things I'm still confused about:
1. I did not know how to animate moving objects. After a bit of research, I discovered that essentially all games use something called a game loop and keep drawing the objects over and over again. Trying to loop over and draw in an infinite loop is not something Turtle likes. What I struggled with is clearing the screen because if I didn't, it kept drawing over itself, which was not pretty. Once I figured out how to clear the screen, it still came out very choppy, which I am still confused about how to fix.
2. SO MANY functions defined in Turtles documentation on the internet were just throwing a not found error. A big one was screen.screensize(). I did find window_width() and window_height() but found them not to be as accurate. As my game used these dimensions to draw things in the right places, this was a big blocker for me, and I worked my way around this by adding margins to all my calculations near the screen edge.
3. The original vision I had was to be able to drag my mouse around the screen and have the paddle follow. I couldn't figure out how to do this. Mainly because I needed a way to know when the mouse is clicked and unclicked, which is impossible in Turtle(as far as I know).
4. There were many variables I defined outside of functions, but when I used them in those functions, they behaved weirdly. I found out this is due to Python creating local variables instead of using the ones I defined above(??) This was a headscratcher for me, but thankfully StackOverflow came to my rescue and using the `global` keyword fixed this. Having to add global to all variables used in a function still seems highly redundant to me, maybe there's a better way around it?

After working around most of the things I listed above, refreshing my concepts of basic physics and math, and learning some foundational things about game development and design, I was able to come up with this, and I am extremely proud of myself.

<iframe src="https://trinket.io/embed/python/139526c9bd" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
