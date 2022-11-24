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

#### Types of access modes
* **r** mode: If we mention this mode, the file will be open in reading format only. The cursor will be at the start of the file.
* **w** mode: If we mention this mode, the file will be open in write format only to overwrite the file content. If the file is not in the working location, then it will create the file first and write the content in it.
* **r+** mode: In this mode, the file will be open in both read and write mode.
* **w+** mode: In this mode, it opens the file and overwrites the content.
* **wb** mode: File opens in writing mode with the binary format.
* **a** mode: This mode is for appending the content in the file. The cursor is at the last end of the content to add something to the file.
* **x** mode: This mode will create a file, returns an error if the file exist


👨‍🏫  ❗ **PRO TIP** ❗ 
**To create a new file in Python, use the same `open()` method, with one of the following parameters: `x`, `a`, `w`.**

The file must be closed after use, because the file object will occupy the resources of the operating system, and the number of files that the operating system can open at the same time is also limited.

```python
f.close()
```
👨‍🏫  ❗ **ATTENTION** ❗ 
**Sometimes we could forget to close a file after use and could cause unexpected bugs. Therefore, we can use `try..finally` block :**
```python
try:
    f = open('test_file.txt', 'r')
    print(f.read())
except Exception as e:
  # log the error
finally:
    if f:
        f.close()
```
But the code looks a little fussy if we always do this when open a file. Actually, the best way to open a file in Python is to use `with` statement:

```python
with open('test_file.txt', 'r') as f:
    print(f.read())
```
Thus, `with` statement helps avoiding bugs and leaks by ensuring that a resource is properly released when the code using the resource is completely executed.

The `open()` function return a file object. A Python file object has 3 reading methods, which gives us enough flexibility to get the contents:

* **read()** : read the entire file and save the contents to a Python string variable. Sometimes a file is larger than the available memory, in order to be safe, we can use the parameter n to read n characters each time: read(n). The default value of n is -1, which means read the whole file.
* **readlines()** is also to read entire file, but it will automatically analyses the file contents and convert them into a list of lines, which makes it convenient to deal with the contents as a list of strings.
* **readline()** reads only one line of the file contents each time.

```python

```
## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***