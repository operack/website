---
title: "Pythonic Wonders: Chapter 4 - Lists and Tuples"
author: mdomocos
date: 2023-03-26 09:04:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: true
mermaid: true
---
### Intro

In Python, lists and tuples are used to store collections of items. Lists are mutable, which means their contents can be changed, while tuples are immutable, which means their contents cannot be changed once they are created.

## Creating and Modifying Lists

To create a list, simply enclose a comma-separated sequence of values in square brackets:

```python
fruits = ["apple", "banana", "cherry"]
```

To add an item to a list, you can use the `append()` method:

```python
fruits.append("orange")
```

To remove an item from a list, you can use the `remove()` method:

```python
fruits.remove("banana")
```

## Indexing and Slicing

You can access individual elements of a list using their index. In Python, indexing starts at 0. For example:

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0]) # prints "apple"
```

You can also slice a list to get a range of elements. The syntax for slicing is `list[start:end:step]`. For example:

```python
fruits = ["apple", "banana", "cherry", "orange", "kiwi"]
print(fruits[1:3]) # prints ["banana", "cherry"]
```

## List Methods

Lists have several built-in methods for performing common operations. Here are a few examples:

- `len(list)`: returns the number of items in the list
- `list.count(item)`: returns the number of times `item` appears in the list
- `list.sort()`: sorts the items in the list in ascending order
- `list.reverse()`: reverses the order of the items in the list

For a complete list of list methods, check out the [Python documentation](https://docs.python.org/3/tutorial/datastructures.html#more-on-lists).

## Tuples and Their Uses

A tuple is similar to a list, but it is immutable, which means its contents cannot be changed once it is created. Tuples are often used to represent fixed collections of items, such as the x and y coordinates of a point.

To create a tuple, simply enclose a comma-separated sequence of values in parentheses:

```python
point = (3, 4)
```

To access the elements of a tuple, you can use indexing or unpacking:

```python
x, y = point
print(x) # prints 3
```

Tuples also support all the same slicing operations as lists.
