1. Modules, libraries
1. Imports, Path parameter.
1. If __name__ == `__main__` magic.

## Introduction
While you learn to program in Python, it may make sense to write all of your code in Python’s Integrated Development and Learning Environment (IDLE). After a while this becomes impractical. The most natural upgrade from there is to begin creating your own Python source files that are used to save your code — Python source files are stored with the .py extension.

In these source files, you can define various functions, classes, and other objects, as well as exactly what you want the program to do when you run the code. Since the file is saved, you don’t have to rewrite your code each time you want to give some instructions to the Python interpreter: you simply run the script you wrote in the past.

However, storing all of your code in a single source file is impractical as you begin to build more complex programs. Tracking all of the functions and classes and how the codes fit together becomes more and more challenging as the complexity of the program increases. Even those with the greatest memories can only remember so much, so we have to build our programs in a way that makes life easier for us.
This is where **_modular programming_** comes into play.

#### Introducing modular programming
Python programmers leverage modular programming to build various applications. Modular programming is simply a way of structuring programs as their complexity increases. It focuses on breaking down large tasks into small subtasks that are easier to manage.

Joining the smaller subtasks together forms an application; In Python, we refer to each individual subtask as a module which is really an umbrella term for reusable code. Modules are stored with the .py extension and imported into various other programs.

When we have several modules then the collection is called a package. A package can be thought of as a folder that contains modules and possibly other folders that contain modules [and so on]. Thus, a package is simply a name used to bind all of the modules inside it together so we can reference it in the future when we want to use that code in another program.

Some benefits of modular programming are:
* Simplicity - When we divide our programs into modules, we are able to focus on smaller portions of the greater problem. This means we can put greater emphasis on ensuring the code we write works before we integrate it into the larger program. In other words, we can write tests that are more detailed and strict to test functionality that does less when we write modular code.
Also, the code is much easier to follow and read when it’s separated into parts that deal with specific parts of the functionality. If we used monolithic code instead, finding specific parts would become increasingly challenging as the number of lines we write grows — talk less of the size of the file.

* Maintainability - Large programs are usually built by multiple programmers who bring their skills together; When each module serves as a single source of truth for its functionality, we reduce the number of places bugs can arise in a program. This is because whenever we come across a bug in our code or a specific piece of functionality must be updated, changes only need to be done at the modular level rather than to the whole program — given we’ve checked the inter dependability criteria.
Not only does this make it easier to spot and rapidly fix these bugs, but it also encourages collaboration among teams. For example, responsibility for specific modules can be assigned to various members of the team, and though we’d still be nervous, there’s greater confidence that changes or updates we make won’t break the overall system.

* Reusability - the main gist is that we often reuse code in software development. Instead of copying and pasting that code, a better solution is to pull in the code required from a single source which is what modularity allows us to do.


👨‍🏫  ❗ **PRO TIP** ❗ 
**As per normal functions, you can assign default arguments to self parameters and instant method arguments**

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
