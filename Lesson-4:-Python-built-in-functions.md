Print, type, len, ..etc.


# 🐍 Built-in functions

## print()

As we have seen before we used `print` couple of times already and made ourselves familiar with it. We did not create the function itself as it comes out of the box right after installing python. It is important to mention that this function is not as dull as it may seem from the first glance, in fact it's quite versatile.

print(object(s), sep=separator, end=end, file=file, flush=flush)

| argument| meaning |
| ------------- | ------------- |
| object(s)  | Any object, and as many as you like. Will be converted to string before printed  |
| sep='separator'  | Optional. Specify how to separate the objects, if there is more than one. Default is ' '  |
| end='end' | Optional. Specify what to print at the end. Default is '\n' (line feed)  |
| file  | Optional. An object with a write method. Default is sys.stdout  |
| flush  | Optional. A Boolean, specifying if the output is flushed (True) or buffered (False). Default is False  |

Some examples:
```python
# Simple print
print("hello world")

# Gets the same result but slightly different:
print("hello", "world")

# Gets the same result but is even more different:
print(*["hello", "world"])

# let's play with separator:
print("hello world", sep=",")

# some more
print("hello", "world", sep=" amazing ")
```

## type()

Another useful function for us to understand what we are dealing with in python is type. often it helps us to understand what instance of the object are we dealing with. Basically it tells us what kind of object we are dealing with.

Examples:
```python
greet = "Hello World"
print(type(a))

number = 2022
print(type(number))

my_list = [1, 2, 3]
print(type(my_list))

print(type(my_list[0]))
```

This becomes really helpful later on when dealing with more complex programs.

## len()
We have already seen this function before with list, so we are also a bit familiar with in. As you remember it returns the length of the list or tuple.
Nevertheless it still works with strings as well. 

Examples:
```python
word = "something"
length = len(word)

print(f"length of the word {word} is: {length}")
```

Reminder how it works with lists:

```python
my_list = [1, 2, 3]

print(f"length of the list {my_list} is: {len(my_list)}")
```

## round()

Function allows to round float to a certain decimal point. It is also quite useful.

round(number, ndigits=None)
| argument| meaning |
| ------------- | ------------- |
| number  | number that needs to be rounded  |
| ndigits  | decimal places, by default None, meaning that it will be rounded to integer value  |


Examples:

```python
print(round(1.999))

print(round(1.5555, 2))
```

## sorted

What if we would like to sort values in the list or tuple

Examples:
```python

```

