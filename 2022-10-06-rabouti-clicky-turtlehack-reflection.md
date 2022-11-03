--- 

layout: post 

author: rabouti 

title: "Rabouti’s Clicky Turtlehack and Reflection" 

--- 

 

 

Since I consider myself an artist and enjoy making art, I wanted to make something artistically inclined – hence, I made a drawing game where users draw clouds (however they want) by clicking the screen around a pre-drawn rainbow and can use the arrow keys to make Tina turtle fly around the rainbow/screen (had to get click events in my game somehow). 

## Clicky Rainbow and Flying Turtle 

<iframe src="https://trinket.io/embed/python/e7e00f62a1?outputOnly=true&start=result" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

 

To make the unique shape of the clouds upon clicking, I used the “Python Basics” page on our class website as a reference, specifically the embedded trinket titled “Why Python Is Cool – Cool Interactive Animations.” I had a frustrating time trying to write a clicky function for a solid circle (to make clouds) on my own, so I rewrote/edited the trinket on the class website (from day 1) to make my desired cloud shape. I tried to be original, which wasn’t the best idea given my novice-level status. I ended up overwhelming myself by starting from scratch opposed to using the “starter code” for this assignment. However, I did incorporate some of the “starter code” into my program to make my life a little easier (like the key events). My program is pretty random and chaotic, but I feel like that’s fitting since I, too, am random and chaotic. I really struggled getting started on this assignment due to the unlimited range of creative freedom in tandem with using my current level of fluency. I definitely overcomplicated this assignment (sorry Dr. Hauser).  

My lightbulb: I should have used the starter code – would have saved me a lot of time, stress, and panicking.  


To make the clicky cloud circles, I rewrote/edited these functions using multiple turtles:

```
def create_turtles(screen, n = 2):
  for i in range(n):
    MyTurtle(screen)
    
def move_turtles(screen, dist=7, angle = 6):
  for i, turtle in enumerate(screen.turtles()):
    turtle.circle(25)
    x, y = turtle.pos()
    turtle.color("white")
```

To make the rainbow, I wrote a function to make a semi-circle with a dynamic radius and color. I added a "z" at the end of "colorz" just for fun. 

``` 

def draw_rainbow(colorz, radius, val): 
    tina.color(colorz) 
    tina.circle(radius, -180) 
    tina.penup() 
    tina.setposition(val, 0) 
    tina.pendown() 
    tina.right(180) 

``` 

I made a list for multiple colors within the rainbow.  

``` 

colorz = ['violet', 'indigo', 'blue', 
       'green', 'yellow', 'orange', 'red'] 

``` 

To make the semi-circles form a rainbow, I made this loop.  

``` 

for i in range(7): 
    draw_rainbow(colorz[i], 10*( i + 7), -10*(i + 1)) 

``` 

## Frustration 

The most frustrating part of this assignment was all of the debugging I had to do. I had to work backwards in order for everything to execute in the correct order - understanding the order of operations is still fuzzy for me (especially when I custom-made the entire program). For example, I spent a lot of time trying to make my custom set up function work in tandem with my custom rainbow function. For some reason that I still don't understand, the rainbow function would either execute before the set up function or not at all (which both were not my intentional result). So I made the rainbow function part of the set up function/completely changed my original plans for my set up screen - there was probably a simpler/better solution. 
 

## Takeaways 

My rainbow drawing game is still not where I want it to be, but I’m excited to continue to work on it and make it better. Additionally, this assignment made me realize I spend too much time ruminating – I need to take more advantage of retreating/letting things incubate.  

Being a perfectionist + learning Python = beautiful yet time-consuming chaos.  


 

Lastly, making posts on GitHub is still fuzzy for me. I feel like I am fundamentally missing/misunderstanding something. Branches? Forks? What? Nevertheless, with time and practice, I think I’ll be fine. Somehow, I've managed this far. 
