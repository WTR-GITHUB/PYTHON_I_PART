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

------ OUTCOME -------------
INFO:root:Logging th event

```
