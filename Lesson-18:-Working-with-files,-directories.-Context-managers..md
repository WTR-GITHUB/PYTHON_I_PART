1. ‘with’ statement. 
1. Working with text files. 
## Introduction 
Python is a very convenient tool to handle files.
File handling is nothing but a combination of various operations performed on the files such as opening the file, reading the file, and writing the file, etc.
There are generally two types of files: text file and binary file.

A `text file` stores the textual information, for example, any message saying “Hello World” and saved as `.txt` extension, while images are stored in the form of `binary` numbers such as 0’s or 1’s and saved as `.bin` extension.

## File Operations
The main operations you will be performing on files are:
* Create
* Read
* Update
* Delete

In programming jargon - **CRUD** operations.

However, do note that there are many other operations that can be performed with the files as well. Such as, copying a file or changing the properties of the file and filter.
All of these operations are important to manipulate the file. This manipulation ensures that the file operations can be performed as per the exact requirement of the user working on the file.

The workflow ⏬ 

![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/crud%20workflow.png)

## CRUD operations

### Create & Read
We use ```open()``` method to open a file, and the second parameter defines which mode we will enter after opening it:

```python
my_file = open('test_file.txt', 'r')
```
The default value of second parameter is `r` which represents `read` mode to read text files. For reading binary files, we use `rb`.
If the file doesn’t exist, there will be a `FileNotFoundError` .

The file must be closed after use, because the file object will occupy the resources of the operating system, and the number of files that the operating system can open at the same time is also limited.

```f.close()```python

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
