---
layout: post
author: inf380pcoder
title: "Inf380pcoder's progress report and updated draft"
---


Overall, I think I’ve continued to make some good progress on my final project over the last week. I’m still on track with my initial timeline for the most part, and I’ve been able to cross some more items off of my list:

-  [ ]  At least one external data file<br />
 - [X]  Dictionaries<br />
 - [X]  Custom modules<br />
 - [X]  Definite `(for)` loops<br />
 - [X]  Custom functions<br />
 - [X]  Have a graphical interface, responding to click events<br />
 - [X]  Consistently available help dialog <br />
 - [X]  Display information about programs state<br />
 - [X]  Have at least 3 levels<br />
 - [ ]  Extend a custom turtle class<br />
 - [ ]  Have a ‘win’ screen<br />
 - [ ]  Have an iterative interface<br />
 - [X]  Use on or more custom images<br />
 
I was able to create a different interface, more in line with what I had envisioned last week. This allowed me to have a display of level options and a help menu available to the user before going in to the game itself. 

The biggest hurdle for me this last week was coming up with the actions for the game board. I envisioned making each square on the game board a `clicky` event so that when a player clicks on a space it displays either a bomb (game over!) or how close the user is to a bomb (using number 0,1,2 or 3), as in the original game. Coming up with the coordinates of the game board took more time that I thought. I realized after the fact that I should have just input `def location(x, y)` and print `(x, y)`, which displays the coordinates of a given point on the screen. However, I used the less effective method of :sparkles:trial and error:sparkles:, and eventually figured out the coordinates of the 4 corners of the board, subtracted the values, and was able to ascertain that each square was 30 units. This helped me to established both where the x and y coordinates were for the `clicky` function, and where the turtle had to go to write in the response for each square. For example: 

```python
def box1():
    bob.color("light green")
    bob.penup()
    bob.goto(-115,95)
    bob.write("0",None,"center","14pt bold")

if -130 < x < -100 and 85 < y < 115:
   box1()
 ```

I then repeated the process for each part of the gameboard. This is what I currently for level 1: 

<iframe src="https://trinket.io/embed/python/51c58e4552" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


I have the other two levels already mapped out. Since I have the main infrastructure of the game completed, it should make creating the other two levels much easier, as it’s just a matter of adding in the new values. I’m going to try to get the majority of the remaining work on done in the next week because I want to leave time for troubleshooting unexpected errors and completing the final reflection. In thinking through the remaining tasks, my plan for the next two weeks are to complete the following:

**Week 3**
- Finish coding levels 2 and 3
- Finish coding the help screen
- Integrate trinkets into one program (currently I have the interface and levels in separate trinkets, I just need to bring them all together)
- Figure out how to input a score function and integrate it with the win screen
- Extend custom turtle class (this one is still a little fuzzy for me, but I’m working on figuring it out!)

**Week 4**
- Work on the integrative interface and final bugs to make the program more seamless
- Complete the final reflection
