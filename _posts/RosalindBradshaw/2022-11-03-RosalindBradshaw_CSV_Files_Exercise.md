---
layout: post
author: Rosalind Bradshaw
title: "Rosalind Bradshaw's CSV Files Code and Reflection Post"
---

This code exercise might be the most difficult one I've worked on thus far. I have never done any work with a full program written by someone else that I am 
then edititng. On the first day of looking at the code I remember being indimidated by the size, density, and complexity of the code and struggling to get a 
handle on what exactly I was looking at.

The first thing I did was run the code a bunch of times to figure out what it was delivering and why and where the end results were coming from. I started
trying to figure out where the "Do you want University in simplified print view?" questions were coming from. I spent a lot of time digging through the code and 
the associated modules to find where that was originating. Finally I realized that `{header}` is a variable – was changeing based on which iteration was being
processed in the `columns_to_print` loop.

```
selected = interface.input_is_yes(f"Do you want {header} in simplified print view?", default = 'y')
```

After that, I had found a couple of spelling errors in the code, so I went ahead and fixed `Contine` and `compate`, even though those didn't have any affect
on the code itself.

Eventually I started getting a handle on some of what the code was doing and asking and felt comfortable enough to start modifying it based on the to-do list.
The first thing was putting the code into a `while` loop, which was easy enough. I used a number variable to control the `while` loop, so that it only runs as
long as the `option` variable is equal to 0.

```
option = 0
while option == 0:
```

The next item was also pretty simple, adding a new main menu option. I added a fifth option to the already established menu called `exit` and used that option
to set my `while` variable to equal 1. I also moved the "goodbye" `print` statement into that option, making a clean way to exit the code.

```
# List of choices to present in main menu 
  menu_dict = {
    "1" : "Browse rows of data",
    "2" : "Print specific row",
    "3" : "Select columns to print",
    "4" : "Change data file",
    "5" : "Exit"
  }
 ```
 ```
 elif choice_str == "5":
    option = 1
    print("Goodbye")
```
 

The third task, refactoring `columns_to_print` into a function, was much more challenging for me. I struggled with this for several days, trying several
different ways of trying to make it work. Finally, I had to admit I was stuck and use the posted class video to help me over that hurdle. I ran into many
of the same issues that were demonstrated in class, such as the function printing nothing when called. I now realize this was because I hadn't actually given
the function anything with a `return` statement. That is definitely something I'll have to remember in the future when using functions.

I'm still struggling with the rest of this code exercise but I'll keep working on it. CSV files are much more complicated than just drawing pictures with
turtles, which is good, it makes a good challenge for me to expand my own skills and keep building on what I already do fairly well.

My (in)complete code as it stands right now:

<iframe src="https://trinket.io/embed/python3/d9f092aeec" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
