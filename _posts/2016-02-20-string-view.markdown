---
published: true
title: String View
layout: post
tags: [string, safety, ownership, raii]
categories: [proposal]
---
My favorite proposal for the C++17 standard is [string_view](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3762.html). If accepted it adds a new type to the standard library which describes a string but doesn't own the memory containing the string data. What's the point one might ask, and oh, isn't this unsafe?

## Why do we need this? ##
Performance and convenience, mostly. A lot of code that deals with strings will at some point work with substrings. This means that part of a larger string is cut out to form a new smaller string to do further work on. Without string views one can either create a new string, or work with iterators and describe the substrings with a begin/end pair.

The first solution is highly inefficient as it wastes memory to hold the data of the substring and precious CPU cycles in order to copy the data. Since we're dealing with C++ here, it's safe to assume that performance is at least somewhat important.

The second solution is fast but makes writing the code more difficult. The easy convenience functions for strings become much longer structures. Still, this is what I chose to do most of the time. It's a bit annoying, but it works and it's fast.

String views solve this problem by essentially wrapping the iterator pair into an object that behaves like a string in pretty much any way. It's even castable to a string if you need to work with some external library that expects an std::string. This will of course cause the aforementioned overheads. However, in cases where a string is manipulated multiple times, this cast may happen only once, so there's still a performance improvement.

The real kicker is the fact that string views allow the programmer to write efficient code *without* having to think too much about it. As long as one understands what a string view is and what it represents, writing code with string views is a simple as with strings.

## Is it Safe? ##
Okay, so the string view doesn't own the memory. Won't this lead to segfaults and security issues. Well, if you don't know what you're doing, yes that can happen. It's the exact same situation with the iterator solution though, or for any use of iterator use in general.

String views are meant to be used as temporary objects for string manipulation, and when used as such they are perfectly safe. When you try to use them to store data, you will get a not so funny surprise. In order to avoid problems, treat the string view like a reference to a string object, not an object itself. Since any decent C++ programmer should be acquainted with references and how they work, I really don't see a big safety concern.