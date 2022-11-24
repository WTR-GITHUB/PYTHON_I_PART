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

## venv
A common way people used to create virtual environments was with a python package known as [virtualenv](https://virtualenv.pypa.io/en/latest/), but as of python version `3.3`, parts of `virtualenv` actually got built into python under the module name `venv`. You can now create a virtual environment with the following command:

```python
python3 -m venv <name_of_your_choice>
```
What’s going on here?

* Well, python3 is your installation of python. If the version of python you installed is called python, python3.7or python3.9 or anything else, then use that;
* `-m venv` is an argument that tells python to run the virtual environment module, `venv`;
*  The last `<name_of_your_choice>` is the name of your virtual environment folder. Some people like to use another name (e.g. env or .env), however, this is completely up to you.



👨‍🏫  ❗ **PRO TIP** ❗ 
** if you use `git`, you will want to add `venv/` to a new line of a `.gitignore` file to make sure you don’t version control your virtual environment. If you forget this step, _you can clog up_ your git repository with hundreds of additional version controlled files**


Once you have created your virtual environment, you won’t need to do this again.

#### Workflow
To use a virtual environment, you need to “activate” that environment with the following command:

(**on MacOS and Linux**)

```python
source <name_of_your_choice>/bin/activate
```

or (**Windows**)

```python
<name_of_your_choice>\Scripts\activate
```

What the above commands did was change the commands python and pip (pythons package manager) to refer to those located in the `venv` folder. A helpful indicator should appear that shows you are using your virtual environment like the following:

```python
(<name_of_your_choice>) $
```

This means that when you install a package with pip, e.g. with:

```python
pip install numpy
```

You will now install it in the virtual environment contained within your <name_of_your_choice> folder. If you like, you should be able to view the files of the packages you install in <name_of_your_choice>/lib/python3.9/site-packages . You will have to substitute python3.9 (or whatever version you use) for your version if this is different.

Example:
 
![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/venv.gif)

Continuing with this example, if you now start python in interactive mode, you will be able to access these packages using the following commands:

```python
python
import numpy as np
print(np.sqrt(5))
```
If everything went correctly, you should have seen something similar to the following:

![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/venv2.gif)

You should also be able to access any packages you install when using python to run your python files. For example if you wanted to use the python contained within your virtual environment to run a file called “main.py”, you could do that with the following command:

```python
python main.py
```

When you are done with your virtual environment, you can close the terminal or, alternatively, deactivate the environment with the command as follows:
```python
deactivate
```
This will also now let you activate a different virtual environment for another one of your projects if you need to.

#### Reproducing your environment
You can reproduce a python virtual environment (e.g. on another machine), you will commonly want to save the packages you install to a file. This will let anyone with your file, install the same version of packages that you used when developing your project. You will however likely still want to tell them what version of python you are using. Commonly people like to use a file called `requirements.txt` for this purpose.

If you have activated your python virtual environment, you can automatically generate a requirements.txt file with the following:

```python
pip freeze > requirements.txt
```
So if you or someone else wanted to create a virtual environment and use the same packages as you did, they can follow along with the above commands to create and activate a virtual environment and then, install your requirements. Installation of requirements is possible using the -r method of pip as follows:

```python
pip install -r requirements.txt
```

## Pipenv
Using `pipenv` has several advantages compared to using `pip` and `venv`. These are the main ones:
* You no longer need to use pip and venv separately. Instead, you have one tool that does it all — and more!
* `pipenv` separates your top-level dependencies from the last tested combination (e.g., _the output of pip freeze_). This makes dependency management more user-friendly for you as a developer.
* `pipenv` encourages the use of the latest versions of dependencies to minimize security risks. It can even scan your dependencies for known vulnerabilities.
* `pipenv` gives insight into your dependency graph with `pipenv graph`.
*  `pipenv` [hashes](https://www.educative.io/answers/what-is-hashing) all dependencies. It will detect packages that have been tampered with after you initially included them as a dependency.
* `pipenv` can work with `requirements.txt` files too. If there is one, it will automatically detect it and convert it into a `Pipfile`.

#### Workflow 
Pipenv is a third-party package, so first you’ll need to _install it_:

```python
pip install pipenv
```
Then you can change into your product directory (or create a new directory if you’re starting a new project, as I’m doing here), and _instantiate_ `pipenv` there:

```python
mkdir ~/dev/projects/my-new-project && cd ~/dev/projects/my-new-project
pipenv install
```
This will create two new files, a Pipfile and a Pipfile.lock.

To _enable_ virtual environment:

```python
$ pipenv shell
```
To _install packages_ with `pipenv`:


```python
pipenv install <package name>
```

_Listing packages_ in your environment:

```python
pipenv lock -r
```
To _show which packages you have installed (and the dependencies of those dependencies)_ you can run:

```python
pipenv graph
```

_Uninstalling Packages:_

```python
pipenv uninstall <package name>
```

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
