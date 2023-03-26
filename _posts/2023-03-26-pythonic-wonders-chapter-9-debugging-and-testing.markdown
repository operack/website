---
title: "Pythonic Wonders: Chapter 9 - Debugging and Testing"
author: mdomocos
date: 2023-03-26 09:09:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: false
mermaid: false
---
## Intro
Debugging and testing are crucial parts of software development. Debugging is the process of finding and fixing errors, while testing is the process of verifying that the program meets the requirements and works as expected. In this chapter, we will cover some of the common techniques and tools used for debugging and testing in Python.

#### Debugging techniques
Debugging can be a time-consuming process, but there are several techniques that can make it easier and more efficient. Some of these techniques are:

- Using print statements: This is one of the simplest and most effective debugging techniques. By adding print statements to your code, you can see the value of variables and the flow of execution at different points in the program.

- Debugging with a debugger: A debugger is a tool that allows you to step through your code and see what is happening at each step. Python comes with a built-in debugger called pdb.

- Using logging: Logging is a technique that allows you to record the flow of execution and the values of variables in a log file. This can be useful for debugging complex programs or programs that run for a long time.

#### Using print statements
Here is an example of using print statements for debugging:

```python
def calculate_sum(a, b):
    print("a =", a)
    print("b =", b)
    result = a + b
    print("result =", result)
    return result

print(calculate_sum(2, 3))
```

When you run this code, you will see the following output:

```python
a = 2
b = 3
result = 5
5
```

This shows that the function is working correctly and returning the expected result.

#### Debugging with a debugger
Here is an example of using the pdb debugger for debugging:

```python
import pdb

def calculate_sum(a, b):
    pdb.set_trace()
    result = a + b
    return result

print(calculate_sum(2, 3))
```

When you run this code, the program will pause at the `pdb.set_trace()` line and drop you into the debugger. From there, you can step through the code one line at a time, examine the values of variables, and make changes as necessary.

#### Using logging
Here is an example of using logging for debugging:

```python
import logging

logging.basicConfig(filename='example.log', level=logging.DEBUG)

def calculate_sum(a, b):
    logging.debug('a = %s, b = %s' % (a, b))
    result = a + b
    logging.debug('result = %s' % result)
    return result

print(calculate_sum(2, 3))
```

This code will write the flow of execution and the values of variables to a log file called `example.log`. You can then examine this log file to see what happened during the execution of the program.

#### Debugging tools
In addition to the techniques described above, there are several debugging tools available for Python. Some of the most popular ones are:

- PyCharm: PyCharm is an IDE that comes with a built-in debugger and many other features for Python development.

- Pdb: Pdb is the built-in debugger in Python.

- IPython: IPython is an interactive shell for Python that includes many debugging features.

- WingIDE: WingIDE is a commercial IDE for Python that includes a powerful debugger and many other features.

#### Unit testing and test-driven development
Unit testing is the process of testing individual components or units of a software system to ensure that each unit is functioning correctly. The purpose of unit testing is to validate that each unit of the software performs as expected before it is integrated into the system as a whole. Test-driven development (TDD) is a software development methodology that emphasizes writing tests before writing the code. With TDD, tests are written first to define the desired functionality, and then the code is written to pass the tests.

There are several Python frameworks for writing and running unit tests, including unittest, nose, and pytest. The unittest framework is included in the Python standard library, making it a good choice for simple projects. Nose and pytest are more feature-rich and flexible, and are popular choices for more complex projects.

Here is an example of a simple unittest test case:

```python
import unittest

def add(a, b):
    return a + b

class TestAdd(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
        self.assertEqual(add(0, 0), 0)
        self.assertEqual(add(-1, 1), 0)
```
In this example, we define a simple function add that takes two numbers and returns their sum. We also define a test case TestAdd that inherits from the unittest.TestCase class. Inside the TestAdd class, we define a test method test_add that checks if the add function returns the expected results for several input values using the assertEqual method.

To run this test case, we can use the following code:

```python
if __name__ == '__main__':
    unittest.main()
```

This will run all the test cases defined in the file.

Here is an example of a simple pytest test case:

```python
def add(a, b):
    return a + b

def test_add():
    assert add(2, 3) == 5
    assert add(0, 0) == 0
    assert add(-1, 1) == 0
```
In this example, we define the same add function as in the previous example, and we define a test function test_add that uses the assert statement to check if the add function returns the expected results for several input values.

To run this test case, we can use the following command:
```shell
$ pytest
```
This will run all the test functions defined in the file.

Test-driven development (TDD) is a software development methodology that emphasizes writing tests before writing the code. With TDD, tests are written first to define the desired functionality, and then the code is written to pass the tests. The TDD process typically consists of the following steps:

Write a test that describes the desired functionality.
Run the test and verify that it fails.
Write the minimum amount of code necessary to pass the test.
Run the test and verify that it passes.
Refactor the code to improve its design while keeping the tests passing.
Here is an example of using TDD to implement a simple function that calculates the factorial of a number:

```python
import unittest

def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

class TestFactorial(unittest.TestCase):
    def test_factorial(self):
        self.assertEqual(factorial(5), 120)
        self.assertEqual(factorial(0), 1)
        self.assertEqual(factorial(1), 1)
        self.assertEqual(factorial(10), 3628800)

if __name__ == '__main__':
    unittest.main()
```
In this example, we have a function factorial that takes an integer n and returns the factorial of n. We also have a TestFactorial class that inherits from the unittest.TestCase class.

Within the TestFactorial class, we define a method called test_factorial that contains several assertions. Each assertion tests the output of the factorial function for a different input value.

We use the unittest.main() function to run the tests. When we run the script, we will see a report that tells us whether all the tests passed or if any of them failed.

This is just a simple example, but unit testing can be incredibly powerful in ensuring that our code works as expected and catching bugs early in the development process.
