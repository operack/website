---
title: "Pythonic Wonders: Chapter 6 - String Manipulation"
author: mdomocos
date: 2023-03-26 09:06:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: false
mermaid: false
---
### Intro

In this chapter, you will learn about string operations and methods, regular expressions, and string formatting.

#### String Operations and Methods

Strings in Python are a sequence of characters, and there are many operations and methods that can be applied to them. Some of the most commonly used ones include:

- `len()`: returns the length of the string.
- `+`: concatenates two strings.
- `*`: repeats a string a certain number of times.
- `in`/`not in`: checks if a substring is present or not.
- `.lower()`: converts a string to lowercase.
- `.upper()`: converts a string to uppercase.
- `.strip()`: removes whitespace from the beginning and end of a string.
- `.replace()`: replaces a substring with another.

Here's an example that demonstrates some of these operations:

```python
str1 = "Hello"
str2 = "World"
str3 = str1 + " " + str2
print(str3)    # Output: "Hello World"
print(str1*3)  # Output: "HelloHelloHello"
print("lo" in str2)     # Output: True
print(str1.lower())     # Output: "hello"
print(str2.strip("ld")) # Output: "Wor"

```

#### Regular Expressions

Regular expressions are a powerful tool for working with strings. They are a way to match patterns in text using special syntax. The `re` module in Python provides support for regular expressions.

Here's an example that demonstrates how to use regular expressions to match a pattern:

```python
import re

string = "The quick brown fox jumps over the lazy dog."
pattern = r"fox"

match = re.search(pattern, string)
if match:
    print("Pattern found in string.")
else:
    print("Pattern not found in string.")
```

#### String Formatting

String formatting allows you to create formatted strings by substituting values into a string. There are several ways to format strings in Python, including using the `%` operator, the `format()` method, and f-strings.

Here's an example that demonstrates how to use f-strings:

```python
name = "Alice"
age = 25

print(f"My name is {name} and I am {age} years old.")
```

This will output: `My name is Alice and I am 25 years old.`
