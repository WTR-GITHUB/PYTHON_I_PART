1. For loop.
1. While loop.

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

## For loop

A for loop is used for iterating over a sequence (that is either a list, a tuple, a dictionary, a set, or a string).


This is less like the for keyword in other programming languages, and works more like an iterator method as found in other object-orientated programming languages.


With the for loop we can execute a set of statements, once for each item in a list, tuple, set etc.

```python
names = ["Albert", "Tom", "Leonardo"]
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

##


