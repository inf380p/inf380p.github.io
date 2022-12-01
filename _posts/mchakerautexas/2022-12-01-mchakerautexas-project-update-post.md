---
layout: post
author: mchakerautexas
title: "Mufaddal's Project Update Post"
---
### Progress so far
I have made significant progress in my project thus far, and these are my updated milestones with their status
|Milestone|Status  |
|--|--|
|Create a functional menu, with selectable menu items|Done|
|Create a shape for the actual astronaut, and have them animate flying up and down in the menu| Done|
|Create shapes for obstacles and background landscape objects(extra!)|Discarded|
|Implement the start game, and have the person just float up and down based on the user input|Done|
|Implement obstacles populating on the screen|Done|
|Implement motion|Done|
|Implement object collision|Done|
|Implement scoring|Done|
|Implement the high score section|Done
|Implement leaderboard|Started|
|Display score and game over splash|Started|
|Implement saving scores to a file|New|
|Add increasing difficulty levels|New|

### Are there any roadblocks ahead? Is there anything your group can do to help out?
One major issue I am facing right now is in my game design. The project requirements for Turtle state that the game has to have a clear win condition, and the way my game is structured, it is an endless runner. This means there is no end in sight. I am still thinking of creative ways to modify this formula and add an ending stage to the game. I will discuss this with my group today and try to come to a solution.

###  Are your milestones ambitious enough? Make sure to include some stretch goals.
My milestones were not ambitious enough the first time I posted project plan. Since then I have revised them and added features that are stretch goals. For example, adding increasing difficulty levels to my game is going to be a tough algorithmic challenge, because apart from ensuring the game gets harder, I also need to ensure that the game is winnable (that the character survives with human-level reaction times and the controls I have provided). Having too many asteroids fly on the screen, such that it becomes an impossible scenario to escape them, would be a fail in this task. I am still thinking of a way to do this to make the game as difficult as I possibly can.

###  Are your milestones too ambitious? Make sure to break down the unglamorous parts of coding into chunks that reflect the actual work to be done.
There were some milestones like drawing the shapes for astronauts and the asteroids, that were too ambitious. I think that it would take too much time and creative energy to draw complex shapes like those using turtle. I have since then opted into using images instead, and just drawing them on the screen instead of these shapes. I have also structured my code nicely so that each scene is its own Python class (and file), this helps me keep my sanity as I read the codebase.

###  Are you able to keep to your plan? Looking back at what you’ve actually done, is the difference accountable to bad planning (i.e. not anticipating what needed to be done), bad execution (not doing it), or something else?
I believe that I have made much more progress than I anticipated to have made by this time. This is mainly due to my underestimation of my abilities but also due to the fact that I found many many resources online on game development using Turtle. I feel like at the current pace, I will be able to finish the project by the submission deadline and deliver a polished and finished playable game on the browser!

Here is my code as it stands right now:
<iframe src="https://trinket.io/embed/python/603c35baf6" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
