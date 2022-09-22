---
layout: post
author: elliott
categories:
  - exercise
  - how-to
inclass: true
title: Embed Trinkets & your so-far reflection into a post on the class website
canvas: false
inprogress: false
---

Use the instructions below to submit a post with your trinket embedded into it.

**Replace `tommytester` with your author name, and the title with whatever you choose**


## Writing about Code

Programmers often need or want to share their work with others.  We're going to do that by making a
jekyll post with our code, a screenshot of our picture, and any thoughts or reflections we have on
the experience.

First you need a header:

<pre>
---
layout: post
author: tommytester
title: "Tommy's Reflection on the Class So Far"
---
</pre>

Then, under the hyphens, put the content of your post, and format it so that your interactive code and static code blocks will show up.

### Reflection Text

Include your pre-composed reflection on the class so far in the post. You can paste the text into github and click on the Preview pane to see what it will look like. From there, you'll need to do a little bit of reformatting.



### Interactive Code

To include embedded interactive trinkets in your post, go to your Trinket program(s) and [follow the instructions here](https://docs.trinket.io/getting-started#/2-sharing-trinkets/embed-a-trinket)
to get the embed code.

Then, paste the code into the text of your post.  At this point your post will look something like this:


```
---
layout: post
author: tommytester
title: "Tommy's Reflection on the Class So Far"
---

Here's the program I'm embedding:

    <iframe src="https://trinket.io/embed/python/c26c35e489" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
```

## Static code blocks

Add at least one static code block to your post, containing excerpts from your embedded program.

If you want to display code that's not interactive (to talk about something you did, for instance), the cool grey boxes above come from telling Jekyll that we're about to write code using backticks: `

<pre>
```
# Look what I did here:
tess = turtle.Turtle()
tess.color("blue")
tess.pensize(3)
tess.forward(50)
tess.left(120)
tess.forward(50)
```
</pre>

Here's that code rendered by Jekyll:

```
# Look what I did here:
tess = turtle.Turtle()
tess.color("blue")
tess.pensize(3)
tess.forward(50)
tess.left(120)
tess.forward(50)
```


## Images

Finally, if you need to embed an image, do it thusly:

<pre>
![Turtle image](https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg)
</pre>

That code looks like this:

![Turtle image](https://www.utexas.edu/sites/all/themes/utexas/img/general/logo.svg)



