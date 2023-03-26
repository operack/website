---
title: "Pythonic Wonders: Chapter 3 - Functions and Modules"
author: mdomocos
date: 2023-03-26 09:03:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: true
mermaid: true
---
### Intro

Functions and modules are essential tools for building complex programs in Python. Functions allow you to break up your code into reusable pieces, while modules enable you to organize your code into separate files.

#### Functions

A function is a block of code that performs a specific task. Functions can take input arguments and return output values. Here's an example of a simple function:

```python
def greet(name):
    print(f"Hello, {name}!")

greet("Alice")
```

In this example, the program defines a function called `greet` that takes a `name` argument and prints a personalized greeting.

Functions can also return values using the `return` keyword. Here's an example:

```python
def square(x):
    return x ** 2

result = square(3)
print(result)
```

In this example, the program defines a function called `square` that takes a number `x` and returns its square.

#### Modules

A module is a file containing Python code that can be imported into another program. Modules enable you to organize your code into separate files and reuse code across multiple programs.

Here's an example of a simple module:

```python
# mymodule.py

def greet(name):
    print(f"Hello, {name}!")

def square(x):
    return x ** 2
```

In this example, the program defines a module called `mymodule` that contains two functions: `greet` and `square`.

You can use the `import` keyword to import a module into your program. Here's an example:

```python
import mymodule

mymodule.greet("Alice")
result = mymodule.square(3)
print(result)
```

In this example, the program imports the `mymodule` module and uses its `greet` and `square` functions.

#### Standard Library

Python also comes with a standard library of modules that provide additional functionality. You can use the `import` keyword to import these modules into your program. Here's an example:

```python
import math

result = math.sqrt(9)
print(result)
```

In this example, the program imports the `math` module and uses its `sqrt` function to calculate the square root of 9.
