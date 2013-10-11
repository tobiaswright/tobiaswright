---
layout: post
title:  "Three ways to make ajax callbacks with jQuery"
date:   2013-07-19 16:01:23
tags: code
color: red
---

Making ajax calls with jQuery is pretty easy. Beyond easy really. A basic set up looks like this:

{% gist 6041652 vanilla+ajax+call %}

I realize that jQuery comes with shortcuts like $.get and $.post, but I like using the full ajax call because it can be a little clearer for me. However the shortcuts can be very good, clear alternatives.

<!--more-->
	
1. Generally. you can attach an anonymous function to the success method. Once you receive data back it will run the function:

 {% gist 6041652 ajax+with+function+expression %}

 What I don’t like about this is it tightly couples the function to the ajax call. The call can be used only once, and parsed in only the one way. Unless it’s a pretty small block of code, it just seems like it can get lost to me. However, this method has served me well, although I probably won’t do it as much as my javascript gets more involved.

2. Next, you can use a function expression or function expression and put that in the callback. It’s still tightly coupled but because of it’s more modular nature, it might make a little more sense for someone coming in fresh to work on your code. By assigning the function a name, you can stay pretty explicit on what the piece of code does.

 {% gist 6041652 ajax+call+with+function %}

3. This one I picked up while working on a project for a hackathon. I basically needed to make similar calls to the same API. With methods above. I would have had to repeat the same block of code with a very small differences. Sounds like a good idea to make the call into a function so I can use it over and over:

 {% gist 6041652 ajax+as+a+function %}

So there are three ways to work with callbacks and ajax calls. There are a few other ways, but I think these can be the easiest to grasp.