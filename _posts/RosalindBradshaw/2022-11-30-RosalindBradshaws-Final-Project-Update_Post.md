---
layout: post
author: RosalindBradshaw
title: Final Project Update Post
---

#### Nov 12-16: Base Functionality
- ~~Draw level maps on graph paper~~
- ~~Code level maps with `functions` for each section (Custom Modules, Functions, 3 levels)~~
- ~~Expand `Turtle Classes` (extended turtle class)~~
- ~~Code Start Menu with number entry options (iterative interface)~~
    - ~~Level 1~~
    - ~~Level 2~~
    - ~~Level 3~~
    - ~~Help
    - ~~Exit
- ~~Allow a user to navigate between new screens using the Start Menu~~
- ~~Code consistently available help menu (help dialogue)~~

#### Nov 17-23: Interactive Functionality
- ~~Research screen-clear functionality for between-level-transitions (program state)~~
- ~~Research click-counting ability for turtles~~
- Incorporate click counting into game levels
- Code scoreboard to display moves taken (program state)
- ~~Code player-navigation for each maze section (graphical user interface)~~
- ~~Boundaries for turtle movements~~
- Options to proceed to the next area

#### Nov 25-Nov 30: Background Functionality
- ~~Code list or dictionary of error codes~~
- ~~Incorporate error codes into main code sets~~
- Code images into the levels (custom images)
    - PC icons?
    - Transition images?
- Win animation (definite for loops, win screen)

#### Dec1-7: Playtesting and Debugging

#### Dec 8: Project Complete and Turned In

As you can see from my list I've managed to acomplish quite a bit of my original expected work plan. Though I didn't manage to complete everything by each 
expected deadline, that was more due to the fact of not being certain which tasks would happen in which order, than to any failure to complete on my part.
Certain tasks ended up being much simpler than I had originally anticipated, and so they got done more quickly than originally planned.

At this point, I'm working on figuring out how to incorporate the click-counting into my game. Dr. Hauser has graciously provided this code that demonstrates
the click counting functionality that we can build in turtle:


<iframe src="https://trinket.io/embed/python/efd34bb8e2" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


I'm hoping to take that code and incorporate it into my game to act as a way of scorekeeping for playthroughs. I don't know if this will end up working, though,
as the click counting seems to be taking over as the primary sequence in the game rather than running in parallel to the game. I'm thinking that is because
the game is having trouble listening for the mouse click and interpreting it in two different ways. I'll keep working on it though. May be this is something my
group has encountered and they can help me figure it out too.

At this point, I definitely feel as though my plans are ambitious enough. I've already spent a lot of time on this program to get it to where it is and all it
needs are some extra pieces to fully complete it. Before I turn in the project I'll have fully evaluated the click-counting to see if I can work it into the
code, or find some other way to display the game state, and incorporate the images and win animations.

If I have some extra time, there is some re-factoring I can do to help make the game play smoother, but overall I'm satisfied with where I am right now.

Here's the current code as it stands right now:


<iframe src="https://trinket.io/embed/python/a40e971a1a" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
