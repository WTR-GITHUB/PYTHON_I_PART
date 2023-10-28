# Lists

In this section we will cover first Python `Data Structure` - `List` or what in other programming languages is called an `array`.

`Lists` can contain no values whatsoever, be empty, or as many objects as `RAM` allows us to hold. What is more, it so happens that in Python `lists` can hold **any types** of values,  it could be other **objects, functions, strings, integers, your own data types or even other lists**. What is also important to mention is that we can change values within the list, lists are **mutable** python objects.

## Notation
The notation of the list is simply these brackets: **`[ ]`** two brackets with values in between separated by commas.

## Creating an empty list in python:
```python
my_list = [] # Instantiating empty list
```
## Special python lists methods

### .append()
There is method called `.append()` that allows to insert an item into the list: `append(<object>)`

```python
my_list = []

name = "Tom"
my_list.append(name)
print(my_list)
```

### .count(obj)

Since there can be dublicated values within the list this function allows us to calculate the frequency of the item within the list

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
print(my_list.count(1)) # 2
```

### .insert()
As we have seen `append` always adds the value to the end of the list, `.insert()` allows us to add the value to which ever index we want:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.insert(1, 50)
print(my_list) # [1, 50, 1, 2, 3, 4, 5]
```

### .remove()
Name speaks for itself. With this method we will simply drop a particular value from the list:
```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(1)
print(my_list)
```
The function will remove the first occurence of the object found. If you want to remove particular item from the list, you can do that with slicing mechanism:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(my_list[-1]) # removing last item from the list
print(my_list) [1, 1, 2, 3, 4]
```

## Python built-in `List` functions
As we have already seen such functions as `print` and probably a few others along the way, Python `lists` also make use of quite a few of them so we do not have to reinvent the wheel each and every time.

### len()
Note that we do not have the "." symbol now, meaning that there are standalone functions that do not belong to a particular data type.

As we have previously discussed lists can be of whatever length, so it would be nice to know how big of a list we are dealing with. `len()` comes in handy here:

```python
my_list = ["name", 123, None, True]
print(len(my_list)) # 4
```

### max()
If you have list of `int`, `float` values you **may find out maximum value** with this function:

```python
my_list = [50, 99, 1, -50]
print(max(my_list))
```

### min()
If you have list of `int`, `float` type values you may **find out minimum value** with this function:
```python
my_list = [50, 99, 1, -50]
print(min(my_list))
```

## Iterating over elements within the `list`

The biggest strength within the lists is that we can have a list of certain actions, objects that we want to do one after another, we can _iterate_ over them and do some actions. 

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item)
```
or we could do some operations along the way as well!

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item + 20)
```

## Changing an existing value within the list

```python
my_list = [1, 2, 3]
my_list[2] = 5
print(my_list)
```
## Slicing
As with the string we can also be slicing items withing the list as well. Each and every item in the list **contains an index** starting at `0`. So we can perform same type of slicing:

```python
my_list = ["first", "second", "third"]
print(my_list[-1])
print(my_list[:1])
print(my_list[::2])
print(my_list[::-1])
print(my_list[0:2])
```

## Operator in with Lists

If you want to check if a certain object is in the list you may do something like this:

```python
my_list = [1, 2, 3]
print(1 in my_list)
```
# Tuple

Another very similar python built-in data structure is `Tuple`. The main difference here is that `Tuple` **is immutable**. Meaning that we have an object that contains multiple values, they can be duplicated, almost all characteristics are similar except that the items in **Tuple by design cannot be changed**.

## Notation

Tuple notation in python is `( )` - two parentheses with values in between separated by commas.

### Creating tuples

```python
empty_tuple = ()
tuple_single_item = (1,)
another_tuple = (1, 2, 3)
```
Note that single item `tuple` **must contain comma**, even though it's just a single item. Other than that it is all the same as the List
### Operations

Those are simply exactly the same, except that you are unable to mutate the tuple. If you try doing so, you will get an error:

🛑 
```python
my_tuple = (1, 2, 3)
my_tuple[0] = 500 # TypeError: 'tuple' object does not support item assignment
```

# Tuples vs Lists

Now it seems that Lists are much better than tuples, but in programming everything is not always one sided and it depends on certain situations.
Usually it is recommended to u**se Tuple on static values** that do not change as it is a bit faster in python than lists. And we should be using lists whenever we have values that are going to be changing, or the list itself will grow or shrink in size.


## 🧠 Exercises:

**`All answers must be printed in terminal`**
1. Write a python program that sums up all items in the list (all items are integers or floats in list, create a list yourself).
1. Write a python program that multiplies all items in the list (all items are integers or floats in list, create a list yourself).
1. Write a python program that gets maximum value from the list (all items are integers or floats in list, create a list yourself).
1. Write a python program that concatenates all strings in the list (all items are strings, create a list yourself).
1. Create two lists and add them together, make sure it works the way you want it to.
1. Write a python program that asks user to enter 3 integers and find the highest value entered.
1. Try doing same exercises with tuples.


## 🌐  Extra reading:

* [w3schools](https://www.w3schools.com/python/python_lists.asp)
* [more material](https://www.programiz.com/python-programming/list)
