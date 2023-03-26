---
title: "Pythonic Wonders: Chapter 8 - Object-Oriented Programming"
author: mdomocos
date: 2023-03-26 09:08:00 +0200
categories: [Courses, Python]
tags: [operack, python, course]
math: true
mermaid: true
---
## Intro
Object-oriented programming (OOP) is a programming paradigm that uses objects to represent and manipulate data. In Python, everything is an object. Understanding OOP is important for writing complex programs and creating reusable code. This chapter will cover the following topics:

## Classes and objects
A class is a blueprint for creating objects, and an object is an instance of a class. In Python, classes are defined using the `class` keyword. Objects can have attributes (data) and methods (functions).

Example:
```python
class Car:
    def __init__(self, make, model, year):
        self.make = make
        self.model = model
        self.year = year

    def description(self):
        return f"{self.year} {self.make} {self.model}"

my_car = Car("Toyota", "Corolla", 2020)
print(my_car.description())  # Output: "2020 Toyota Corolla"
```

## Methods and attributes
Methods are functions that are associated with a class or an object, and attributes are data stored in an object or a class. In Python, methods are defined like functions, but they are associated with a class or an object using the dot notation.

Example:
```python
class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

    def perimeter(self):
        return 2 * (self.length + self.width)

my_rect = Rectangle(5, 3)
print(my_rect.area())       # Output: 15
print(my_rect.perimeter())  # Output: 16
```

## Inheritance and polymorphism
Inheritance is a mechanism for creating a new class that is a modified version of an existing class. The new class inherits the properties and methods of the existing class. Polymorphism is the ability of an object to take on many forms. In Python, polymorphism is achieved through inheritance and method overriding.


Example:
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def sound(self):
        pass

class Cat(Animal):
    def sound(self):
        return "Meow"

class Dog(Animal):
    def sound(self):
        return "Woof"

my_cat = Cat("Tom")
my_dog = Dog("Spike")
print(my_cat.sound())  # Output: "Meow"
print(my_dog.sound())  # Output: "Woof"
```

## Encapsulation and data hiding
Encapsulation is the concept of binding data and methods together within a class, and data hiding is the concept of restricting access to certain data and methods. In Python, data hiding is achieved through name mangling.

Example:
```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance

    def deposit(self, amount):
        self.__balance += amount

    def withdraw(self, amount):
        if amount <= self.__balance:
            self.__balance -= amount
        else:
            print("Insufficient balance")

    def get_balance(self):
        return self.__balance

my_account = BankAccount(1000)
my_account.deposit(500)
print(my_account.get_balance())  # Output: 1500
my_account.withdraw(2000)        # Output: "Insufficient balance"
```
