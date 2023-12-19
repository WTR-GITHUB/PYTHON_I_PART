## Logging library

`Logging` is a very useful tool in a programmer’s toolbox. It can help you develop a better understanding of the flow of a program and discover scenarios that you might not even have thought of while developing.

By logging useful data from the right places, you can not only **debug errors** easily but also use the data to analyze the performance of the application to plan for scaling or look at usage patterns to plan for marketing.

The [logging module](https://docs.python.org/3/library/logging.html) in Python is a ready-to-use and powerful module that is designed to meet the needs of beginners as well as enterprise teams. It is used by most of the third-party `Python` libraries, so you can integrate your log messages with the ones from those libraries to produce a homogeneous log for your application.

### `Import the library:`
`import logging`

### `Logging vs Print Statement`
`Logging` and `print` both can be used to debug the code but still, there are reasons for you to choose `log` over `print()`.

A `Log file` contains a log message with other information such as _line number, module name, date, time,_ etc. On the other hand, a `print` statement only has a log message.

A `Log file` will save the records of the application even after it is closed but a print statement will lose out all the records and log message just after the execution stops.

The only time when you should consider using a `print()` statement over a `log` is when you need to display a help statement on the command line.

### `Logging`
There are five ways we can display a log message in python with setting log levels: **DEBUG**, **INFO**, **WARNING**, **ERROR**, and **CRITICAL**.

```python
import logging

logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')

-------------------OUTPUT---------------------
WARNING:root:This is a `warning` message
ERROR:root:This is an `error` message
CRITICAL:root:This is a `critical` message
```
In the code output above, there are two things to notice:

- The **root** is the default logger for all the logs.
- There are only three log messages printed. The reason behind this is the **severity level of log messages** and messages higher than or equal to the severity level of `WARNING` will only get printed.

### `The Five Levels of Logging`
 - **DEBUG**: It is used for diagnosing the problem. It gives a piece of detailed information about the problem. The severity level is 10.
 - **INFO**: It gives the confirmation message of the successful execution of the program. The severity level is 20.
 - **WARNING**: The message is for when an unexpected situation occurs. The severity level is 30.
 - **ERROR**: It is due to a more serious problem than a warning. It can be due to some inbuilt error Like syntax or logical error. The severity level is 40.
 - **CRITICAL**: It occurs when the program execution stops and it can not run itself anymore. The severity level is 50.

### `basicConfig`

We can print the `DEBUG` and `INFO` messages too by **changing the basic configuration of the logger** with the help of `basicConfig(**kwargs)`.
There are some parameters that are commonly used in this:

 - **level**: To change the root logger to a specified severity level.
 - **filename**: Filename where the logs going to be stored.
 - **filemode**: If a filename is given then this specifies the file mode in which the file will open. default is append (a )
 - **format**: This is the format of the log message.
 - **datefmt** : It specified the date and time format.

Simple example:

```python
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%d/%m/%Y %H:%M:%S')
logging.debug('This is Debug Message')
logging.info('This is an info message')
-------------------------CONSOLE OUTPUT------------------
12/05/2021 20:46:41 - root - DEBUG - This is Debug Message
12/05/2021 20:46:41 - root - INFO - This is an info message
```
### `Logging to file`
Similarly, for logging the result** in a file** you can add filename and file mode to `basicConfig`:

```python
logging.basicConfig(level=logging.DEBUG,filename='data.log', filemode='w')
```
```python
import logging
logging.basicConfig(level=logging.DEBUG,filename='data.log', filemode='a', format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%d/%m/%Y %H:%M:%S')
name = input("Enter Your Name:\n")
logging.info(f"{name} has logged in successfully !!")

-----------------data.log file output-------------
12/05/2021 21:01:37 - root - INFO - Tom has logged in successfully !!
12/05/2021 21:02:47 - root - INFO - Karl has logged in successfully !!
12/05/2021 21:03:27 - root - INFO - Rahul has logged in successfully !!
```

### `Logging Exception`
The `logging module` can also able to trace and showcase _full exceptional errors_ that occur during the execution of the program. With the help of `exc_info` with set argument as `True`:

```python
import logging
a = 10
b = 0
try:
  c = a / b
except Exception as e:
  logging.error("Exception Occurred", exc_info=True)  ## At default it is True
  
 ----------------------------------CONSOLE OUTPUT------------------------
ERROR:root:Exception Occurred        ## If exc_info=False then only this message will print
Traceback (most recent call last):
  File "C:\Users\minde\Desktop\ds\python\advance_concepts\logging_code.py", line 5, in <module>
    c = a / b
ZeroDivisionError: division by zero
```
## Exercises: 

1) Create a simple program that would log all inputs from the terminal. Configs must show all additional data (time, date, level etc.)
2) Write a function that moves all elements of one type to the end of the list:
   ```python
   move_to_end([1, 3, 2, 4, 4, 1], 1) ➞ [3, 2, 4, 4, 1, 1]
   # Move all the 1s to the end of the array.
   ```
   Log out inputs and results in a file.

3) Create 3 functions, that are related to each other (one is being called in another), and test all logger severity levels by your own design. 
  
   Function examples:
   ```python
   def check_engine() -> None:
     pass
   
   def start_car() -> None:
     check_engine()...
   .......
    
   ```

4) Create a program that takes 4 data types/structures: `strings`, `numbers`, `list`, `dict`. Iterate 10 times with inputs and log what data 
   type/structure and how many times was entered. Handle all possible errors and log it.


5) Setup accounting software , that would take annual income , expenses , VAT rate (all values must be floats) and calculate profit, paid taxes in 4 
   different currencies (USD, EU, JPY, CNY). All calculations and results should be printed on screen. All data and possible errors must be logged to a 
   file. 

## 🌐  Extra reading (or watching 📺 ):

* [Real Python](https://realpython.com/python-logging/)
* [Corey Schafer: Logging (multiple videos)](https://www.youtube.com/watch?v=-ARI4Cz-awo)
***
