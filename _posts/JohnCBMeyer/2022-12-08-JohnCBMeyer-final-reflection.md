---
layout: post
author: JohnCBMeyer
title: "John's Last Post"
---

## Wow, that was a lot of work
Honestly, I assumed this would be a lot of work to begin with. It's a final project,
I'm still not incredibly comfortable working in Python, and I decided to work on
something I had never tried or even really thought about doing before. Still, that
was a *lot* of work, and my game is barely functioning compared to what I originally
planned. In this reflection, I'll walk you through my idea, some of the biggest
hurdles I found along the way, how I scaled things back, and what I eventually
came to as my final product.

## Original idea
Here's a quote from a younger, more naive version of myself who was still blissfully
unaware of how much of a pain making a text based game is:

```
I would like to make a text-based game based on D&D. My idea is to have a basic
dungeon crawl, with branching pathways and set enemies. If I have time, I'd like
to include random encounters and an equipment system. I'll start by making two
character classes, Fighter and Wizard, but if I have time, I'd like to end up with
four: Fight, Wizard, Rogue, Cleric. Each class will have a different set of stats,
including health, armor, accuracy, and damage. I would also like to give each a
class-specific unique effect, like Fighter gets a Block action that increases armor,
Rogue gets a Sneak Attack that does extra damage, etc...
```

HA! The fool!

But, really, I had no idea how difficult that would be. For reference, of the eight
or so ideas I had in that quote, two of them made it to the final version. And even
then, they weren't in the original form I came up with, but reduced to work within
time constraints.

I had so many ideas. Different classes would have unique special abilities, there
could be multiple enemies per encounter, enemies would have randomized attack patterns,
and there would even be non-combat oriented enounters that would rely on puzzle solving
or your character's abilities like athletics or knowledge.

In case it's still vague, yeah, none of that made it in. I'm planning on working
on this more in the future, and I think it would be great if I eventually manage
to create that original vision. For now, though, I'm just happy that I succeeded
in making something that works as intended. I hope. I'm not exactly a professional
software tester and programming gremlins seems particularly persistent.

## Challenges
Where to begin? I had never done anything with classes or object-oriented programming
before this class, and that experience only extended to the class extension hack.
(No, that wasn't really meant to be a pun, but here we are.) That was easily the 
biggest problem I encountered. I spent a good three days around Thanksgiving and
then another few days at home just trying to debug a single inheritance problem
I ran into.

The main class I created for this game was the `Player` class. It's the parent of
almost all other classes used in the program. Because of that, I really needed to 
get the inheritance right or nothing was going to work. I guess I could also have
just cobbled together a ton of classes without inheritance, but I really wanted to
practice making something more scalable. I'm not entirely sure I succeeded, but it
turned out better than any alternatives I was considering.

The `Player` class looks like this:

```python
class Player:
  def __init__(
    self,
    experience=0,
    level=1,
    health=10,
    attack=1,
    damage=1,
    armor=1,
    athletics=1,
    faith=1,
    knowledge=1,
    thievery=1
  ):
    self.experience = experience
    self.level = level
    self.health = health
    self.attack = attack
    self.damage = damage
    self.armor = 10 + armor
    self.athletics = athletics
    self.faith = faith
    self.knowledge = knowledge
    self.thievery = thievery
```

There's actually a lot more to it, but I am sparing you from the methods for the
moment because the major issue I had was with these attributes. To me, this seemed
straightforward. This is the parent class, I define a bunch of baseline stats for
players, then I create subclasses that alter these baseline stats. Except I had no
idea how to do that.

```python
class Fighter(Player):
  def __init__(
    self,
    name,
    health = 30,
    armor = 10,
    attack = 5,
    athletics = 3
  ):
    super().__init__()
    self.name = name
    self.health = health
    self.armor = armor
    self.attack = attack
    self.athletics = athletics
```

This is the `Fighter` class. It's a child class that inherits from `Player`, as
you can see. This is the current working version (and this is the only playable 
class in the final version of the game). This works, but only after I suffered through
trying to learn how the `super().__init__()` function works.

I tried things like `super().__init__(self.name = name)` and `super().__init__(name)`.
None of that worked. I considered dropping the classes idea altogether and making
everything with functional programming, with which I am much more familiar. But,
that felt like admitting defeat and I wasn't willing to do that.

And that's when I had an epiphany. I realized that certain attributes like `name`
didn't need to be in the parent function because I would never create a `Player`
by itself. It would always be created as a subclass. I realized that even child
classes need the `self` attribute and can't simply inherit that. And, most importantly,
I realized that I needed to define the attributes for the child classes after the
`super().__init__()` call.

Finally, after literal days of banging my head against the problem, scouring Stack
Overflow for answers, looking at page after page of documentation, watching hours
of tutorials on classes in Python... I had proper inheritance, and it was glorious.

I also ran into problems with the game's main loop, getting the program to restart
through a menu command, and several other things along the way. But none of those
problems took much time to solve and, more importantly, none gave me the same raw
adrenaline rush as finally figuring out the classes problem.

## Scope
I don't like setting reasonable expectations. I like aiming high and doing what
I can to achieve the original goal. That didn't work out, as I've already mentioned
once or twice.

I had to really think through what was core to my idea for the game and what was
just nice-to-have fluff. First, I decided to scale back the dungeon layout. I wanted
to have a branching path with interconnected rooms. Instead, it's now linear; you
get forward and you get backward. This allowed me to simplify the logic for travelling
between rooms and really cut down on the mental load of designing the setting.

Next, I scrapped special abilities. As I was having so much trouble just getting
the base classes to work properly, I realized I wasn't going to have the extra time
to think through exactly how I wanted to implement each class' special feature. Instead,
the only thing really separating them for now is their stats. Well, once I realized
that, there wasn't much point in having more than one playable class, so everything
but the Fighter has been put on the backburner as a future project. Enemies got
to keep their subclasses because they were mostly just names to begin with, and
having differently named enemies makes it easy to judge the current difficulty of
a fight more easily than just saying Goblin or Goblin+.

The last thing to go may have hurt the most to cut: noncombat encounters. I just
ran out of time for this one. Every tiny tweak that improved the core gameplay loop
of fighting, resting, and moving to the next room created huge cascading errors
that required time to go through and debug. As far as I can tell, the game is as
close to bug free as I can reasonably get it and I've been able to play from start
to finish several times in a row while testing. Designing interesting noncombat
encounters would have taken too long. So, rather than poorly implementing the system,
I decided to leave those aspects of the classes in for a future project, but there
are currently no violence-free encounters.

## The final product
Here we are, the big reveal. In it's final form (for now, think Dragon Ball where
everyone gets new 'final forms' every few seasons), the game has six rooms, with 
a unique enemy in each. You can move between rooms, rest to regain health, fight enemies,
and even suffer random encounters (only while resting). The goal is to win enough
fights and level up enough that you can defeat the lich in the last room and escape
the dungeon. Unfortunately, the difficulty bounces between cakewalk and brutally 
hard, mostly depending on how the first fight goes. The player tends to spiral out
of control pretty quickly, so the lich isn't exactly the impossible enemy I was originally
hoping. Even so, I think it's a reasonable first version of the game and I look
forward to working on it in my spare time for years to come.

So here it is, Dungeon Crawl:

<iframe src="https://trinket.io/embed/python3/a7b2c54d38" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
