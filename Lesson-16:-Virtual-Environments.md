## Introduction 
To understand what a virtual environment really is and how can it make our lives easier let’s look at some things which you might encounter while developing a simple python project.

A python project might have dependencies on several 3rd party libraries to achieve your business goal. You can manage all these additional packages/dependencies using the python package manager called `pip`.

To check your pip version you can do:

```python
python3 -m pip --version
```
You can install a package by using the install command in pip:
```python
python -m pip install <package-name>
```
`pip` always installs the **latest version of any package** by default (until a specific version of that package is provided) and will also **install any dependencies** that the required package has.

## The Catch
Lets say, you develope a project `Project A` which runs on python 3.5 [version](https://www.python.org/doc/versions/) ,and you also start working on another python project `Project B` which requires on python 3.9 .

Both `Project A` and `Project B` might need a library `lib A` to achieve their goals but `Project A` which is running on python 3.5 might be compatible with a different version of `lib A` while `Project B` (python 3.9) might be compatible with some other version (example: [Flask](https://pypi.org/project/Flask/#history)).

Even if your multiple projects are using the same python version, a case may arise when updating a dependency version (example: [The same Flask](https://flask.palletsprojects.com/en/2.2.x/installation/) ) for any of your new project might break the functionality an existing one.

Since by default every project on your system will write and consume 3rd party packages from the same directory this poses a challenge as it **can break the functionality for either of your projects**.

## Virtual Environments 
The official documentation from [Python](https://docs.python.org/) says:

_A virtual environment is a Python environment such that the Python interpreter, libraries and scripts installed into it are isolated from those installed in other virtual environments, and (by default) any libraries installed in a “system” Python, i.e., one which is installed as part of your operating system._

The definition above is simple enough to understand that a `virtual environment` is just offering you an isolated place for managing dependencies of a project such that they **do not interfere with libraries installed in any other virtual environment or installed on your system**.

You can simply create a virtual environment for every project that you work on.
We will discuss two very popular virtual environment managers: [venv](https://docs.python.org/3/library/venv.html) and [Pipenv](https://pipenv.pypa.io/en/latest/)

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
