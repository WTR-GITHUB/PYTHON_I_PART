1. Calls & Definition, First Function 
1. Arguments, Intro to Types.
1. Return statement
1. Naming, Scope

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
* Non-public method name should begin with a single underscore.
* Use two consecutive underscores at the beginning of a method name, if it needs to be mangled.

A very good source of examples are here: [Python Function Naming](https://melevir.medium.com/python-functions-naming-tips-376f12549f9)

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
