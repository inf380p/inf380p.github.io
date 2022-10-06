---
 layout: post
 author: unixEnthusiast
 title: “unixEnthusiast’s Chessboard and Reflection”
---

I liked the concept of the Hotter-Colder game suggested in the ideas topic and decided to give a little spin on it. I thought of adding a chessboard to the screen and then assigning a cell among them in random as the target. This can be accomplished by the random module I found in the python documentation as part of the internal implementation of the language by importing the 'random' module.

The main issue I found was to correctly use the loops as well as the conditionals to make sure the chessboard is setup correctly. I was making mistakes when trying to assign the black and white colors to the cells but then was able to figure it out and correcetly assign it.

After that, I assigned the user to click on various cells to determine how far they were from the target. Once the game started, we can derive the distances on the clicks and see if the new distances are more or less than the last one and prompt the user for the same. Once the user reaches the target cell, we can declare them the winner!

I really enjoyed this exercise as I was finally able to find some motivation and creativity to do a random program and this is something I've struggled with in the past. I think I will try to enhance my chessboard program in the future and try to add more functionality to it, maybe try making it into a full fleged chess game! I feel Prof. Hauser's classes have helped me in this direction greatly and I am eager to learn more!

The trinket embed:

<iframe src="https://trinket.io/embed/python/75942b889c" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
