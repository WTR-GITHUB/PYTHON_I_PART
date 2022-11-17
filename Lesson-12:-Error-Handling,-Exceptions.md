## Introduction

Exceptions are the events that are triggered when the program encounters an error during execution. When an error occurs, we can handle these exceptions to avoid the program from getting crashed.

### Why do we Require Exception Handling?

* **Error Handling**: In the case of Errors during runtime, the application might terminate unconditionally. Using the Exception Handling, we can handle the scenario of Failures and avoid termination of the program.
* **Code Separation**: Error Handling can help us segregate the code that is required for error handling from the main logic. The error related code can be placed inside the “except” block which is segregating it from the regular code that contains the application logic.
* **Grouping Error Type and Error Differentiation**: It can help us to segregate different kinds of errors that are encountered during the execution. We can have multiple “except” blocks, each handling a specific kind of error. In the article below, we will see the implementation of multiple “except” blocks to handle different types of error.

It’s important we make a clear distinction between what an error is in Python, as there are two. One error is known as a syntax error ([or parsing error](https://rollbar.com/blog/python-syntaxerror/)). This is when our program is being parsed and detects an incorrect statement within our code. These types of errors cannot be handled.

Another type of error we may observe is an Exception error. These types of errors occur when our code is syntactically correct but an unexpected event occurred during the execution of the program. They are not unconditionally fatal and can be handled at runtime

### Catching and handling Exceptions
To capture the exceptions we use a code block called try-except. We put the piece of code that is suspected to be a source of error inside a try block then capture and design the response inside the except block.

A simple `boilerplate` code example would be: 
```
def my_func() -> Any:
  try:
    # code which might throw/raise exception
  except <exception_to_handle>:
    # code to be executed once the exception is handled.

my_func()

```

The basic schema for exception handling is here down below ⬇️ 

![ah](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/try_except_else_finally.webp)

Python consists of several built-in exceptions we may leverage in our programs: ⬇️

![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/1%20yKRseWKBjdccXRoFsjIIQw.png)

### Examples
Lets use simple function to divide 2 numbers and try to handle possible error:
```
def divide_two_numbers(dividend: int, divisor: int) -> None:
    try:
        quotient = dividend / divisor
        print(f'Result = {quotient}')
    except ZeroDivisionError:
        print('Divisor is zero; Division is impossible')
```
Possible results: 
```
>>> divide(50, 2)
Result = 25
>>> divide(50, 0)
Divisor is zero; Division is impossible
```

👨‍🏫  **< PRO TIP >**
**Try to avoid generic `except` clause, otherwise you can miss and/or mishandle potential errors** 🔽 
```
def my_func() -> Any:
  try:
    # code which might throw/raise exception
  except:
    print('Ups! Something went wrong!')

my_func()
```


### Extra references:

* [Official Python Website](https://docs.python.org/3/tutorial/errors.html)

* [Real Phyton](https://realpython.com/python-exceptions/)
***



