---
layout: post
author: scdai9
title: "Shih-Chieh's final project update and user interface draft"
---

### Introduction

I will do a data analysis project. Currently, I am playing an NBA Fantasy game, and I want to use Python to do data analysis so that it can help me to make some decisions.

### Progress
I found the data from https://www.nbastuffer.com/ They provide up-to-date data in CSV format. I think I am going to use the data from their website. 

Currently, I create a interface for my program. I defined these 5 actions for the user.

```
menu_dict = {
    "1": "Show Stats",
    "2": "Performance Leader",
    "3": "Run Analysis",
    "4": "Data Visualization",
    "5": "Exit",
}
```

For each action, the user may also be able to select the sub-action. For instance, if the user select action 2- Performance Leader, they will be able to see the leader by the criteria they selected. 

```
elif action == "2":
    print("1: By Point")
    print("2: By Rebound")
    print("3: By Assist")
    print("4: By FG%")
    print("5: By Block")
    print("6: By Steal")
    sub_action = input("")
    print("You select {}".format(sub_action))
```

I think my next move will be implement all the functions in this program.
### Roadblocks
Currently, I think everything is ok. One concern can be the sub-actions for some actions may be too many. For instance, in action 2, there could be more than 10 sub-actions. I think I have to find a way to provide better usability. Moreover, to visualize the data, I need to use third-party libraries. Therefore, I have to figure out how to use them.

### Revised Milestones
- [x]  Find Dataset
- [x]  Plan the interface (i.e. menu)
- [ ]  Data Preprocessing
- [ ]  Analysis Methods (Z-score)
- [ ]  Data Visualization
### My Trinket Code
<iframe src="https://trinket.io/embed/python3/aff9089212" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
