## Python `conditions` and `if` statements

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
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two !")
```
**It is important that the statements after the `if clause` and colon (`:`) is indented. Python relies on indentation (whitespace at the beginning of a line) to define scope in the code. Other programming languages often use curly-brackets for this purpose.**

### `elif`
What if we want to extend out program and print out something else if the statement is not true?

Example:

```python
number_one = 500
number_two = 600
if number_one < number_two:
    print("number_one is greater than number_two!")
elif number_one == number_two:
    print("Numbers are equal !")
```

**Note. There can be as many `elif` statements as we want**

```python
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two  !")
elif number_one == number_two :
    print("numbers are equal !")
elif...
```

### `else`

The else keyword catches anything which isn't caught by the preceding conditions:

```python
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two  !")
elif number_one == number_two :
    print("numbers are equal !")
else:
    print("number_two is greater than number_one !")
```

### short version of `if ... else`

```python
a = 200
b = 450
print("A") if a > b else print("B")
```

3 conditions example:

```python
a = 200
b = 200
print("A") if a > b else print("=") if a == b else print("B")
```

### `and`
We have more logical operators that allow us to combine statements into more complex logic.
The **and** keyword is a logical operator, and is used to combine conditional statements.
Basically both conditions **must be true for statement to return `True` **:

```python
a = 200
b = 400
c = 500
if c > a and c > b:
    print("C is the greatest of them all!")
```

### `or`

The or keyword is a logical operator, and is used to combine conditional statements.
Basically at least one of the conditions must be true for statement to return `True`:

```python
a = 200
b = 400
c = 500
if b > a or b > c:
    print("B is at least greater than one of the values !")
```

### Nested `if`

As we have seen with `lists` being able to carry other `lists` inside them. There is no exception for `if` statements.

```python
x = 15

if x > 10:
  print("Above 10")
  if x > 20:
    print("and also above 20!")
  else:
    print("Above 10 but bellow 20!.")
```

### `pass`

If we want to have an empty `if` statement for some reason we can simply do `pass` and nothing will happen.
```python
a = 50
b = 80

if b > a:
  pass
```


### `If` with `string` values

We may also do logical operations on strings.

```python
name = "Tom"

if name == "Tom":
    print("Nice to see you Tom")
else:
    print("welcome, user")
```

Lets do this with `lists` as well!

```python
user = "Johnny"
privileged_users = ["Tom", "Albert", "Stephen"]
if user in privileged_users:
    print(f"Welcome home {user}")
else:
    print("INTRUDER ALLERT. Silently calling police...")
```

Or even dictionaries:
```python
my_dict = {"name": "Steven", "born": "1955-02-24", "interests": "Apples"}
if my_dict["name"] == "Steven":
    print("This guy does not like Windows")
else:
    print("No clue who this is")
```

```python
my_dict = {"name": "Bill", "born": "1955-10-28", "interests": "small software"}
if "Bill" in my_dict.values():
    print("This guy hates apples")
else:
    print("No clue who this is")
```
### Shorter version of `if..`

in Python we love to optimize code. For example, if we want to check that user has entered a `name` at all . Instead of doing this:

```python
...
if name != "":
  print("Name was not entered")
...
```
or

```python
...
if len(name) == 0:
  print("Name was not entered")
...
```
Do this:
```python
if not name:
  print("Name was not entered")
```

Same applied to other data structures as well

```python
my_list = []
if not my_list:
  print("oh no, list is empty")
```

## 🧠 Exercises:

1. Let user enter `name`, `surname` and `age`. Print if `user` is allowed to enter an online casino or not. `21` is the `age` cap.
2. Create a database (`list` of privileged users), print a specific message with a personal greeting if the `user` is a privileged and just "Welcome otherwise"
3. Allow user to enter two numbers, print out which one is higher than the other, or equal.
4. Write a small calculator application, that allows user to enter two numbers and a symbol, do the operation and print the answer.
5. Create a number guessing game from `1-10`. 


## 🌐  Extra reading:
[RealPython](https://realpython.com/python-conditional-statements/)
