1. Calls & Definition, First Function 
1. Arguments, Intro to Types.
1. Return statement
1. Naming, Scope

### What is a function?
Functions are **a convenient way to divide your code into useful blocks, allowing us to order our code, make it more readable, reuse it and save some time**. Also functions are a key way to define interfaces so programmers can share their code.
In Python, you define a function with the _**def**_ keyword, then write the function identifier (name) followed by parentheses and a colon.
The next thing you have to do is make sure you indent with a tab or 4 spaces, and then specify what you want the function to do  for you.

```
def function_name():
    # What to make the function do
```
A simple example - functions that prints 'Hello world':

```
def print_smth():
    print('Hello world!')
```

Or prints random int number from 0 to 10:

```
def get_random_number():
    print(random.randit(0, 10))
```

### Naming, Scope

#### Naming:
Choosing names for your variables, functions and/or classes, and so forth can be challenging. You should put a fair amount of thought into your naming choices when writing code as it will make your code more readable. The best way to name your objects in Python is to use descriptive names to make it clear what the object represents.
Main rules as follows: 
* Use only lowercase in method names.
* An underscore should separate words in a method name.
* Non-public method name should begin with a single underscore.
* Use two consecutive underscores at the beginning of a method name, if it needs to be mangled.

A very good source of examples are here: [Python Function Naming](https://melevir.medium.com/python-functions-naming-tips-376f12549f9)