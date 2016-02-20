---
published: true
title: Why I haven't given up on C++
layout: post
categories: [debate]
---
I've recently come across [this article](http://dorinlazar.ro/the-day-i-gave-up-on-cpp/) in which the author attempts to outline why he is no longer using C++. I figured it would be a good idea for me to consider each of his points and state why I either agree with them or not. I may even have learned something along the way.

> C++ IDEs suck. Big time.

There's something to this. Most C++ IDEs have problems, probably because C++ is a difficult language to fully parse. I've only ever used Visual Studio and KDevelop. Neither was awesome, but neither was horrible either. VS is a little strange to get used to, like almost all Microsoft products. KDevelop crashed a lot until around 2014, then started working relatively smoothly. It's missing some debugging features, but that's not too bad. All in all I don't think C++ IDEs are all that horrible. The fact that I haven't been forced to try any others show that they work just fine for most tasks.


> It's an unmanageable language.

I've never really understood the big fuss about split header files. They work well, really aren't a big hassle and can even serve as a short overview of the code. Include guards are a bit ugly though, I agree. But I must say, I've not come across a compiler without #pragma once in the past few years. What I really don't understand in this section in the original article is how headers are supposed to be fine in C but somehow horrible in C++.

> It's a barely portable language.

I'll really have to disagree here. The standard libraries and Boost work fine without any preprocessor handling. Unless you want to do low level optimizations, this is just not an issue. And don't get me started about Java being portable. It's portable on paper, not in practice, but that's a topic for another post.


> It's a counterproductive language.

I honestly don't quite understand the point that is being made here. Something about trying to implement a game ladder and C++ containers being a problem. A problem how? I don't know what's supposed to be unintuitive about standard containers. Maybe the libraries he used had odd behavour. I don't know.

> STL sucks.

Now here I really disagree. I think the STL is the one point where modern C++ really shines. It's fast, its intuitive, and it's reasonably simple. Most of the criticisms he writes are about the naming of the data structures. The thing is, the naming scheme makes perfect sense if you have any idea about what these data structures are about. They are not simply containers for putting stuff. They are specific containers that are meant to be used in certain ways and optimized for that usage pattern. As always, the motto is: You don't pay for what you don't use. The unified interface for containers are the common iterators. Iterators work just fine, with minimal overhead.


>The focus on performance actually makes STL impracticable.

The focus on performance makes STL great. It's easy to write some working, but slow container structures. But C++ is meant for writing efficient code. You don't pay for what you don't use.


> namespace stupidity

Namespaces actually make large projects manageable. The code may not look nice, but it's quite readable. I don't understand this obsession with nice looking code. In many cases it makes sense to use a local typedef though. Not for making the code shorter, but in order to make it even more readable and adaptable.


> The language sucks. It sucks because it's so complicated.

I agree it's complicated, but that's not necessarily a bad thing. You really don't need to understand the whole thing to start using it. And when you've been using it for a while and start to understand the intricate details, it becomes very, very powerful.


In summary, I disagree with most of the points made. The real reason I still use C++ though is because it is unrivaled as the best high level, low level programming language. You can write highly abstract code which yet obeys tight hardware level criteria. It's often not easy, but just because it's difficult doesn't mean it sucks. I haven't given up on C++, and don't think I will any time soon.