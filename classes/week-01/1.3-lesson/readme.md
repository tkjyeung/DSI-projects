---
title: Intro to Python 1
duration: "1:5"
creator:
    name: Lucy Williams
    city: DC
modified:
    name: Luiz Pizzato & Wee Kiang Yeo
    city: HK    
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Intro to Python: Datatypes

Week 1 | Lesson 1.3 ..

### LEARNING OBJECTIVES
*After this lesson, you will be able to:*
- Define integers, strings, tuples, lists, and dictionaries
- Demonstrate arithmetic operations and string operations
- Demonstrate variable assignment ..

### PROGRESS CHECK
- Yesterday: Git and Github
- Tomorrow: Intro to Python

### STUDENT PRE-WORK
*Before this lesson, you should already be able to:*
- Describe/define Python data types ..

### LESSON GUIDE

| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Introduction](#introduction)   | Python Data Types  |
| 10 min  | [Practice](#demo1)  | Integers  |
| 10 min  | [Practice](#demo2) | Strings  |
| 10 min  | [Practice](#demo3)  | Tuples  |
| 10 min  | [Practice](#demo4) | Lists  |
| 10 min  | [Practice](#demo5) | Dictionaries  |
| 10 min  | [Practice](#demo6)  | Arithmetic operations and String operations  |
| 10 min  | [Independent Practice](#ind-practice)  | Pair Practice  |
| 5 min  | [Conclusion](#conclusion)  | Conclusion | ..

### ALTERNATE LESSON GUIDE

Some students might already know Python quite well so we are offering this _optional_ code challenge to warm-up on while we go over Python fundamentals with the rest of the class.

| TIMING  | TYPE  | TOPIC  |
|:-:|---|---|
| 5 min  | [Introduction](#introduction)   | Challenge  |
| 70 min  | [Code Challenge #1](code/starter-code/Alternate%20Code%20Challenges%20-%20Week%201%20Lesson%201.2.ipynb)  | Intense Coding  |
| 5 min  | [Conclusion](#conclusion)  |  Challenge Conclusion |

---

<a name="introduction"></a>
## Introduction: Python Data Types (5 mins) ..

#### Integers

whole numbers from negative _infinity_ to positive _infinity_, such as: 1, 0, -5 ..

#### Floats

short for "floating point number," any rational number, usually used with decimals such as 2.8 or 3.14159 ..

#### Strings

a set of letters, numbers, or other characters.
```python
"This is not a sentence."
```
 ..

#### Tuples
a list with a fixed number of elements. i.e. (1,2,3) parentheses makes it a tuple.
```python
("Red", "Blue", "Green")
```
 ..

#### Lists
a list without a fixed number of elements. i.e. [1,2,3] note the square brackets, a list
```python
["The", "secret", "of", "life", "is"]
```
 ..

#### Dictionaries
a type with multiple elements i.e. {1: 'a','b': 2,3: 3} where you address the elements with, e.g., a text.
```python
{'username':'zuckerberg', 'password':'dadada'}
```
 ..

See [Python Basic data types](https://en.wikiversity.org/wiki/Python/Basic_data_types)

---

<a name="demo"></a>
## Demo / Guided Practice: Integers (10 min) ..

#### Integers
Integers are numeric values and can be stored, manipulated, and expressed inside variables without quotes.
In iPython notebook type:
```python
23
```
and it returns:
```python
23
```
 ..

In iPython notebook type:
```python
-44
```
and it returns:
```python
-44
```
 ..

You can also perform basic math using integers as well. In iPython notebook type:
```python
45-19
```
and it returns:
```python
26
```

---


## Demo / Guided Practice: Strings (10 min) ..

#### Strings
Strings are a type. They are the basic unit of text in Python and all the other types except integers may contain strings.
In iPython notebook type:
```python
"I love yum cha"
```
and it returns:
```python
"do you really?"
```
 ..

 nope, that's wrong... checking if anyone noticed ..


You can also make a variable refer to a string. In iPython notebook type:
```python
x = "The playwright is a weird Carribean pharao with a handkerchief."
```
Now type:
```python
x
```
and it returns:
```python
"The playwright is a weird Carribean pharao with a handkerchief."
```
 ..

Now type:
```python
print(x)
```
and it returns:
```bash
The playwright is a weird Carribean pharao with a handkerchief.
```

> The print command prints the value that 'x' stands for on the screen. It removes the quotations. Whenever you type something into a type that isn't an integer, syntax (the commands that you give python, such as print), or variable (such as x just was) you need to put it into quotations. You can use 'single' or "double" quotations.

---

## Demo / Guided Practice: Tuples (10 min) ..

#### Tuples

A tuple is an unchangeable sequence of values.
When you typed ('I love yum cha') you only included one element.

In iPython notebook type:
```python
x = ("Red", "Blue", "Green")
```

When you do this you create a tuple with three elements. You can access these elements individually by typing the variable and the then inside brackets directly to the right of the variable type the number of the element to which you are referring ..

Now type:
```python
print(x[1])
```
and it returns:
```python
Blue
```

You may think that it is odd that it returned element 2 instead of element 1. The reason that it did this is because Python starts numbering at 0. element 1 = 0, element 2= 1, element 3= 2. You can also call on the elements in reverse order ..

Now type:
```python
print(x[-1])
```
and it returns:
```python
Green
```
 ..

#### My pet peeve

Overuse of index access on tuples.
Ex.
```python
 rgb_color = (40, 20, 220)
```

This is the color: <spam style="background-color: #2814DC; color: #2814DC">XXX</spam>

Do this:
```python
 red, green, blue = rgb_color
 _, green, _ = rgb_color
```

Don't do this:
```python
 red = rgb_color[0]
 green = rgb_color[1]
 blue = rgb_color[2]
```

---

## Demo / Guided Practice: Lists (10 min) ..

#### Lists
A list is a changeable sequence of data. A list is contained by square brackets i.e. [1,2,3]

In iPython notebook type:

```python
x = ["I", "drink", "black", "tea", "with", "milk"]
x[1] = "hate"
x[3] = "coffee"
x[5] = "sugar"
print(x)
```
 ..

and it returns:
```python
["I", "hate", "black", "coffee", "with", "sugar"]
```

The code above changes elements number 1, 3, and 5 in x

---

## Demo / Guided Practice: Dictionaries (10 min) ..

#### Dictionaries

Dictionaries contain a key and a value. { } enclose dictionaries (Note, that you can also construct a set with curly brackets.
The first input in a dictionary pair is the 'key'. The second input in a dictionary pair is the 'value'.

The general format looks like this:
* key1:value1 ..

In iPython notebook type:
```python
x = {'key1':'value1', 'key2':'value2'}
print(x)
```

These may not be in the exact order in which you typed them. The reason for the different order is because dictionaries have no order. You cannot type x[0] and be referring to 'key1':'value1' ..

What you do to refer to a value is type the key

In iPython notebook type:
```python
x["key1"] = "I love Python"
print(x)
```

and it returns:
```python
{'key2': 'value2', 'key1': 'I love Python'}
```

The keys stay the same but the values are changeable ..

You can also only have one occurrence of a key in a dictionary, but you may have the values all be the same.

Now type:
```python
x = {'key':'value1', 'key':'value2'}
print(x)
```

and it returns:
```python
{'key': 'value2'}
```

The first key is overwritten by the second ..

Now type:
```python
x = {'key1':'value', 'key2':'value'}
print(x)
```

and it returns:
```python
{'key2': 'value', 'key1': 'value'}
```

This example shows that you can create two separate keys with the same value ..

#### Some links:

[Integers, Strings, Tuples, Lists, Dictionaries](https://en.wikiversity.org/wiki/Python/Basic_data_types) ..
[Dictionaries](http://sthurlow.com/python/lesson06/) ..

#### Check

- Define/describe: integer, string, tuple, list, dictionary

- () are used for tuples, lists, or dictionaries?
- [] are used for tuples, lists, or dictionaries?
- {} are used for tuples, lists, or dictionaries?

---

<a name="demo"></a>
## Demo / Guided Practice: arithmetic operations and string operations (20 mins) ..

#### Simple Math

Math is very straightforward in Python.

Basic operations are:
- addition: `5+2`
- subtraction: `5-2`
- multiplication: `5*2`
- division: `5/2`
  - > Note on division: In Python 2.7 the expression `5/2` is an integer multiplication and it returns the integer `1`. For it to behave like Python 3 where "/" represents a float division, then the following import is needed "from __future__ import division"  ..

Other operations:
- modulus: `5//2`
  - returns the integer component of the division (5/2 is 2)
- modulus: `5%2`
  - returns the remainder of an integer division (5%2 is 1) ..

In iPython notebook type:
```python
9 % 3
```

and it returns:
```python
0
```

Now type:
```python
9 % 2
```

and it returns:
```python
1
```
 ..

You can also use variables, and elements and values in simple arithmetic.
In iPython notebook type:
```python
x = 1
y = 5
x + y
```

and it returns:
```python
6
```
That is how the variable works ..


Now type:
```python
x = [1, 2, 3]
x[1] + x[2]
```

and it returns:
```python
5
```

This is how you use elements from a list to perform arithmetic operations. It should be clarified that x[0] = 1, x[1] = 2, and x[2] = 3. You can also add and multiply strings, tuples, and lists ..

In iPython notebook type:
```python
x = {'a':1, 'b':2}
x['a'] + x['b']
```

and it returns:
```python
3
```
That is how you do arithmetic with values from a dictionary. Don't forget to use quotations around the keys unless you use integers as the keys. Spend a couple of minutes messing around with this stuff, its fun and it'll help you remember it better. You may also add strings, tuples, and lists ..


**Check:** What does % do? ..

#### Concatenating

To add two strings together - to do this you just type the first string, an addition sign, the second string.

In iPython notebook type:
```python
"Learning Python" + " is awesome"
```

and it returns:
```python
'Learning Python is awesome'
```
 ..

You can do the same with variables referring to strings.
In iPython notebook type:
```python
x = "Learning Python"
y = " is awesome"
x + y
```

and it returns:
```python
'Learning Python is awesome'
```
 ..

You can do the same with tuples.

In iPython notebook type:
```python
x = ('I', 'love')
y = ('gluing things together',)
print(x + y)
```

and it returns:
```python
('I', 'love', 'gluing things together)
```

It works the same with lists. What you cannot do is combine two different kinds of types ..

#### Multiplying types
Multiplying is very easy and straight forward.

In iPython notebook type:
```python
x = 'buffalo '
x * 8
```

and it returns:
```python
'buffalo buffalo buffalo buffalo buffalo buffalo buffalo buffalo '
```
 ..

Now, try it with a tuple.

In iPython notebook type:
```python
x = ('buffalo buffalo',)
x * 4
```

and it returns:
```python
('buffalo buffalo',
 'buffalo buffalo',
 'buffalo buffalo',
 'buffalo buffalo')
```
 ..

Can we do the same with a dictionary? ..

You cannot do the same with dictionaries; that would make multiple keys with the same entry name, which isn't valid in Python.

In iPython notebook type:
```python
x = {'buffalo buffalo':1}
x * 4
```

and it returns:
```python
TypeError                                 Traceback (most recent call last)
<ipython-input-16-f25efe1807bd> in <module>()
      1 x = {'buffalo buffalo':1}
----> 2 x * 5

TypeError: unsupported operand type(s) for *: 'dict' and 'int'
```
 ..


#### Indexing
You have already learned how to index in lesson 2. When you typed x[3] you were indexing. You may also index a string without first making a variable represent it.
In iPython notebook type:
```python
"abcdefghijklmnopqrstuvwxyz"[5]
```

and it returns:
```python
'f'
```
 ..

#### Slicing
Slicing is used to access a range of elements the way that indexing accesses one element.
In iPython notebook type:
```python
x = "Together John and Mary will conquer the world."
print(x[18:45])
```

and it returns:
```python
'Mary will conquer the world'
```
The numbers that you enter after the variable (the [18:45]) are called indices ..

[arithmetic operations and string operations](https://en.wikiversity.org/wiki/Python/Basic_data_types) ..

**Check:** What is concatenating? indexing? slicing?

---

<a name="ind-practice"></a>
## Independent Practice: (10 minutes)
Pair up, make up your own statements and see if your partner can tell you what will be returned BEFORE running it.

---

<a name="conclusion"></a>
## Conclusion (5 mins)
Let's check to see if we know what we learned about today:
- Define integers, strings, tuples, lists, and dictionaries
- Demonstrate arithmetic operations and string operations
- Demonstrate variable assignment
