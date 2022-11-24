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
👨‍🏫  ❗ **Attention** ❗ 
**By default, all the variables and member functions of a class are public in a python program.**

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
👨‍🏫  ❗ **Good To Know** ❗ 
**Despite the fact that usage of  protected attributes are  limited 'on paper', soon you will see, that you can (but DONT!) use those as `public` attributes **

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

##  Four pillars of OOP
### Inheritance
`Inheritance` is the process by which one class inherits the properties of another class. This newly formed class is called a child class and the other class is called a parent class. It provides code reusability because we are using an existing class to increase the properties of a new class. A child class can access all the data members and functions of the parent class.

In Python, to inherit a class, we use `ChildClass(ParentClass)` at the time of defining the class: 🔽 

```python
class Employee:                     
    def __init__(self, name: str,age: int, exp: int, salary: int):                          ## Defining The Constructor With Common data
        ## Instance Attributes                                       ## instance attributes that are only accessible by the object of the class
        self.name = name                                              
        self.age = age
        self.exp = exp
        self.salary = salary

    def show(self) -> None:                                                   ## A Simple method that prints the data 
        print(self.name,self.age,self.exp,self.salary)                ## Printing all the variables


class Engineers(Employee):                                            ## Parent class Employee inherit by child Enginners

    def __init__(self, name: str,age: int, exp: int, salary: int, level: int):                     ## Constructor of Enginners class(child)
        super().__init__(name,age,exp,salary)                         ## accessing the parent class constructor and instance attributes with the help of super method
        self.level = level                                            ## Assigning a new attribute level for the Enginner class


    def print_data(self):                                             ## Creating a New Method for the Enginner class that is only accessable by the object of Enginner class
        print(self.level)                                             ## Printing the level of the Enginner



class Designers(Employee):                                           ## Parent class Employee inherit by child Designers

        def __init__(self,name,age,exp,salary,position):               
            super().__init__(name,age,exp,salary)                    
            self.position = position                                 ## Extending the attributes of parent class by adding a new attribute position
        
        def show(self):                                              ## A Simple Method Belong to the Designer Class that is used to print the data
            super().show()                                           ## Accessing parent class method and extending it to print the position also
            print(self.position)                                     ## Printing the position of the Designer


obj_E = Engineers("Alex",35,10,50000,'JR Developer')                ## Creating an object for the Enginners class, Need to paas arguments because It is a inherit class

obj_E.show()                                                        ## accessing parent method show with the help of the child class object
obj_E.print_data()                                                  ## accessing child class method debug, that is only access by the Designers object

obj_D = Designers("Karl",45,20,55000,"UI Designer")                 
obj_D.show()                                                        ## printing all the data 

'''
obj_E.debug()                                                       ## AttributeError: 'Engineers' object has no attribute 'debug'  ,debug is not a member of the Enginners class
Employee('Garry',35,10,50000).show()                                ## Garry 35 10 50000   ,because a class can access class attributes without the need of an object
obj = Employee('Garry',35,10,50000)
obj.debug()                                                         ## AttributeError: 'Employee' object has no attribute 'debug' , A parent can not access a child class
'''
```
At first, we have a parent class `Employee` that has some basic information: name, age, exp (experience), and salary. Employee class has a constructor that contains all the instance attributes. Lastly, we also have a method named show that only has a print statement and is used for printing the information.
Engineer and Designer both are the child classes of the parent class Employee.
The** `super()` method** helps a child class to access the members of the parent class. Engineers class accesses name, age, exp, and salary information from the parent class.

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
