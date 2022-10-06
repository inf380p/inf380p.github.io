---
layout: post
author: mchakera
title: "Mufaddal's reflection on the class so far."
---

# My reflection

Intro to programming has been a fantastic experience so far. I came to this class with some programming experience and did not think I would learn as much as I had learned already, even though it was just the beginning. The textbook is fantastic, with its interactive exercises and examples. My first big light bulb was when we were working with Turtle, and I wondered how I could make not just a square or a triangle... but any polygon. It was at that point that I came up with the following code:


<iframe src="https://trinket.io/embed/python/1377ae1ec1" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


What I did above allowed me to connect math with programming and was a gratifying experience.

Though, there was always a lingering question in the back of my head: How does Python understand what Turtle is? Why can you import Turtle and not any other arbitrary package? I started googling and soon found that Turtle is included in the standard library packages that ship with the default installation of Python. I then proceeded to install Python on my computer and try it out to ensure it was true.

I started exploring Turtle more, trying to understand its capabilities. The second coding exercise helped me understand more about Turtle. For example:


<iframe src="https://trinket.io/embed/python/daacb02d24" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

I hope to learn much more about Turtle, and not just that, about other software, I could use to draw and do other amazing things in Python. I'm sure the fuzziness will clear as this class goes on. I also found the internet an amazing resource and seem to learn best by example.

Among the many strategies I tried, the two that worked out best for me were perseverance and learning by example. Programming is confusing, and there are many exceptions and unusual behaviors that a programming language exhibits, which is often confusing. So, it is very easy to give up. I found that
1. There are unlimited resources on the internet.
2. If you give it enough time, you can always master it. Practicing is the best way to learn anything.
So if you keep at it, you'll be able to do it.

Another thing that helped me a lot was looking at and analyzing many examples. For instance, I found the Conditionals chapter in the textbook quite confusing. But the given code examples helped me master the concept, and I was able to complete all of the chapter assessment questions. An example of a solution I'm proud of is below:
```
rainfall_mi = "1.65, 1.46, 2.05, 3.03, 3.35, 3.46, 2.83, 3.23, 3.5, 2.52, 2.8, 1.85"
rainfall_mi = [float(r) for r in rainfall_mi.split(",")]
num_rainy_months = 0
for r in rainfall_mi:
    if r > 3.0:
        num_rainy_months += 1
```
