---
published: true
title: Is C++ a low level languange?
layout: post
tags: [high-level, low-level]
---
I often quip that C++ is the best high level low level programming language. The reason is that it can be as hight level as you like and almost as low level as is possible while remaining portable.

A short example: I often deal with embedded systems with heterogeneous processor systems. If a certain processor wants to access a certain element without too much overhead , it has to be N bytes aligned in memory. The required alignment is often different for each system. In this case I could do my memory management manually, but that would be ugly. I could ignore the issue, but it would degrade performance, often by an order of magnitude. With C++ i can of course use the rich template system and a custom allocator to simply handle the problem with the type system.

There are of course other ways in which C++ can realize low level constraints in a high level way. This is just one of the cases I came across this week.

The other thing is that, if necessary, you can really get down to the basics and write block of C-like code and use it inside C++. I generally discourage this practice, but it is sometimes useful to manually optimize a small piece of code here and there. The fact that each object has a fixed memory location really helps here.