---
layout: post
author: elliott
title: "Final Project Guide: Using Milestones to Plan & Refine"
categories:
- reading
- how-to
external: false
---


# Turning requirements into milestones

The final project has some requirements. Software engineering, and engineering more broadly, has long thought in terms of requirements: what does this need to _do_ to be successful?

Your milestones are your **translation** of the overall requirements into a contextualized checkbox for your program idea. 

For instance, if a requirement is to use dictionaries, your milestone might be something like:

- [ ] Keep track of player's lives, points, and levels using a dictionary
 
This would satisfy that requirement in the context of a program that needed to keep track of these elements of program state. There are other miles that would also satisfy the requirement, but if you pick this one it's because it fits with your other goals.

Some related code might be:

```python
game_state = {
    lives = 3,
    points = 0,
    level = 1
}
```

Subsequently, you'd use this `game_state` variable to update this information, and perhaps **conditionals** to change your program's behavior. The levels could increase difficulty, lives going below zero could end the game, and points (or any of this data) could be displayed to the user.

Another example of a different milestone satisfying this same requirement:

- [ ] Use a dictionary to translate US state codes to full state names

If you named this dictionary `state_names`, this would then allow you to use any state code as a key and retrieve the state's name:

```python
print("Data for " + state_names["TX"] + ":")

# Prints "Data for Texas:"
```

So, milestones are a tool for you to map the requirements of the project to specific design decisions.

# Milestones are criteria

Are your milestones theoretically accomplishable things that collectively **satisfy** the criteria in the final assignment?  

Consider this:

- [ ] Program has text-based user interface with five options

That's a description of a desired characteristic of your final program. Great! 

But...now what do you _do_?


This is a _plan_ to acheive the milestone:

- [ ] Milestone: Program has text-based user interface with five options
    - [ ] Create basic main menu with 2 options
    - [ ] Create functions for options one and two
    - [ ] Options one an two both print out data, unmodified
    - [ ] Implement option one to summarize data
    - [ ] Implement option two to allow user to search through data
    - [ ] Make interface for options three, four and five
    - [ ] Implement option three (more detail TBD)
    - [ ] Implement option four (more detail TBD)
    - [ ] Implement option five (more detail TBD)

You need not know ahead of time exactly what _all_ the steps in your plan will be. But you can sketch out several and iteratively **re-plan** based on what you learn along the way.

# A plan has steps, a sequence and a schedule

We just talked about breaking down steps. The two other formal components of a plan are a sequence (the order of the steps)

I already roughly sequenced my plan above. Here's an example of scheduling it:

For next Tues:

- [ ] Create basic main menu with 2 options
- [ ] Create functions for options one and two
- [ ] Options one an two both print out data, unmodified
- [ ] Implement option one to summarize data

___

To be Scheduled:

- [ ] Implement option two to allow user to search through data
- [ ] Make interface for options three, four and five
- [ ] Implement option three (more detail TBD)

__

Stretch goals (not needed for basic functionality):

- [ ] Implement option four (more detail TBD)
- [ ] Implement option five (more detail TBD)


Now, of course, this plan is incomplete because several of the **Criteria** like using
external files are not addressed if I execute just this plan.  In fact, reading in data
would need to happen before some of these steps. But you get the point.

Your plan is a **living document** that you will re-submit and revise every class until
we're done.  In each submission, analyze what you did in comparison ro your previous account of the plan
and plan out what you'll do before the next class.  In this way you'll get a good sense
of your pace.  Some things will be easy.  Others will be hard.  By reflecting on each
iteration you'll get a better sense of what will take more time in your future plans, and
you should get more accurate as time goes on.

# Going off-plan

Sometimes you'll be tempted to go off plan.  Do this consciously, and reflect on it.  Did you
not think of a required thing when you made the plan?  Revise your plan and try to get better
at planning for next time. Or did you get distracted?  In that case, get back on plan and
save your explorations for after you've hit most or all of the requirements.

# Tracking and updating Milestones & Plans

I want your milestones list to be a living document and, like your code, for you to compare how it changes over time. So, in your project updates and in your final reflection, provide a sense of how and why your milestones and plan have evolved.