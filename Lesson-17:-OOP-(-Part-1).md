1. Python is all about the objects
1. Class definition & initiation. 
1. ‘self ’ explained
1. First method.

## Introduction 
`OOP(object-oriented programing)` is a programming paradigm based on the concept of “objects”, which can contain data, in the form of fields, and code, in the form of procedures.

There are three words in the word Object-Oriented Programming.
The first is “Object” which means a thing that has existence. The second word is “Oriented”. If we look at this word Oriented, we can understand that the word Oriented is coming from Orient. Orient means to face or surround something. That means object-oriented means surrounding the object or using the object, and so the programming that is done around an object or with a lot of objects is called Object-Oriented Programming (OOP).

Objects are a representation of the real world objects like cars, dogs, bike, etc. The objects share two main characteristics: data and behavior.
Cars have data like number of wheels, number of doors, seating capacity and also have behavior: accelerate, stop, show how much fuel is missing and so many other.
We call data as attributes and behavior as methods in object oriented programming. Again:
`Data → Attributes & Behavior → Methods`

And a `Class` is the blueprint from which individual objects are created. In the real world we often find many objects with all the same type. Like cars. All the same make and model (have an engine, wheels, doors, …). Each car was built from the same set of blueprints and has the same components.

## What is a class?
A class is a **blueprint** for that object.
We can think of a class as a sketch (prototype) of a house. It contains all the details about the floors, doors, windows, etc. Based on these descriptions we build the house. House is the object.
As many houses can be made from a house’s blueprint, we can create many objects from a class. An object is also called an instance of a class and the process of creating this object is called **instantiation**.
Like function definitions begin with the def keyword in Python, class definitions begin with a class keyword:
```python
class Employee:
    age: int = 30
    designation: str = 'Manager'
    
  def greet(self) -> None:
      print('Hello')
```
We saw that the class object could be used to access different attributes.
It can also be used to create new object instances (instantiation) of that class. The procedure to create an object is similar to a function call.

```python
emp_obj = Employee()
```
This will create a new object instance named `emp_obj`. We can access the attributes of objects using the object name prefix.
Attributes may be data or method. Methods of an object are corresponding functions of that class.
This means to say, since **employee.greet** is a function object (_**attribute of class**_), employee.greet will be a method object.

## **self** keyword

## Exercises: 
🧠 : Repeat the [Data Structures (part 1)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-3:-Data-Structures-(Part-1)), [Data Structures (part 2)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-5:-Data-Structures-(Part-2)), [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops) to finish these task.
* Create at least 5 different functions and try to handle at least 5 built-in Python Exceptions.
* Create a function what would include full cycle of error handling (try/except/else/finally) with real world scenario example.
* Create a mini python program which would take two numbers as an input and would return their sum, subtraction, division, multiplication. Handle all possible errors that may occur.  
* Update previous task with possible `raise` exception.


## 🌐  Extra reading:

* [Type Annotations in Python 3.8](https://medium.com/analytics-vidhya/type-annotations-in-python-3-8-3b401384403d)

* [Real Phyton](https://realpython.com/defining-your-own-python-function/)

* [Real Python Youtube](https://www.youtube.com/watch?v=Q93bwyZoXk0)
***
