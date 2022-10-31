# 🐍 Built-in functions

## print()

As we have seen before we used `print` couple of times already and made ourselves familiar with it. We did not create the function itself as it comes out of the box right after installing python. It is important to mention that this function is not as dull as it may seem from the first glance, in fact it's quite versatile.

print(object(s), sep=separator, end=end, file=file, flush=flush)

| Operation| Result |
| ------------- | ------------- |
| object(s)  | Any object, and as many as you like. Will be converted to string before printed  |
| sep='separator'  | Optional. Specify how to separate the objects, if there is more than one. Default is ' '  |
| file  | Optional. Specify what to print at the end. Default is '\n' (line feed)  |
| flush  | Optional. An object with a write method. Default is sys.stdout  |
| x // y  | Optional. A Boolean, specifying if the output is flushed (True) or buffered (False). Default is False  |

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