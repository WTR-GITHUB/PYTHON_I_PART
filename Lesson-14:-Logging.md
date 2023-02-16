## Logging library

Logging is a very useful tool in a programmer’s toolbox. It can help you develop a better understanding of the flow of a program and discover scenarios that you might not even have thought of while developing.

By logging useful data from the right places, you can not only debug errors easily but also use the data to analyze the performance of the application to plan for scaling or look at usage patterns to plan for marketing.

The [logging module](https://docs.python.org/3/library/logging.html) in Python is a ready-to-use and powerful module that is designed to meet the needs of beginners as well as enterprise teams. It is used by most of the third-party Python libraries, so you can integrate your log messages with the ones from those libraries to produce a homogeneous log for your application.

### Import the library:
`import logging`

### Logging vs Print Statement
`Logging` and `Print` both can be used to debug the code but still, there are reasons for you to choose `log` over `print()`.

A `Log file` contains a log message with other information such as line number, module name, date, time, etc. On the other hand, a `print` statement only has a log message.

A `Log file` will save the records of the application even after it is closed but a print statement will lose out all the records and log message just after the execution stops.

The only time when you should consider using a `print()` statement over a `log` is when you need to display a help statement on the command line.

### Logging
There are five ways we can display a log message in python with setting log levels: **DEBUG**, **INFO**, **WARNING**, **ERROR**, and **CRITICAL**.

```python
import logging

logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')

-------------------OUTPUT---------------------
WARNING:root:This is a warning message
ERROR:root:This is an error message
CRITICAL:root:This is a critical message
```
In the code output above, there are two things to notice:

- The **root** is the default logger for all the logs.
- There are only three log messages printed. The reason behind this is the **severity level of log messages** and messages higher than or equal to the severity level of `WARNING` will only get printed.

### The Five Levels of Logging
    - **DEBUG**: It is used for diagnosing the problem. It gives a piece of detailed information about the problem. The severity level is 10.
    - **INFO**: It gives the confirmation message of the successful execution of the program. The severity level is 20.
    - **WARNING**: The message is for when an unexpected situation occurs. The severity level is 30.
    - **ERROR**: It is due to a more serious problem than a warning. It can be due to some inbuilt error Like syntax or logical error. The severity level is 40.
    - **CRITICAL**: It occurs when the program execution stops and it can not run itself anymore. The severity level is 50.


## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):

* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
