# Integers

Z = {..., -3, -2, -1, 0, 1, 2, 3, ...}

How to instantiate a variable as an integer in Python

```python
a = 5
print(a)

b = 25
print(b)
```

# Integer Operations
Possible operations:
| Operation| Result |
| ------------- | ------------- |
| x + y  | sum of x and y  |
| x - y  | difference of x and y  |
| x * y  | product of x and y  |
| x / y  | quotient of x and y  |
| x // y  | floored quotient of x and y  |
| x % y  | remainder of x / y  |
| x ** y | x to the power y |

```python
a = 5
b = 25

c = a + b 
print(c)

c = a - b
print(c)

c = a * b
print(c)

c = b / a
print(c)

c = b // a
print(c)


c = a % b
print(c)

c = a ** b
print(c)
```

# Float type

Z = {..., -2.5 , ..., -2.0, ... , -1.0, ... , 0, ... , 1.0, ... , 2.0, ... , 2.5, ...}

### Note that there can be endless number possibilities between two floats.

# Float Operations
Same operations/ mathematical expressions apply to the float numbers

Possible operations:
| Operation| Result |
| ------------- | ------------- |
| x + y  | sum of x and y  |
| x - y  | difference of x and y  |
| x * y  | product of x and y  |
| x / y  | quotient of x and y  |
| x // y  | floored quotient of x and y  |
| x % y  | remainder of x / y  |
| x ** y | x to the power y |

```python
a = 5.5
b = 25.3

c = a + b 
print(c)

c = a - b
print(c)

c = a * b
print(c)

c = b / a
print(a)

c = b // a
print(a)


c = a % b
print(c)

c = a ** b
print(c)
```

# String

String is simply a piece of text, it could be a single letter or the while word or an entire sentence:
```python
letter = "a"
name = "Code Academy"
sentence = "I really enjoy learning python !"
```


# String operations
Strings have plenty of useful in-built functionality in Python, more information [here](https://www.w3schools.com/python/python_ref_string.asp)

What is more with strings we can select certain characters from the word. In python it works:
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/string_ops.png)
```python
name = "Code Academy"
print(name[5])

# A

print(name[-2])

# m

print(name[5:12])

# Academy

print(name[5:])

# Academy

print(name[:4])

# Code

print(name[5:12:1])

# Academy

print(name[5::2])

# Aaey

print(name[::-1])

# ymedacA edoC

print(name.split())

# ['Code', 'Academy']

print(name.upper())

# CODE ACADEMY

print(name.replace('c', 'k'))

# Code Akademy

print(name.replace('Code', 'Music'))

```

It is also possible to get the last or second to last character from string:
```python
print(name[-1])
print(name[-2])
```

You can also do slicing of string:
```python
name = "Code Academy"
print(name[:4])

print(name[5:12])
```

Try doing any of the methods that are described in the link above:
```python
name = "Code Academy"
print(name.upper())

print(name.replace('c', 'k'))
```
Or any other as you wish.

# Combining of string
You may also combine various string together to make other variables:

```python
greeting = "Hello, my name is"
name = "Tom"

completed_greeting = f"{greeting} {name}"
print(completed_greeting)
```
Or:

```python
greeting = "Hello, my name is"
name = "Tom"

completed_greeting = greeting + " " + name
print(completed_greeting)
```

Wow! "+" operator does work on strings too! All it does is concatenation. Such trick has a term _Operator overloading_ we will learn some tricks how to apply what certain operators can do to our classes. Unfortunately "-" in the case of string does not make any particular sense so this method is not allowed on string type.

# Conversion of types
What is more important to mention are methods allowing to transform data from one type to another:
```python
str()
int()
float()
```

What is important to mention here is not all data types are compatible for such operations. For example:
```python
a = "Hello"
b = int(a)
```
This will simply throw an error because it does not even make sense how the alhapnumeric value can suddenly become an integer

Rule of thumb is that all integers, floats can be translated to string, but only numeric strings can be transformed to int() or float():

```python
✅ 
a = "55"
b = int(a)
c = float(a)

a = 55
b = str(a)
c = float(a)

🛑 
a = "Hello"
b = int(a)

c = float(a)

```

# User input

You program may ask user to enter something and use it for the further operations:

```python
name = input("Enter you name: ")
age = input("Enter your age: ")

print(f"Your name is {name}, you are {age} years old"
```


# Variable naming conventions

As per PEP8 https://peps.python.org/pep-0008/ there are some guidelines to follow when naming your variables. In Python simple variables as we have seen today should be named with snake_case style. What is more constants should be all capital letter, and hidden variables or functions should start with "_".

✅ 
```python
_hidden_variable = "secret"
PI = 3.14
first_name = "Albert"
last_name = "Einstein"
```
⛔ 
possible but does not comply with PEP8:
```python
FirstName = "Albert"
First_Name = "Albert"
FIRST_NAME = "Albert"
```

Python will understand such notion but your colleagues will hate you for this, so please following the naming conventions to make life easy to everyone.

Variables cannot be called as Python built in functions or special words like:
'False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield'



# Excercises 🧠 
1
* Create a program that allows user to Enter his/her name and Age
* Calculate the year in which user was born
* Print the answer to the Terminal


2
* Create a program that allows user to enter a full sentence
* print the sentence backwards
* print every second letter in the sentence

3
* Create a program that expects user to enter two numbers
* multiply those numbers and print the answer
* Create similar programs with other signs.

4
* Create program that allows user to enter text
* Convert that text to Leet speak [1337](https://simple.wikipedia.org/wiki/Leet)
* print outcome

## 🌐  Extra reading:

* [other material](https://pythonhumanities.com/lesson-04-python-integers-and-floats/#:~:text=Numbers%20in%20Python%20exist%20in,from%20and%20exported%20to%20Excel.)
* [string operations](https://www.w3schools.com/python/python_ref_string.asp)

