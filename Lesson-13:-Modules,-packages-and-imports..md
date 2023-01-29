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
* **Simplicity** - When we divide our programs into modules, we are able to focus on smaller portions of the greater problem. This means we can put greater emphasis on ensuring the code we write works before we integrate it into the larger program. In other words, we can write tests that are more detailed and strict to test functionality that does less when we write modular code.
Also, the code is much easier to follow and read when it’s separated into parts that deal with specific parts of the functionality. If we used monolithic code instead, finding specific parts would become increasingly challenging as the number of lines we write grows — talk less of the size of the file.

* **Maintainability** - Large programs are usually built by multiple programmers who bring their skills together; When each module serves as a single source of truth for its functionality, we reduce the number of places bugs can arise in a program. This is because whenever we come across a bug in our code or a specific piece of functionality must be updated, changes only need to be done at the modular level rather than to the whole program — given we’ve checked the inter dependability criteria.
Not only does this make it easier to spot and rapidly fix these bugs, but it also encourages collaboration among teams. For example, responsibility for specific modules can be assigned to various members of the team, and though we’d still be nervous, there’s greater confidence that changes or updates we make won’t break the overall system.

* **Reusability** - the main gist is that we often reuse code in software development. Instead of copying and pasting that code, a better solution is to pull in the code required from a single source which is what modularity allows us to do.

## Modules

### Create

Creating a module in python is similar to writing a simple python script using the `.py` extension. For the example bellow, lets try to make a module for the various operations:

```python
def add(x: int,y: int) -> int:
     return x + y
 
def sub(x: int,y: int) -> int:
     return x - y
 
def prod(x: int,y: int) -> int:
    return x * y
 
def div(x: int,y: int) -> int:
    return x // y
```
Save the above code in a file `calc.py` (you can name it the way you want). _This is how we create a module in python_. We have created different functions in this module. We can use these modules in our main file.

### Usuage
We will use the **import** keyword to incorporate the module into our program, from keyword is used to get only a few or specific methods or functions from a module. Let us see what are different methods to use a module in your program. Let us say we have our file with a name main.py :

```python
import calc as calculator
a = 10
b = 20
 
addition = calculator.add(a,b)
print(addition)

# Output: 30
```

In the above code, we have created an alias using the **as** keyword. The output of the above code will be the addition of the two numbers a and b using the logic specified in the add function in the **calc.py** module.

Let us take a look at another approach. In the code below, we have **imported all the functions** using the asterisk and we can simply mention the function name to get the results.

```python
from calc import *
a = 20
b = 30
 
print(add(a,b))

# Output: 50
```
### Python Module Path
When we import a module, the interpreter looks for the module in the build-in modules directories in sys.path and if not found, it will look for the module in the following order:

```python
import sys 
print(sys.path)
```
When you run the above code, you will get the list of directories. You can make changes in the list to create your own path.

Built-in modules are written in C and integrated with python interpreter. Each built-in module contains resources for certain specific functionalities like Operating system management, disk input/output etc.

The standard library also has many python scripts containing useful utilities. There are several built-in modules in python at our disposal that we can use whenever we want.

To get the list of all the modules in python, you can write the following command in the python console:

```python
help('modules')
```

## `if __name__ == "__main__"` magic
For most practical purposes, you can think of the conditional block that you open with `if __name__ == "__main__"` as a way to store code that should only run when your file is executed as a script.

Example:
```python
# echo.py

def echo(text: str, repetitions: int = 3) -> str:
    """Imitate a real-world echo."""
    echoed_text = ""
    for i in range(repetitions, 0, -1):
        echoed_text += f"{text[-i:]}\n"
    return f"{echoed_text.lower()}."


if __name__ == "__main__":

    text = input("Yell something at a mountain: ")
    print(echo(text))
```
In this example, you define a function, echo(), that mimics a real-world echo by gradually printing fewer and fewer of the final letters of the input text.
When you run the file as a script by passing the file object to your Python interpreter, the expression `__name__ == "__main__"` returns `True`. The code block under if then runs, so Python collects user input and calls `echo()`.

**Remember:**
Nesting code under `if __name__ == "__main__"` allows you to cater to different use cases:
 * Script: When run as a script, your code prompts the user for input, calls echo(), and prints the result.
 * Module: When you import echo as a module, then echo() gets defined, but no code executes. You provide echo() to the main code session without any side 
   effects.


## Exercises: 

* Create a simple calculus program as a script and as module.
* Create a program with 3 different modules: 
  - first, to do basic tasks with strings
  - second, basic tasks with lists.
  - third, basic tasks with numbers

 Import them as modules to the `main.py` module and show calculations.

* Create a module and import any PIP package of your choice. Then create a function that would use it.
  Import that function to the `main.py` module and use it.


## 🌐  Extra reading (or watching 📺 ):

* [Python Official](https://docs.python.org/3/tutorial/modules.html)
* [Medium](https://medium.com/python-features/understanding-if-name-main-in-python-a37a3d4ab0c3)

***
