Mighty ‘if’

# Python Conditions and If statements

When executing code we usually want to make some sort of decisions according to the data we are getting, if statements allows us to that eactly.

How it looks like:
```python
if <test_expression>:
    statement(s)
```


Flow chart:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/if_else.webp)


For checking of the conditions, python support usual mathematical expressions:

* Equals: a == b
* Not Equals: a != b
* Less than: a < b
* Less than or equal to: a <= b
* Greater than: a > b
* Greater than or equal to: a >= b

Example:
```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
```
**It is important that the statements after the if clause and colon (":") is indented. Python relies on indentation (whitespace at the beginning of a line) to define scope in the code. Other programming languages often use curly-brackets for this purpose.**

## Elif
What if we want to extend out program and print out something else if the statement is not true?

Example:

```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
elif number1 == number2:
    print("numbers are equal !")
```

**Note. There can be as many elif statements as we want**

```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
elif number1 == number2:
    print("numbers are equal !")
elif...
```

## 

