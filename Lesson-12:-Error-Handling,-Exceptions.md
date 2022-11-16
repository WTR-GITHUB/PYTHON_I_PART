## Introduction

Exceptions are the events that are triggered when the program encounters an error during execution. When an error occurs, we can handle these exceptions to avoid the program from getting crashed.

### Why do we Require Exception Handling?

* Error Handling: In the case of Errors during runtime, the application might terminate unconditionally. Using the Exception Handling, we can handle the scenario of Failures and avoid termination of the program.
* Code Separation: Error Handling can help us segregate the code that is required for error handling from the main logic. The error related code can be placed inside the “except” block which is segregating it from the regular code that contains the application logic.
* Grouping Error Type and Error Differentiation: It can help us to segregate different kinds of errors that are encountered during the execution. We can have multiple “except” blocks, each handling a specific kind of error. In the article below, we will see the implementation of multiple “except” blocks to handle different types of error.