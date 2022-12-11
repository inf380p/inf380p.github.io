---
layout: post
author: Rowan-Loft
title: Rowan-Loft csv and Reflection
---

## Initial Reflection

During my initial approach to the csv code, my main confusion came not in the code itself, but the csv sheets **ischools-clean.csv** and **ischools-messy.csv**. One of the lingering issues that I've had with our class is word choice. For some methods, or variables, or other, what makes sense to someone with experience in python's language makes little sense to me since I'm not used to seeing some of the wording we use used in these ways. With the csv files, the confusion came from my thinking that the **messy.csv** was much easier to read than the **clean.csv**, even though it contains information that doesn't have context written in. After speaking with someone who knows much more about coding, I realized that the reasoning is because I have to define what is "messy" or "clean" from the perspective of the code and computer that will be reading the code and displaying it, not me. I will elaborate more on why I think this in my next reflection.

One of the first things done to the code was creating the while loop that users would be put into when interacting with the main menu. In our class example, we created a loop using `while True` and `break` that was called if the user input "5" into the main menu. While my change was not groundbreaking in anyway, I think it simplified the jumble of the code a bit, and only had to be called at the top:

```
while choice_str != "5":
  # Tell user what choice they made
  print(f"You chose {choice_str}:")
  print(menu_dict[choice_str])
```

using this code led to the same result, choosing "5" in the main menu broke out of the while loop that I created and printed `Goodbye`.

Here is my initial trinket:

<iframe src="https://trinket.io/embed/python3/6d64fdf41c" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

## Expanded Reflection

During my second week, I re-approached the "clean" and "messy" csv's to try and make **ischools-messy.csv** readable for the user. In order to do this, I first had to talk with someone with more experience than myself about what made this file messy. What really gave me my lightbult moment was realizing that there were "invisible" newlines, only 3 headers: `University`, `Location`, and `Membership`, and more information that what would apply to just those three headings, which would soon become: `Website`, `School/Unit`, and `Region` after using the *regular expression* suite to do some cleaning. To the best of my understanding, *regular expression* is used to match and extract targeted strings.

After using *regular expression* to target the `\n` that I could not see with my own eyes, `re.split` was used to separate these cells, `re.sub` was used to replace the unknown "**(3)**"'s, etc. that were present in the messy data but with no explenations, and the information that had not been given headers in the .csv itself were assigned new keys. While I initially had the thought to just manually remove these oddities and manually assign more headers to the .csv itself, I was told that when working with the data and code, I should try my best to ensure that me .csv's were as close to the original as they could be, and that altering them would mean my code was ultimately too different from anyone elses. 

Here is my expanded trinket:

<iframe src="https://trinket.io/embed/python3/492552ae4b" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
