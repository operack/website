---
title: "Pythonic Wonders: Chapter 7 - File Input and Output"
author: mdomocos
date: 2023-03-26 09:07:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: false
mermaid: false
---
### Intro
Files are a common way to store data in computer systems, and Python provides a powerful set of tools for working with files. We'll learn how to read from and write to files, handle errors and exceptions, and work with different file formats. Whether you're working with text files, binary files, or CSV files, this chapter will give you the skills you need to manipulate them in Python.
## Reading and Writing to Files
Python allows us to read and write data to and from files. Reading data from a file is a way to extract data from an external source, while writing data to a file is a way to save data for later use. In Python, we can read and write files using built-in functions like open(), close(), read(), readline(), and write().
Example:
```python
# writing data to a file
with open('my_file.txt', 'w') as file:
    file.write('Hello, World!')

# reading data from a file
with open('my_file.txt', 'r') as file:
    data = file.read()
    print(data)
```

## Context Managers
A context manager is a Python object that provides a way to manage resources such as files, sockets, and locks. The main advantage of using a context manager is that it automatically takes care of releasing the resources after use, even if an error occurs.

Example:

```python
# using a context manager to open a file
with open('my_file.txt', 'r') as file:
    data = file.read()
    print(data)
```

## File Modes
In Python, we can specify the mode in which we want to open a file using a second argument to the open() function. The available modes are:

- 'r' : read-only mode
- 'w' : write mode
- 'a' : append mode
- 'x' : exclusive creation mode

Example:
```python
# opening a file in write mode
with open('my_file.txt', 'w') as file:
    file.write('Hello, World!')
```

## Handling Exceptions
When working with files, it is important to handle exceptions properly. Errors can occur if a file is not found, if there are permission issues, or if there are other problems with the file. In Python, we can use a try-except block to catch and handle exceptions that may occur.

Example:
```python
# handling exceptions when reading from a file
try:
    with open('my_file.txt', 'r') as file:
        data = file.read()
except FileNotFoundError:
    print('File not found!')
except PermissionError:
    print('Permission denied!')
except Exception as e:
    print(f'Error: {e}')
```
