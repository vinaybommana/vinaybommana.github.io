---
layout: post
title:  "F Strings - Python's String Formatting"
date:   2019-02-24
excerpt: "Python's new style of string formatting"
tags: [formatting, python]
comments: false
---

## Conventional String Formatting in Python

This is how we format strings in python - conventionally.
	
	for i in range(10):
        print("This is %dth index in the for loop" %(i))
	
	output:
	
	This is 0th index in the for loop
	This is 1th index in the for loop
	This is 2th index in the for loop
	This is 3th index in the for loop
	This is 4th index in the for loop
	This is 5th index in the for loop
	This is 6th index in the for loop
	This is 7th index in the for loop
	This is 8th index in the for loop
	This is 9th index in the for loop
	
but in the loop `i` can be any thing, What if we give `%s` instead of `%d`
in the formatting.

	for i in range(10):
        print("This is %sth index in the for loop, type of i is %s" %(i, type(i)))
	
	output:
	This is 0th index in the for loop, type of i is <class 'int'>
	This is 1th index in the for loop, type of i is <class 'int'>
	This is 2th index in the for loop, type of i is <class 'int'>
	This is 3th index in the for loop, type of i is <class 'int'>
	This is 4th index in the for loop, type of i is <class 'int'>
	This is 5th index in the for loop, type of i is <class 'int'>
	This is 6th index in the for loop, type of i is <class 'int'>
	This is 7th index in the for loop, type of i is <class 'int'>
	This is 8th index in the for loop, type of i is <class 'int'>
	This is 9th index in the for loop, type of i is <class 'int'>
	
WHATT!!

we can't use this functionality in `c` right. we'll get a `TypeError`
Python's liberal way of type checking allows this.

> If it walks like a duck, quacks like a duck and swims like a duck: it's a duck. 

This is the Zen of Python.

Why do we need `%<format-specifier>` anyway. we're not mortals.
Python-3 allows a new type of string formatting.


## Formatting Strings the python-3 way

	for i in range(10):
		print("This is the {}th index of the for loop".format(i))
	
	This is the 0th index of the for loop
	This is the 1th index of the for loop
	This is the 2th index of the for loop
	This is the 3th index of the for loop
	This is the 4th index of the for loop
	This is the 5th index of the for loop
	This is the 6th index of the for loop
	This is the 7th index of the for loop
	This is the 8th index of the for loop
	This is the 9th index of the for loop
	
we're not specifying what `i` is in the loop, we don't need to
This is actually a helpful feature in the dynamic way for python.

We don't have to know what type of duck `i` is to print it.

## F-String Formatting
F-Strings are python's new way of string formatting.

	for i in range(10):
		print(f"This is the {i}th index of the for loop.")
	
	This is the 0th index of the for loop.
	This is the 1th index of the for loop.
	This is the 2th index of the for loop.
	This is the 3th index of the for loop.
	This is the 4th index of the for loop.
	This is the 5th index of the for loop.
	This is the 6th index of the for loop.
	This is the 7th index of the for loop.
	This is the 8th index of the for loop.
	This is the 9th index of the for loop.
	
We became Captain America to Captain Marvel here. The above formatting is
so clean and smells good.

### What about `floor` truncating and other formatting options

What if we want to print only a `floor` value upto only two decimals.

	i = 0.0234
	print("%.3f is the value of i" %(i))
    
	output:
	0.023 is the value of i
	
python-3 way:

	print("{:.3f} is the value of i".format(i))
	
	output:
	0.023 is the value of i
	
f-string way:
	
	print(f"{i:.3f} is the value of i")
	
	output:
    0.023 is the value of i
	
one last example, if we want to print a number with trailing zeros, like:

    for i in range(10):
        print("%03d is the value of i" %(i))
        print("{:03d} is the value of i".format(i))
        print(f"{i:03d} is the value of i")

    output:
	000 is the value of i
	000 is the value of i
	000 is the value of i
	001 is the value of i
	001 is the value of i
	001 is the value of i
	002 is the value of i
	002 is the value of i
	002 is the value of i
	...



