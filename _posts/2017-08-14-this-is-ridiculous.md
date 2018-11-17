---
layout: post
title:  "a,b = b, a # This is ridiculous"
date:   2017-08-14
image: /assets/images/vintage.jpg
---

An Informal Introduction to Python Programming Language.

This tutorial is further divided into two main parts:

    Introduction to Python
    Introduction to html


Let's learn some basics of Python first

    The first thing to learn about python is that everything is an object.
    There is no such thing as primitive data type in python.
    Indentation is a must - I'll tell you what indentation is, further.
    No semicolons
    No need of main function for execution of the program


Indentation:

"Leading white space (spaces and tabs) at the beginning of a logical line is used to compute the indentation level of the line, which in turn is used to determine the grouping of statements."

Indentation seperates blocks of code and helps to understand the code written. Python design engineers thus made indentation compulsory for writing python code. A good way of indentation is four white spaces. we'll gather around indentation when we learn more topics.

Declare Yourself out : variables in python

As I mentioned earlier, Everything in python is an object. So if we write

string is an object. Note that no semicolons are needed in python. Syntactically, its looks cleaner
The above statement is a string declaration. It tells the python interpreter to assign "This is a string" to string. So whenever we want "This is a string" we will ask string variable for that.


Here, integer_number and decimal_number are also objects. decimal_numbers in computer jargon are called floating point numbers.

Let's test some warm waters and dive deep into datatypes specifically in python.

    lists
    dictionaries
    tuples


list is nothing but an array of similar datatypes like strings and floats.
dictionary is data structure which has two things

    a key
    a value

if you want to access a value, you need to put the key to it
tuple is data structure same as list except that is immutable - which means we can't change the values in the tuple once declared.

Let's not get lost in this forest and quickly see how these are declared in python

The next question is how to convert one to another. if a string is in the form "123" how do we convert it to number 123.
Now here's why python is awesome. In order to do that all we need is this single piece of code.

Here we are instructing python to convert the string to a number variable by using keyword int

Points to remember:

    number is just a variable name. python understands the value assigned to number variable is an integer.


The output will be "456". here we used the keyword str
Note that:

    print is the in-built function in python - to print the given thing obviously.


Its time to take some decisions : conditionals
conditionals in python are basically divided as

    simple if
    if .. else
    Nested if


simple if

if .. else

Nested if

okay, That was too much let's break them down and understand each and every one of them.

    if statement is a condition and only execute when the statement is true
    number > 1 gives the boolean value of true or false
    if then executes the below statement according to the boolean value


Points to remember and duly noted : ## This is important

    Note that # do something is 4 spaces away from the above if statement
    This is intentional
    This is indentation
    If you don't give indentation python interpreter throws IndentationError : expected an indented block
    The colon after the condition is compulsory
    No brackets are required as in C for python to execute the conditionals.



    Here we use indentation even if C does not require it because others have to understand what you write, The other may be you after three months. You don't want to pull you hair out looking at the code that you wrote a while ago.
    else if in C is compressed as elif
    There's no switch case as in C for python.


Rinse and Repeat : Looping constructs:

There are basically two looping constructs in python unlike three that we know:

    for loop
    while loop

A properly structured while loop acts like a do .. while
Let us quickly go through both of them

for loop:


while loop:

Note :

    Indentation under while and for is compulsory
    The colon at the end of for and while
    the weird print(i, end=' ') basically gives the output in the same line.
    there is no i++ in python
    for loop is used when the number of iterations to be followed is known to us in advance
    while loop is used when the number of iterations is not known.
    The boolean values in python are True, False
    range in the for loop goes through the specified order given as parameters


range function has parameters as following:

    start
    end
    increment


functions in python:


as everything is an object in python we don't need to specify what is going to returned while defining a function. If we want to explicitly specify it. we can do so. we'll learn more about functions in the future.

if you are wondering why the post name is a , b = b , a.
It is how two values are swapped in python.

isn't it ridiculous. That's why I say python is simple.

The picture in the front is Alan Turing. search for him and find out more.

This was a long post sorry for that, bear with me for the next one.
In the part - 2 of this introduction post I'll discuss some html.
I'll make it as small as possible

Say hi to me at : vinaybommana7@gmail.com
