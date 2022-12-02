---
layout: post
author: inf380pcoder
title: "Inf380pcoder's progress report and updated draft #2"
---

**Progress Update**
<br>This past week, I’ve continued to make progress on my final project. I’m still generally on track with my  timeline and I’ve been able to cross a few more items off of my list: 

- [X]  Dictionaries
- [X]  Custom modules
- [X]  Definite `(for)` loops
- [X]  Custom functions
- [X]  Have a graphical interface, responding to click events
- [X]  Consistently available help dialog 
- [X]  Display information about programs state
- [X]  Have at least 3 levels
- [X]  Extend a custom turtle class
- [ ]  Have a ‘win’ screen
- [X]  Have an iterative interface (halfway, I still need to put in prompts after the “Game Over” screen for all three levels)
- [X]  Use one or more custom images 

I was able to get most of my goals accomplished for this week. One of the things that is still tripping me up is the scoring and the 'win' screen. I had trouble figuring out how to input a score feature in my program. I figured out how to add an `onclick` feature that adds a point every time the user clicks on the screen. However, I had trouble figuring out how to integrate this so that you could do two click events at the same time, drawing on the game board AND adding points to the score. By doing some research, I found that adding `add=True` to the second `onclick` function is one way that this can be fixed, allowing both click functions to work simultanously, although I’m sure there is a better solution out there. My problem is that I only want to add a point when the user misses a bomb. As it is now, the program still adds a point when a bomb is hit. I’m still not sure how to fix this. 

I tried putting a score function within my `clicky` function that would execute the drawing on the game board (the box() function) and then add a point to the score. I tried to do research on Stack Overflow and attempted several things such as: 

```python
score = 0

def clicky(x, y):
    if -130 < x < -100 and 85 < y < 115:
    	box1()
    	score += 1
    	sara.clear()
  	sara.write("SCORE: {}".format(score), None, "center", "10pt bold")
    if -100 < x < -70 and 85 < y < 115:
    	box2()
	score += 1
    	sara.clear()
  	sara.write("SCORE: {}".format(score), None, "center", "10pt bold")
```

```python
score = 0
scorestring = "SCORE: %s" %score
sara.write(scorestring, False, "center","10pt bold")

def clicky(x, y):
    if -130 < x < -100 and 85 < y < 115:
    	box1()
	score += 1
   	scorestring = "SCORE: %s" %score
    	sara.clear()
     	sara.write(scorestring, False, "center","10pt bold")
   if -100 < x < -70 and 85 < y < 115:
    	box2()
	score += 1
    	sara.clear()
  	sara.write("SCORE: {}".format(score), None, "center", "10pt bold")
```

Neither of them worked because they didn’t recognize the `score` component. If I put the score inside the function it only recognizes a score for the first click, but it doesn’t change when the user keeps on clicking. I also saw several programs that utilize the `global` function, but I wasn’t able to figure out how to use that correctly either. I can’t seem to work out how to have the score increase periodically, it either continually adds or doesn’t add at all. I’m hoping that I’ll be able to troubleshoot this in class and get some tips. I’ll need the score function in order to execute the 'win' screen, so I’m hoping to find a workable solution! All in all, though, I’m feeling pretty good about where I’m at currently and I think I should be able to finalize the program in the next week. 

**Week 3**
- [X] Finish levels 2 and 3 
- [X] Finish the help screen 
- [X] Integrate interface, help screen, and level 1,2, and 3 trinkets into one program 
- [ ] Figure out how to input a score function and integrate it with the 'win' screen :construction:(Still working on this...):construction:
- [X] Extend custom turtle class 

**Week 4**
- Work on iterative interface and final bugs to make the program more seamless
- Complete the final reflection


 <br>:joystick: **Here is my current program:** :joystick:
<iframe src="https://trinket.io/embed/python/523654d891" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
