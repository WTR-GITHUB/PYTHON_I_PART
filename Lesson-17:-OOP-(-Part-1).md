1. Python is all about the objects
1. Class definition & initiation. 
1. ‘self ’ explained
1. First method.

## Introduction 
Object-oriented programming (OOP) is a method of structuring a program by bundling related properties and behaviors into individual objects. 
Conceptually, objects are like the components of a system. Think of a program as a factory assembly line of sorts. At each step of the assembly line a system component processes some material, ultimately transforming raw material into a finished product.
An object contains data, like the raw or preprocessed materials at each step on an assembly line, and behavior, like the action each assembly line component performs.
Object-oriented programming is a [programming paradigm](http://en.wikipedia.org/wiki/Programming_paradigm) that provides a means of structuring programs so that properties and behaviors are bundled into individual objects.

For instance, an object could represent a person with properties like a name, age, and address and behaviors such as walking, talking, breathing, and running. Or it could represent an email with properties like a recipient list, subject, and body and behaviors like adding attachments and sending.

Put another way, object-oriented programming is an approach for modeling concrete, real-world things, like cars, as well as relations between things, like companies and employees, students and teachers, and so on. OOP models real-world entities as software objects that have some data associated with them and can perform certain functions.

## What is a class?
A class is a **blueprint** for that object.
We can think of a class as a sketch (prototype) of a house. It contains all the details about the floors, doors, windows, etc. Based on these descriptions we build the house. House is the object.
As many houses can be made from a house’s blueprint, we can create many objects from a class. An object is also called an instance of a class and the process of creating this object is called **instantiation**.
Like function definitions begin with the def keyword in Python, class definitions begin with a `class` keyword:

```python
class House:
    pass
```
This creates a new `House` class with no attributes or methods.
Creating a new object from a class is called **instantiating** an object. You can instantiate a new `House` object by typing the name of the class, followed by opening and closing parentheses:

```python
>>> House()
<__main__.House object at 0x105248e40>

```
You now have a new `House` object at 0x106702d30. This funny-looking string of letters and numbers is a memory address that indicates where the House object is stored in your computer’s memory. Note that the address you see on your screen will be different.

Now instantiate a second `House` object:

```python
>>> House()
<__main__.House object at 0x0034ccd70>
```
The new `House` instance is located at a different memory address. That’s because it’s an entirely new instance and is completely unique from the first House object that you instantiated.
We easily can compare both object instances:
```python
>>> a = House()
>>> b = House()
>>> a == b
False

```
### Class Constructor (```.__init__()```)

The `House` class isn’t very interesting right now, so let’s spruce it up a bit by defining some properties that all `House` objects should have. There are a number of properties that we can choose from, including cost, age, color, and number of bedrooms. To keep things simple, we’ll just use cost and age.
The properties that all House objects must have are defined in a method called ```.__init__()```. Every time a new House object is created, ```.__init__()``` sets the initial state of the object by assigning the values of the object’s properties. That is, ** ```.__init__()``` initializes each new instance of the class**.

You can give ```.__init__()``` any number of parameters, but the first parameter will always be a variable called self. When a new class instance is created, the instance is automatically passed to the self parameter in ```.__init__()``` so that new attributes can be defined on the object.

Let’s update the House class with an ```.__init__()``` method that creates .cost and .age attributes:

```python
class House:
    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age

```
Notice that the ```.__init__()``` method’s signature is indented four spaces. The body of the method is indented by eight spaces. **This indentation is vitally important**. It tells Python that the ```.__init__()``` method belongs to the House class.

In the body of ```.__init__()```, there are two statements using the self variable:

self.cost = name creates an attribute called `cost` and assigns to it the value of the `cost` parameter.

self.age = age creates an attribute called `age` and assigns to it the value of the `age` parameter.

### Class & Instance attributes

Attributes created in ```.__init__()``` are called** instance attributes**. An instance attribute’s **value is specific to a particular instance of the class**. All House objects have a cost and an age, but the values for the cost and age attributes will vary depending on the **House instance**.

On the other hand, **class attributes** are attributes that have the same value for all class instances. You can define a class attribute by assigning a value to a variable name outside of ``.__init__()``.

For example:

```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age

```


## **self** keyword
The self is used to represent the instance of the class.
With this keyword, you can access the attributes and methods of the class in python. It binds the attributes with the given arguments.

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
