1. OOP principles: Polymorphism
1. OOP principles: Encapsulation and Abstraction Explained.
1. Static method.

## Introduction 
As we already know, Python is an Object-Oriented Programming language. Everything in Python is an object. Like other Object-Oriented languages, when creating objects using classes, there are 4 basic principles for writing clean and concise code. These principles are called the **four pillars of object-oriented programming (OOP)**. These four pillars are:  **Inheritance, Polymorphism, Encapsulation and Abstraction.** 

### Why OOP?
A few to name:
* It makes it so much easier to maintain and update existing code.
* Provides code reusability.
* Provides a modular structure.
* It is easy to debug.

## Access modifiers
In most of the object-oriented languages access modifiers are used to limit the access to the variables and functions of a class. Most of the languages use three types of access modifiers, they are - private, public and protected.

Just like any other [object oriented programming language](https://en.wikipedia.org/wiki/List_of_object-oriented_programming_languages), access to variables or functions can also be limited in python using the access modifiers. Python makes the use of `underscores` to specify the access modifier for a specific data member and member function in a class.

Access modifiers play an **important role to protect the data from unauthorized access as well as protecting it from getting manipulated**. When inheritance (look at the following chapter ⬇️ ) is implemented there is a huge risk for the data to get destroyed(manipulated) due to transfer of unwanted data from the parent class to the child class. Therefore, it is very important to provide the right access modifiers for different data members and member functions depending upon the requirements.
There are 3 types of access modifiers for a class in Python. These access modifiers define how the members of the class can be accessed. 
These are:

* Public - the members declared as Public are accessible from outside the Class through an object of the class.
* Protected - the members declared as Protected are accessible from outside the class but only in a class derived from it that is in the child or subclass.
* Private - these members are only accessible from within the class. No outside Access is allowed.

_Public_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self.name = name # Public attribute
        self.sal = sal

---- OUTPUT ----
>>> emp = Employee("Ironman", 999000);
>>> emp.sal
999000
```
_Protected_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self._name = name # Protected attribute
        self._sal = sal # Protected attribute

---- OUTPUT ----
>>> emp = Employee("Captain", 10000);
>>> emp.sal
10000
```
_Private_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self.__name = name # Private attribute
        self.__sal = sal # Private attribute

---- OUTPUT ----
>>> emp = Employee("Bill", 10000);
>>> emp.__sal;

AttributeError: 'employee' object has no attribute '__sal'

```


👨‍🏫  ❗ **Attention** ❗ 
**By default, all the variables and member functions of a class are public in a python program.**

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
