1. List, tuple, dict comprehensions 

1. zip method

3 Enumerators



# Data Structure: Special methods

In this lecture we will review some additional functionalities of python built-in data structures. And also review **`math`** library

## List comprehensions

It is a very useful way of making your loops more compact/ readable/ understandable. 

Example:

Let's say you want a program that gets first 10 perfect squares, how do you do it?

```python
squares = []
for number in range(10):
    squares.append(number * i)
print(squares)
```

It works just fine, but there is a bit nicer way of writing this down which is even more human readable:

```python
squares = [number * number for number in range(10)]
print(squares)
```

Neat isn't it? All it does is the following:

1. creates squares as a list.
1. inside of the list it says that we are looping all the numbers in `range(10)`
1. each object in the list is going to be that number in the loop multiplied by the number: `number * number`


What is more, what if we wanted to have all the perfect squares except 25? Try writing this one down without list comprehension.

The implementation with list comprehension:

```python
squares = [number * number for number in range(10) if number != 5]
print(squares)
```

**Boom**, simple yet efficient and still super human readable. 

Now trying writing down a list comprehension yourself that would only return perfect square of even numbers:




Answer
```python
squares = [number * number for number in range(10) if number % 2 == 0]
print(squares)
```

Alright for now we have seen such numbers with only integers, but can we work with strings too? Ofcourse!

let's say you have list of names and want to filter our only the ones starting with certain letter:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A")])
```

You can even chain more logic with **and** and **or** clauses as well:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A") or "e" in name])
```

As you can see you can chain as much logic as you want to here. But it is best to keep there list comprehensions as short as possible because if you have too much logic here, it might become impossible to understand even for you after couple of days...

### **Note** ❗ The list, set, tuple comprehensions work exactly the same except that outer brackets are different, everything else stays the same.


## Dictionary comprehensions

Dictionaries also have this fancy one liner comprehension functionality:

Let's say we have the same problem of perfect squares but we want to have _number: percect_square_ structure like this: **`{1: 1, 2: 4, 3: 9}`**
Try writing this without dictionary comprehension yourself.


Dictionary comprehension example:

```python
squares = {i: i * i for i in range(10)}
print(squares)
```

Try doing both exercises done with lists:
1. program without perfect square of 5.
1. only odd numbers.

## Enumerate

Let's imagine we have a python loops over some items in the list:

```python
values = ["a", "b", "c"]

for value in values:
    print(value)
```

it is a simple nice loop, that does all it has to. Now imagine you also want to get the corresponding index of the item. How would you do it?

You could do something like this:

```python
index = 0

for value in values:
    print(index, value)
    index += 1
```

So here we have an integer that increments with each iteration and it also works. But too keep our code simpler we may use python build int function **`enumerate()`**


```python
for count, value in enumerate(values):
    print(count, value)
```

If we wanted to change the start count:

```python
for count, value in enumerate(values, start=1):
    print(count, value)
```


If we go a bit crazy we can combine two things we learned today:
```python
def even_items(numbers: list):
    return [v for i, v in enumerate(numbers, start=1) if not i % 2]

seq = list(range(1, 11))
```
