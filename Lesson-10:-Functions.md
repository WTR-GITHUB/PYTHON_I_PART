1. Calls & Definition, First Function 
1. Arguments, Intro to Types.
1. Return statement

## Introduction 
What is a function?
Functions are **a convenient way to divide your code into useful blocks, allowing us to order our code, make it more readable, reuse it and save some time**. Also functions are a key way to define interfaces so programmers can share their code.
In Python, you define a function with the _**def**_ keyword, then write the function identifier (name) followed by parentheses and a colon.
The next thing you have to do is make sure you indent with a tab or 4 spaces, and then specify what you want the function to do  for you.

```python
def function_name():
    # What to make the function do
```
A simple example - functions that prints 'Hello world':

```python
def print_smth():
    print('Hello world!')
```

Or prints random `int` number from 0 to 10:

```python
def get_random_number():
    print(random.randit(0, 10))
```

## Naming

Choosing names for your variables, functions and/or classes, and so forth can be challenging. You should put a fair amount of thought into your naming choices when writing code as it will make your code more readable. The best way to name your objects in Python is to use descriptive names to make it clear what the object represents.
Main rules as follows: 
* Use only lowercase in method names.
```python
def compute():
  pass
```
* An underscore should separate words in a method name.
```python
def calculate_smth():
  pass
```
* Non-public method name should begin with a single underscore.
```python
def _get_smth():
  pass
```
* Use two consecutive underscores at the beginning of a method name, if it needs to be mangled.
```python
def __get_secret():
  pass
```

A very good source of naming rules and examples are here: [Python Function Naming](https://melevir.medium.com/python-functions-naming-tips-376f12549f9) ❗ **Must be read!** ❗

## ℹ️ Short Intro to Type Hints
Type hints, also known as `type annotations`, are completely optional in Python. Yet, there are huge benefits of using them in your code.
The type term used in Python refers to the object type. Objects are mainly things containing data and the functions act on that data. As an example; an integer object in python can store integer values and you can perform some tasks with that object, such as doing arithmetic calculations.

Objects have strict types. You cannot store a string value in an integer object type as this is not allowed in that specific type. But names we use in our code can point to any object type. You have to spend some time reviewing the code to understand how a specific name can be used if object types are not clearly annotated. This will be a more obvious problem if you have a complex code base.

Type hints are introduced with Python 3.5 to address this difficulty.
A simple example of the function which add two numbers (without `type hints`):

```python
def add_two_int_numbers(a,b):
  return a + b
```

And with `type hints`: 

```python
def add_two_int_numbers(a: int, b: int) -> int:
  return a + b
```
### Why do you need to use type hints? 
* Statically typed languages require you to define the types of objects and they can catch errors before run-time. Python is a dynamically typed language and does not force you to do this. This flexibility comes at a cost. When your code base increased, it can be cumbersome to solve runtime TypeErrors if you don’t define the types with type hints.
* You need to consider using type hints to help others and yourself. Type hints increase the readability with self-explanatory code.
* Type hints also help you to build and maintain a cleaner code architecture as you need to consider types when annotating them in your code.

## Exercises: 
🧠 : Repeat the [Data Structures (part 1)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-3:-Data-Structures-(Part-1)), [Data Structures (part 2)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-5:-Data-Structures-(Part-2)), [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops) to finish these task.
* Create at least 5 different functions and try to handle at least 5 built-in Python Exceptions.
* Create a function what would include full cycle of error handling (try/except/else/finally) with real world scenario example.
* Create a mini python program which would take two numbers as an input and would return their sum, subtraction, division, multiplication. Handle all possible errors that may occur.  
* Update previous task with possible `raise` exception.


## 🌐  Extra reading:

* [Official Python Website](https://docs.python.org/3/tutorial/errors.html)

* [Real Phyton](https://realpython.com/python-exceptions/)

* [Dataquest](https://www.dataquest.io/blog/python-exceptions/)
***
