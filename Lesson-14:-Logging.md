## Logging library

Logging is a very useful tool in a programmer’s toolbox. It can help you develop a better understanding of the flow of a program and discover scenarios that you might not even have thought of while developing.

By logging useful data from the right places, you can not only debug errors easily but also use the data to analyze the performance of the application to plan for scaling or look at usage patterns to plan for marketing.

The [logging module](https://docs.python.org/3/library/logging.html) in Python is a ready-to-use and powerful module that is designed to meet the needs of beginners as well as enterprise teams. It is used by most of the third-party Python libraries, so you can integrate your log messages with the ones from those libraries to produce a homogeneous log for your application.

### Import the library:
`import logging`

### Severity levels
The _logger_ has five standard logging levels:

*     DEBUG
*     INFO
*     WARNING
*     ERROR
*     CRITICAL

**DEBUG** -  Detailed information, typically of interest only when diagnosing problems.

**INFO** -  Confirmation that things are working as expected.

**WARNING** -  An indication that something unexpected happened, or indicative of some problem in the near future (e.g. ‘disk space low’). The software is still working as expected.

**ERROR** -  Due to a more serious problem, the software has not been able to perform some function.

**CRITICAL** -  A serious error, indicating that the program itself may be unable to continue running.
 
A good example of logging in _action_ with different logging levels: (Note! - The default level of logging library is **WARNING**)

```
import logging

logging.basicConfig(level=logging.DEBUG)
logging.debug('Logging the event')

------ OUTCOME -------------
DEBUG:root:Logging th event

```

```
import logging

logging.basicConfig(level=logging.INFO)
logging.debug('Logging the event')

-------------------------CONSOLE OUTPUT------------------
INFO:root:Logging th event

```
We can Print the DEBUG and INFO message too by changing the basic configuration of the logger with the help of basicConfig(**kwargs)
There are some parameters that are commonly used in this —

* _**level**_: To change the root logger to a specified severity level.
* `**filename**`: Filename where the logs going to be stored.
* `**filemod**`e: If a filename is given then this specifies the file mode in which the file will open. default is append (a )
* `**format**`: This is the format of the log message.
* `**datefmt**` : It specified the date and time format.

```
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%d/%m/%Y %H:%M:%S')
logging.debug('This is Debug Message')
logging.info('This is an info message')
-------------------------CONSOLE OUTPUT------------------
12/05/2021 20:46:41 - root - DEBUG - This is Debug Message
12/05/2021 20:46:41 - root - INFO - This is an info message
```

## Exercises: 
🧠 : Repeat the [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Functions](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) to finish these task.
* Create a `Calculator` class with main functionality: add, divide, multiply, subtract , etc.. Initiate class and show up some calculations.


## 🌐  Extra reading (or watching 📺 ):


* [Full OOP course - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (multiple videos)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***
