---
title: "Pythonic Wonders: Chapter 2 - Control Flow and Loops"
author: mdomocos
date: 2023-03-26 09:02:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: true
mermaid: true
---
### Intro

Control flow statements are used to control the flow of a program, while loops are used to repeat a section of code multiple times.

#### Conditional Statements

Conditional statements are used to execute different parts of code based on whether a certain condition is true or false. In Python, conditional statements are created using the `if`, `elif`, and `else` keywords.

Here's an example of a simple conditional statement:

```python
x = 5

if x > 0:
    print("x is positive")
elif x == 0:
    print("x is zero")
else:
    print("x is negative")
```

In this example, the program checks whether `x` is greater than zero, equal to zero, or less than zero, and prints a corresponding message.

#### Loops

Loops are used to repeat a section of code multiple times. In Python, there are two types of loops: `for` loops and `while` loops.

##### For Loops

For loops are used to iterate over a sequence of values. Here's an example of a simple for loop:

```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

In this example, the program iterates over a list of fruits and prints each one.

##### While Loops

While loops are used to repeat a section of code while a certain condition is true. Here's an example of a simple while loop:

```python
x = 0

while x < 10:
    print(x)
    x += 1
```

In this example, the program prints the value of `x` and increments it by 1 until `x` is greater than or equal to 10.

#### Control Flow Keywords

Python has several keywords that can be used to control the flow of a program, including `break`, `continue`, and `pass`.

- The `break` keyword is used to exit a loop prematurely.

- The `continue` keyword is used to skip over
