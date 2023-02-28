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


## **Self** keyword
The self is used to represent the instance of the class.
With this keyword, you can access the attributes and methods of the class in python. **It binds the attributes with the given arguments**.

👨‍🏫  ❗ **GOOD TO KNOW** ❗ 
** `Self` is nothing more than a convention: the name `self` has absolutely no special meaning to Python. Note, however, that by not following the convention your code may be less readable to other Python programmers.**

## Instance methods
**Instance methods** are functions that are defined inside a class and can only be called from an instance of that class. Just like ```.__init__()```, an instance method’s first parameter is always `self`:

```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age
    
    # Instance method
    def get_cost(self) -> int:
        return f"The house cost is:{self.cost}"

    # Another instance method
    def get_age(self) -> float:
        return f"The house age is:{self.age}"

```
This House class has **two instance methods**:

* get_cost() -  returns an `int` displaying the `cost` of the house.
* get_age() -  returns a `float` displaying the `age` of the house.

Lets initiate the class and call some methods:
```python
>>> house = Dog(100000, 12.5)

>>> house.get_cost()
'The house cost is: 100000'

>>> house.get_age()
'The house age is: 12.5'

```
👨‍🏫  ❗ **PRO TIP** ❗ 
**As per normal functions, you can assign default arguments to self parameters and instant method arguments**
```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int = 50000, age: float= 10.5):
        self.cost: int = cost
        self.age: float = age
    
    # Instance method
    def get_cost(self) -> int:
        return f"The house cost is:{self.cost}"

    # Another instance method
    def get_age(self) -> float:
        return f"The house age is:{self.age}"

    # Yet another instance method
    def get_house_colour(self, colour: string = 'White') -> string:
        return f"The house colour is:{self.age}"


```

```python
>>> house = Dog(100000, 12.5)

>>> house.get_cost()
'The house cost is: 100000'

>>> house.get_age()
'The house age is: 12.5'

>>> house.get_house_colour('Blue')
'The house colour is: Blue'

>>> another_house = Dog()

>>> another_house.get_cost()
'The house cost is: 50000'

>>> another_house.get_age()
'The house age is: 10.5'

>>> house.get_house_colour()
'The house colour is: White'
```

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.
* Create the instance attributes fullname and email in the Employee class. Given a person's first and last names:
   - Form the fullname by simply joining the first and last name together, separated by a space.
   - Form the email by joining the first and last name together with a . in between, and follow it with @company.com at the end. Make sure the entire 
     email is in lowercase.

* Create a Book class that has two attributes:
    - title
    - author

  and two methods:

    - A method named .get_title() that returns: "Title: " + the instance title.
    - A method named .get_author() that returns: "Author: " + the instance author.

  and instantiate this class by creating 3 new books:

    - Pride and Prejudice - Jane Austen (PP)
    - Hamlet - William Shakespeare (H)
    - War and Peace - Leo Tolstoy (WP)

  The name of the new instances should be PP, H, and WP, respectively. For instance, if I instantiated the following book using this Book class:

    - Harry Potter - J.K. Rowling (HP)

  I would get the following attributes and methods:
  ```python
  HP.title ➞ "Harry Potter"
  HP.author ➞ "J.K. Rowling"
  HP.get_title() ➞ "Title: Harry Potter"
  HP.get_author() ➞ "Author: J.K. Rowling"
  ```

* A country can be said as being big if it is:

   - Big in terms of population.
   - Big in terms of area.

  Add to the Country class so that it contains the attribute is_big. Set it to True if either criterea are met:

   - Population is greater than 20 million.
   - Area is larger than 3 million square km.

  Also, create a method which compares a country's population density to another country object. Return a string in the following format:
  
  ```python
  {country} has a {smaller / larger} population density than {other_country}
  ```
  Examples:
  
  ```python
  australia = Country("Australia", 23545500, 7692024)
  andorra = Country("Andorra", 76098, 468)

  australia.is_big ➞ True
  andorra.is_big ➞ False
  andorra.compare_pd(australia) ➞ "Andorra has a larger population density than Australia"
  ```

## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
