---
layout: post
author: <EnglandHam>
title: "Soojin's Project Update"
---
  
## My project idea and milestone :thought_balloon:
~~### My initial project ideas:~~ 
~~I want to do some kind of turtle video game with stories. Perhaps a cooking game or 1 vs 1 fighting game or even a dating reality-based show game since I am motivated by the story-telling part of Python and turtle exercises. I want to involve users to stay engaged with the story while using all the python concepts we learned in the story.~~ 
  
## Final project idea: 
I am making a turtle cooking game called Danny's Restuarant where the turtle accepts a customer and makes food for them, similar to the game Cooking Mama or Overcooked. For instance, if a customer turtle wants a burger in a specific order, Danny has to grab the bun and rest of the ingredients in the order the customer wants to win the game. The following game levels will get harder as a customer turtle will want more complex burger or other type of food. 


### (soft initial) Milestones:
1. Reflect back on all the Trinkets and homework problems that stood out to me (week 1)
1. Reflect back on all the Trinkets and homework problems that stood out to me (week 1) 
2. Narrow down the project idea into one and set another milestones that's do-able for me; discuss with the professor to see the possibilities (week 1)
3. Set up storyboard and Python concepts I want to incorporate into the game (week 1)
4. Try to focus on building the basic and external file, specifically for level 1 (week 2) I am a bit scared this will lead me to focus more on the front-end visualization
7. Wrap up the project, fix minor bugs, try to get it play-tested; contact the professor if any major issues rise (week 4)
8. Show off my game to my awesome classmates (week 4/5)

## Interface Draft
I am going to work on top of the clicky turtle exercise we did in class. Here is the [interface draft](https://trinket.io/python/1be9239cce). From here I can focus on setting up the visual background and creating a game where a turtle goes through an adventure to find his soul mate. I am still wondering how I will make it into 3 different levels but I feel excited to make much more complex and interactive game by utilizing this key:
```
myscreen.onkey(go_left, 'left')
myscreen.onkey(go_right, 'right')
myscreen.onkey(go_forward, 'up')
myscreen.onkey(go_backward, 'down')
```
For now, I will focus on getting the first level done and setting up an environment where a turtle can successfully interact with specific things to meet his princess turtle. 
  
## Discussion and future milestone 
From the discussion with my partner, my current interface draft had solid ground to work on my game further. She was excited to see the future game and its interaction with clicky and wasd functions. Although the interface draft doesn't have much going on, a lot of the functions like clicky, wasd, and win screen are there and I need to work further on them. My next milestones are:  
  
- [ ] create a game menu that takes you to the game or tutorial 
- [ ] create background for level 1 
- [ ] create ingredients using class or dictionary 
- [ ] have a customer turtle that shows what kind of burger it wants
- [ ] see the list of the ingredients Danny the chef has picked 
- [ ] be able to serve the burger to the customer turtle 
- [ ] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [ ] have a win screen 
- [ ] create level 2 after meeting all those requirements
- [ ] create level 3 after meeting all those requirements 
- [ ] be able to exit out of the game whenever or go back to the menu screen 
- [ ] have a help icon at the top where the user can access at any time 
  
  
## Project Update  
The current cooking game has a solid system going on. Danny is able to pick up ingredients and make a cutomizable burger. Compared to the last initial draft, my game now meets all these milestones I set up during the initial draft: 

- [x] create a game menu that takes you to the game or tutorial 
- [x] create background for level 1 
- [x] create ingredients using class or dictionary (still working on this- just needs to format the code to fit with the requirements)
- [ ] have a customer turtle that shows what kind of burger it wants
- [x] see the list of the ingredients Danny the chef has picked 
- [x] be able to serve the burger to the customer turtle 
- [x] be able to reset the burger if Danny wants to remake it  
- [ ] have an error screen/text if Danny made a wrong burger (wrong order of ingredients)
- [x] have a win screen (turned it off from my game for now to work on my game.py codes, but its in the codes)
- [ ] create level 2 after meeting all those requirements
- [ ] create level 3 after meeting all those requirements 
- [ ] be able to exit out of the game whenever or go back to the menu screen 
- [ ] have a help icon at the top where the user can access at any time 
  
Here is the current game: 
<iframe src="https://trinket.io/embed/python/9d286ceaf3" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
  
(P.S. I personally recommend going directly into the trinket website [here](https://trinket.io/python/9d286ceaf3), since my game requires to be on a full screen. After typing out that you want to help Tina, you have to click back on the canvas to make Danny move for the ingredients. When Danny is at the ingredient, you have to click on the ingredient for him to pick them up.)
  
### Are there any roadblocks ahead? Is there anything your group can do to help out?
I currently don't have a major roadblocks, except that I am not working on Python 3 and when I tried to use #!/bin/python3 shebang to import my CSV tutorial file into the main menu but failed to do. I ended up writing a code that manually imports the file, but I am not sure what's causing this issue. If you or the professor can figure it the issue, that'd be great! 
  
### Are your milestones ambitious enough? Make sure to include some stretch goals. Are your milestones too ambitious? Make sure to break down the unglamorous parts of coding into chunks that reflect the actual work to be done.
My current milestones are pretty realistic to me, considering my timeline and the knowledge of Python. Although I have tremendously learned a lot from this class, I am still unfamiliar with the whole concept of "thinking like a programmer" and I want to take my time with this game to **really** learn the basic concepts that will go a long way in the future. Some of the other bigger goals I could think of are: 
- [ ] create a main menu interface with clickable buttons 
- [ ] make the game smoother where Danny can automatically pick up the ingredient and the list of ingredient he picked up will show each time 
- [ ] allow the customer turtle complain if Danny made a wrong order (aka lose condition)
- [ ] make the tutorial CSV look nicer 
  
### Are you able to keep to your plan? Looking back at what you’ve actually done, is the difference accountable to bad planning (i.e. not anticipating what needed to be done), bad execution (not doing it), or something else?
I actually struggled a lot when trying to work further on the game from the initial draft. There were so many things I wanted to do in my head, but I wasn't sure which one to tackle first in terms of priority. I also felt really overwhelmed from other finals and coding finals felt like an immense unknown hurdle for me to tackle. In the end, I told myself to work on getting the main menu and level 1 done before this class no matter what. My game has a lot of rough elements but I am proud of the progress I have made so far. 
  
## Next step
I am definitely going to keep working on finishing the milestones stated above, especially getting Level 1 completely done. Once I have Level 1 finished with working functions like picking-up ingredients, serving successfully, having a win screen when serving a correct burger, and  having a lose screen when serving a wrong burger, I will be able to smoothly transition into Level 2 and Level 3. I will also work on the main menu and help icon to always be accessible at the top left corner after completing Level 1, 2, and 3. 
  
Thank you! 
 
