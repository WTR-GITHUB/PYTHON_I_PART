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
Just like built-in functions, user-defined functions **are called using the function name followed by parenthesis** : 

```python
get_random_number() 
print_smth()
# and so on....

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

## Return statement 
Return statements are used to end a function while returning an expression that can be used later on. However, they are not mandatory and can be left out when unneeded.
Syntax:
```
return [expression]
```
👨‍🏫  ❗ **ATTENTION** ❗ 
**If [expression] is left empty, a None type object will be returned while exiting the function**


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

#### Some _easy-to-follow_ examples:

**Variable Annotations**:
To annotate types of variables, you start with the variable name and continue with the : finally, you provide the data type of the variable.

```python
type_annotation_int: int = 43
type_annotation_float: float = 2.54
type_annotation_string: str = 'efe'
type_annotation_bool: bool = True
```
You can also annotate more complex built-in data types like dicts, lists, and tuples. Before doing this, you need to import (we will learn in another lecture) the typing module.

```python
from typing import List, Tuple, Dicttype_annotation_tuple: Tuple[str] = ('1','2','3')
type_annotation_list: List[str] = ['a', 'b', 'c']
type_annotation_dict: Dict[str, int] = {'a': 1, 'b': 2}
```
**Combining Datatypes**:
If your variable or return type can have one of several different types, you can use Union for type annotation.

Pre-Python 3.10 implementation looks like this:

```python
from typing import List, Dict, Uniontype_annotation_list: List[Union[float,int]] = [1.23, 3.32, 1, 3]
type_annotation_dict: Dict[str, Union[float,int]] = {'a': 1, 'b': 2}
```
The annotation List[Union[float,int]] means that type_annotation_list variable should be a list where each element is either a floating-point or an integer.

With Python 3.10, you can replace Union with the new union operator | and you don't need to import anything from typing module:
```python
type_annotation_list: List[float | int]= [1.23, 3.32, 1, 3]
```
**Optional Operator**:
Optional[???] is short version of Union[???, None], which basically tells that either an object of the specific type is required, or None is required.
```python
type_annotation_list: List[Optional[int]] = [1, 3]
```
This implementation has changed with version 3.10: Optional can now be written as List [int | None]

**Function Annotations**:
As previous example, we saw how to add type hints to return type, arguments . Now more complex example:
```python
from typing import Tuple, Optional

def the_func(x: Union[int, float], y: Tuple[str, str], z: Optional[float] = None) -> str:
   return 'You called the_func with ' + str(x) + str(y) + str(z)
```
This example shows you that the_func() takes three arguments, x, y, and, z that x can be either an integer or float, y should be tuple storing strings and the z can be either none or float. The return type is str, which you specify using the -> after the ending parentheses but before the colon.
ℹ️ 

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
