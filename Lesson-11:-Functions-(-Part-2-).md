## Continue
One of the powerful yet less popular feature of Python are the *args and the **kwargs arguments, lambda function.

## *args, **kwargs
So, what are the `*args` and `**kwargs` arguments? On a high level, they allow functions to _accept optional arguments_ providing us with the flexibility to call a function with any number of arguments. Therefore, using them allows us to write more flexible classes and modules.

A simple example : 🔽 

```python
def check_arguments(mandatory: any, *args, **kwargs) -> None:
    print (mandatory)
    if args:
        print (args)
    if kwargs:
        print (kwargs)
```

Above function `check_arguments` requires at least one argument called “mandatory” but it can accept extra positional and keyword arguments as well.
If we call the function with additional arguments, `args` will collect extra _positional arguments_ as a **tuple** because the parameter name has a * prefix.

Likewise, `kwargs` will collect extra keyword arguments **as a dictionary** because the parameter name has a ** prefix. Both `args` and `kwargs` will be empty if no extra arguments are passed to the function.
Let’s invoke our `check_arguments` method with different arguments to understand the `args` and `kwargs` behaviour:

```python
>>> check_arguments():
TypeError:
"check_arguments() missing 1 required positional arg: 'mandatory'"
>>> check_arguments('welcome')
welcome

>>> check_arguments('welcome', 1, 2, 3)
welcome
(1, 2, 3)

>>> toy_fun('welcome', 1, 2, 3, name='Sarah', age=26)
welcome
(1, 2, 3)
{'name': 'Sarah', 'age': 26}
```
👨‍🏫  ❗ **GOOD TO KNOW** ❗ 
** `args` and `kwargs` is simple a naming convention. Above example would work just fine if we called them `*parms` and `**argv` or anything for that matter. Actual syntax is just the asterisk (*) or double asterisk (**).**

👨‍🏫  ❗ **ATTENTION!** ❗ 
** While using `*args` or `**kwargs` with other parameters or using them together, we should keep in mind that the arguments should follow the given order ⬇️ .**

1. **Formal arguments**
1. ***args**
1. **keyword arguments**
1. ****kwargs**

```python
def my_func(a:int, b:int, *args, c: int = 5, d: int = 9, **kwargs) -> None:
    print (a, b)
    print (type(args), args)
    print (c, d)
    print (type(kwargs), kwargs)

>>> my_func(1, 2, 3, 4, 5, e=6, f = 7)
1, 2
<class 'tuple'> (3, 4, 5)
5, 9
<class 'dict'> {'e': 6, 'f': 7}
```
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
