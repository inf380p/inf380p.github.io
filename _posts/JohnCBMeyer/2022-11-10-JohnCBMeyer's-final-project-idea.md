---
layout: post
author: JohnCBMeyer
title: "John's Final Project Idea"
---

# Game or Data?
I would like to make a text-based game based on D&D. My idea is to have a basic
dungeon crawl, with branching pathways and set enemies. If I have time, I'd like
to include random encounters and an equipment system. I'll start by making two
character classes, Fighter and Wizard, but if I have time, I'd like to end up with
four: Fighter, Wizard, Rogue, Cleric. Each class will have a different set of stats,
including health, armor, accuracy, and damage. I would also like to give each a
class-specific unique effect, like Fighter gets a Block action that increases armor,
Rogue gets a Sneak Attack that does extra damage, etc...

# Implementation
I think the best way to accomplish this would be by having each class be... a class.
I know, predictable. Each class can have methods of the same name, but different
effects based on the class. Enemies will also have classes, like Goblin, Orc, Dragon,
etc... The goal would be to level up by defeating weaker enemies until you're
strong enough to fight the boss. Then, you move up (down?) a level in the dungeon.
The last boss will be something iconic like a lich, but along the way it would be
nice if I could add some puzzles in addition to combat encounters. I don't think
I'll include skill checks, because that would start getting too complicated, but
I might change my mind if it would make encounter design easier. Maybe a simplified
skill system like stealth, lore, athletics, mechanics? Each class could have different
scores in the various skills, which would make it easier or harder to accomplish
the various encounters.

Everything would be decided based on randomized rolls, like in tabletop RPGs.
The player will select an action from a list of choices, a random 1-20 roll will
be made behind the scenes, the result will be added to a modifier, and whether the
action is a success or failure will get printed.

I think keeping room descriptions in a separate text file (or maybe multiple text
files?) makes the most sense. The game will reference the text location when needed,
printing pre-written prose. As the game progresses, the game state will be kept
in a separate save file as well, updating at the end of each encounter.

I think the main player navigation will be done through number keys, selecting 
options from a pre-defined list. There will also be an option for help and an option
for the main menu.

# Initial class ideas
*Fighter*</br>
High armor, high saves, high health, middling accuracy, middling damage.
Special action: `Block` The fighter raises their shield, increasing armor for one
turn.

*Wizard*</br>
Low armor, low saves, low health, middling accuracy, high damage.
Special action: `Fireball` The wizard fires a magical ball of fire from their
staff, damaging all enemies who fail a saving throw.

*Rogue*</br>
Middling armor, high saves, low health, high accuracy, middling damage.
Special action: `Sneak Attack` The rogue makes a deceptive attack with their
daggers, dealing extra damage if the enemy fails a saving throw.

*Cleric*</br>
High armor, middling saves, middling health, low accuracy, low damage.
Special action: `Heal` The cleric calls to their deity for aid, regaining some of
their lost health.

# Initial enemy ideas
*Goblin*</br>
Low armor, low saves, low health, low accuracy, low damage.
Special action: `Mob` The goblin works with its companions, gaining higher accuracy
and higher damage if both goblins hit the target.

*Skeleton*</br>
Middling armor, middling saves, low health, low accuracy, low damage.
Special action: `Endure` The skeleton is especially resistent to destruction; when
reduced to zero health, it rolls a saving throw to heal for one point. This action
can only be used once.

*Dragon*</br>
High armor, middling saves, high health, middling accuracy, high damage.
Special action: `Breathe Fire` The dragon breathes fire, doing high damage if the
player fails a saving throw.

*Lich*</br>
Middling armor, high saves, low health, high accuracy, high damage.
Special action: `Animate Dead` The lich uses their necromantic powers to summon
a skeleton to fight for them.
Special action: `Power Word: Kill` The lich uses their strongest spell to attempt
to kill the player outright; the player dies unless they pass a saving throw. This
ability can only be used once.

# Final Thoughts
This sounds like a lot. I'm not sure I'll be able to accomplish all of this, but
I think it would be really cool if I managed it. I'll try to come up with a minimal
acceptable version of this idea for the first run, then iterate more details after
I've got a prototype.
