## Data Structure: Special methods

In this lecture we will review some additional functionalities of python built-in data structures. And also review **`math`** library

### `List comprehensions`

It is a very useful way of making your `loops` more compact/ readable/ understandable. 

Example:

Let's say you want a program that gets first 10 perfect squares:

```python
squares = []
for number in range(10):
    squares.append(number * number)
print(squares)
```

It works just fine, but there is a bit nicer way of writing this down which is even more human readable:

```python
squares = [number * number for number in range(10)]
print(squares)
```

All it does is the following:

1. Creates squares as a `list`.
2. Inside of the `list` it says that we are looping all the numbers in `range(10)`
3. Each object in the `list` is going to be that number in the `loop` multiplied by the number: `number * number`


What is more, what if we wanted to have all the perfect squares except `25`? Try writing this one down without `list` comprehension:

```python
squares = [number * number for number in range(10) if number != 5]
print(squares)
```

Simple, yet efficient and still super human readable. 

Now lets try to write down a `list` comprehension that would only return perfect `square` of `even numbers`:


Answer
```python
squares = [number * number for number in range(10) if number % 2 == 0]
print(squares)
```


Let's say you have `list` of names and want to filter our only the ones starting with certain letter:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A")])
```

You can even chain more logic with **and** and **or** clauses as well:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A") or "e" in name])
```

As we see you can chain as much logic as you want to here. But it is best to keep there list comprehensions as short as possible because if you have too much logic here, it might become impossible to understand.

### **Note** ❗ The `list`, `set`, `tuple` comprehensions work exactly the same except that outer brackets are different, everything else stays the same.


### `Dictionary comprehensions`

`Dictionaries` also have this fancy one liner comprehension functionality:

Let's say we have the same problem of perfect squares but we want to have _number: percect_square_ structure like this: **`{1: 1, 2: 4, 3: 9}`**
Try writing this without dictionary comprehension yourself.

Dictionary comprehension example:

```python
squares = {i: i * i for i in range(10)}
print(squares)
```

Try doing both exercises done with lists:
1. Program without perfect square of 5.
2. Only odd numbers.

### `Enumerate`

Let's imagine we iterate over some items in the `list`:

```python
values = ["a", "b", "c"]

for value in values:
    print(value)
```

it is a simple nice `loop`, that does all it has to. Now imagine you also want to get the corresponding index of the item:

```python
values = ["a", "b", "c"]
index = 0

for value in values:
    print(index, value)
    index += 1
```

So here we have an `integer` that increments with each iteration and it also works. But too keep our code simpler we may use python build in function **`enumerate()`**


```python
values = ["a", "b", "c"]
for count, value in enumerate(values):
    print(count, value)
```

If we wanted to change the start count:

```python
values = ["a", "b", "c"]
for count, value in enumerate(values, start=1):
    print(count, value)
```


If we go a bit crazy we can combine two things we learned today:
```python
def even_items(numbers: list) -> list:
    return [v for i, v in enumerate(numbers, start=1) if not i % 2]

seq = list(range(1, 11))

print(even_items(seq))
```

Go through this once yourself, operate small things out and combine them together once again.

**NOTE** `enumerate` returns an iterator so if you want to look what's inside you can either loop through it or convert it to `list`.


### `mat` library

For most math specific calculations you can use `math` library in `python`:
```python
import math
```

For example if you wanted to calculate a circle area:

```python
import math
area = 5 * 5 * math.pi
```

`math.pi` here is a constant which we can you straight out of the box.

Some more functionality:

### `factorial`

For example if we wanted to calculate factorial: `7! = 7 * 6 * 5 * 4 * 3 * 2 * 1`

We could write a function ourselves, but actually it is already available to us:

```python
import math
math.factorial(7)
```

What is more it is actually quite optimized as well.


#### `ceil()` and `floor()`

All there functions do is that if you have a `float` value, it can literally get `floor` or `ceiling` of it. Examples:


```python
import math


print(math.ceil(6.1))

print(math.floor(-11.1))
```

Is this clear?


#### `power function`


Let's say you want to have a number raised by the power of `n: 5^5 = 5 * 5 * 5 * 5 * 5 = 3125`


```python
import math

print(math.pow(5, 5))
```


#### `square root`


```python
import math
print (math.sqrt(9))
```

There is more functionality in math library as said before, here we reviewed just a tiny bit



## Exercises 🧠 :

1. Find all of the numbers from 1-1000 that are divisible by 6.
1. Find all number from 1-1000 that have 9 in them.
1. Given string: `text = 'In this lecture we will review some additional functionalities of python built-in data structures.'` calculate how many words have letter 'e' in it.
1. Given the same string as in previous exercise: calculate count of words that have more than 5 characters.
1. Given the same string calculate the occurrence of each letter in the string. (HINT: store everything in dictionary)
1. Write a program that checks if given number is a perfect square.

## 🌐  Extra reading:

* [Real Pyhton comprehensions](https://realpython.com/list-comprehension-python/)

* [Real Python math](https://realpython.com/python-math-module/)
***