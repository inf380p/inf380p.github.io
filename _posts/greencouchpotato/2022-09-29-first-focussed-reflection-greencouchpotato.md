---
layout: post
author: greencouchpotato
title: "First Focussed Reflection"

---

## Introduction
**Trial and Error** , simple as it sounds, it’s perhaps one of the most effective methods that can teach one critical problem solving skills. And as always it stands true for me.

### First Class
I’m learning to code for the first time through this class and I was quite apprehensive about it from the beginning. Looking at a black screen full of characters that I couldn’t make sense of was intimidating, and I think that withheld me from trying.

My first class was exciting (if I could summarise it in one word). When I first looked at the examples presented in the first class, I assumed that it’s take me years to even begin to learn how to do that. But most of all the class gave me confidence. And I wanted to learn!

Below is my **first at home assignment**. I probably might have gone overboard, but I was very excited to work on this. 

<iframe src="https://trinket.io/embed/python/5cde5e345e" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

My takeaway from this was simple - Python works on command. It reacts to the prompt that was communicated to it in a language that it understood. It is highly logical, and a few trials and iterations helped me get my output the way I wanted it. 

### Current Experience

The textbook was instrumental in helping me explore the different components of the language. With the help of the classes, I found the first few chapters of the textbook easy to follow through and was able to get most of the questions right in the first attempt. Probably since the complexity of the program was less and the code was only a few lines, I enjoyed the debugging section the most.

As I progressed through the chapters, I realised that most of the errors that I made were syntax errors.

###Challenges
I found functions to be the most complex concept yet from the sections I’ve learnt. In particular, these 2 functions - 

Math functions and 
Defining Functions

Probably there is some overlap between these 2 as well. An example of a type of problems that took a significant amount of time for me to complete is the below - 

```
def get_initials(first, last):
    return first[0] + last[0]

def main():
    print(type("Hello"))
    print(type("Class"))
    print(type(42))

    print(get_initials("J'Quan","Alik"))

main()

from unittest.gui import TestCaseGui
class myTests(TestCaseGui):

    def testOne(self):
        self.assertEqual(get_initials("J'Quan","Alik"),"JA",'''get_initials("J'Quan",'Alik')''')

myTests().main()
```


Although debugging required me to only modify the digit in the first function definition from -1 to 0, it took me a while to understand the rest of the code (defining testOne, importing unittest.gui, etc) I assumed that the complexity of the rest of the components were a significant source for the error. I tried googling their usage and tried to change variables as well.

However, I slowly realised that since the initials were being printed incorrectly, the problem must lie in just the sections (definition in particular), because the output command was straightforward. Bingo! I was able to get the required result and pass the test. This is an example of my thought process with most of the practice exercises.

### My Process

My process is, try to write or debug code > If there’s an error, refer to the chapter and compare specific functions with the examples provided > if the error persists, google the meaning and usage.

This has worked well for me so far! 

***And I look forward to learning more!***

