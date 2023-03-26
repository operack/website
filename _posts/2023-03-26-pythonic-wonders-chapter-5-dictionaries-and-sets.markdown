---
title: "Pythonic Wonders: Chapter 5 - Dictionaries and Sets"
author: mdomocos
date: 2023-03-26 09:05:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: false
mermaid: false
---
### Intro
Dictionaries are used to store key-value pairs, allowing for efficient lookup of values based on their associated keys. Sets, on the other hand, are collections of unique and unordered elements that can be used for various purposes such as membership testing, removing duplicates, and mathematical operations.
## Creating and Modifying Dictionaries
A dictionary is a collection of key-value pairs. You can create an empty dictionary or a dictionary with values in it. Here are examples:

```python
empty_dict = {}
nonempty_dict = {"key1": "value1", "key2": "value2", "key3": "value3"}
```

To add a key-value pair to a dictionary, simply assign a value to a new key, like this:

```python
nonempty_dict["key4"] = "value4"
```

To modify an existing key-value pair, simply assign a new value to that key, like this:

```python
nonempty_dict["key3"] = "new_value3"
```

## Dictionary Methods
Dictionaries have several methods for manipulating and accessing data. Here are a few examples:

```python
nonempty_dict.keys()      # Returns a list of all keys in the dictionary
nonempty_dict.values()    # Returns a list of all values in the dictionary
nonempty_dict.items()     # Returns a list of all key-value pairs in the dictionary
nonempty_dict.get(key)    # Returns the value associated with the given key, or None if the key is not present
```

## Set Operations and Methods
A set is an unordered collection of unique elements. You can create an empty set or a set with values in it. Here are examples:

```python
empty_set = set()
nonempty_set = {1, 2, 3, 4}
```

To add an element to a set, use the add() method, like this:

```python
nonempty_set.add(5)
```

To remove an element from a set, use the remove() method, like this:

```python
nonempty_set.remove(3)
```

Sets have several methods for manipulating and accessing data. Here are a few examples:

```python
nonempty_set.union(other_set)          # Returns the union of two sets
nonempty_set.intersection(other_set)   # Returns the intersection of two sets
nonempty_set.difference(other_set)     # Returns the difference between two sets
```

## Combining Data Types
You can combine different data types to create complex data structures. Here's an example:

```python
my_dict = {"name": "Alice", "age": 30, "hobbies": ["reading", "swimming", "cooking"]}
```

In this example, we have a dictionary with a string key and values of different data types. The "hobbies" value is a list of strings, which is itself a data type. By combining data types like this, you can create powerful and flexible data structures for your programs.
