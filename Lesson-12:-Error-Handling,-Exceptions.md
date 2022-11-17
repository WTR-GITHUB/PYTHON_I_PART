## Introduction

Exceptions are the events that are triggered when the program encounters an error during execution. When an error occurs, we can handle these exceptions to avoid the program from getting crashed.

### Why do we Require Exception Handling?

* **Error Handling**: In the case of Errors during runtime, the application might terminate unconditionally. Using the Exception Handling, we can handle the scenario of Failures and avoid termination of the program.
* **Code Separation**: Error Handling can help us segregate the code that is required for error handling from the main logic. The error related code can be placed inside the “except” block which is segregating it from the regular code that contains the application logic.
* **Grouping Error Type and Error Differentiation**: It can help us to segregate different kinds of errors that are encountered during the execution. We can have multiple “except” blocks, each handling a specific kind of error. In the article below, we will see the implementation of multiple “except” blocks to handle different types of error.

It’s important we make a clear distinction between what an error is in Python, as there are two. One error is known as a syntax error (or parsing error). This is when our program is being parsed and detects an incorrect statement within our code. These types of errors cannot be handled.

Another type of error we may observe is an Exception error. These types of errors occur when our code is syntactically correct but an unexpected event occurred during the execution of the program. They are not unconditionally fatal and can be handled at runtime

### Catching and handling Exceptions
To capture the exceptions we use a code block called try-except. We put the piece of code that is suspected to be a source of error inside a try block then capture and design the response inside the except block.
```
def my_func():
  try:
    your_code()
  except Exceprion as e:
    print(f"This is the captured error: {e}")

my_func()

```