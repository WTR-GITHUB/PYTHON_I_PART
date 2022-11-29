# Python Loops

Python has two primitive loop commands:

* while loops
* for loops


## While loop

With the while loop we can execute a set of statements as long as a condition is true.

```python
i = 0
while i < 10:
  print(i)
  i += 1
```
**Note: remember to increment i, or else the loop will continue forever.**

### endless loops

This loop will not allow user to pass empty space as argument, will always wait until something is typed.
```python
while True:
    user_input = input("Enter your name: ")
    if len(user_input) != 0:
        break
print(f"You entered {user_input }")
```

## For loop

A for loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).


This is less like the for keyword in other programming languages, and works more like an iterator method as found in other object-orientated programming languages.


With the for loop we can execute a set of statements, once for each item in a list, tuple, set etc.

### loop through lists
```python
names = ["Albert", "Tom", "Leonardo"]
for name in names:
    print(f"Greetings, {name}")
```
### loop through strings

```python
name = "Code Academy"
for character in name :
    print(character)
```

### loop through dictionaries:

```python
my_dict = {"name": "Albert", "role": "scientist"}

for key, value in my_dict.items():
    print(key, value)
```

### loop through sets, tuples:
it is exactly the same as with the lists
```python
names = ("Albert", "Tom", "Leonardo")
for name in names:
    print(f"Greetings, {name}")
```


```python
names = {"Albert", "Tom", "Leonardo"}
for name in names:
    print(f"Greetings, {name}")
```

## range() function

The range() function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and stops before a specified number.


### Syntax
range(start, stop, step)

| argument| meaning |
| ------------- | ------------- |
| start  | Optional. An integer number specifying at which position to start. Default is 0  |
| stop  | Required. An integer number specifying at which position to stop (not included).  |
| step | Optional. An integer number specifying the incrementation. Default is 1  |


```python
x = range(3, 6)
for n in x:
  print(n)
```

```python
for n in range(10):
  print(n)
```


## break

With the break statement we can stop the loop even if the while condition is true:

The while loop requires relevant variables to be ready, in this example we need to define an indexing variable, i, which we set to 0.

```python
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```

## continue

With the continue statement we can stop the current iteration, and continue with the next:


```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

## 🧠  Excercises

1. Create a variables containing strings for username and password. Start Endless loop allowing to enter username and password. If credentials are correct stop endless loop and print greeting message.
1. Allow user to enter 10 integers, and then print the sum and average of those entered numbers.
1. Generate a dictionary of 10 keys being 1,2,3...10 each of them should store a value of random integer number from 1 to 100.
1. Create a pin code cracker. Let's say pin code consists of 4 random digits. You can store the value in variable. Then create a loop going through all possible combinations until you find the one you entered.

## 🌐  Extra reading:

* [advanced stuff on loops](https://www.dataquest.io/blog/tutorial-advanced-for-loops-python-pandas/)

