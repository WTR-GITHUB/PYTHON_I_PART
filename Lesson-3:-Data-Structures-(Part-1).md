# Lists

In this section we will cover another Python Data Structure - List or what in other programming languages is called an array.

Lists can contain no values whatsoever, be empty, or as many objects as RAM allows us to hold. What is more, it so happens that in Python lists can hold any types of values,  it could be other objects, functions, strings, integers, your own data types or even other lists.

## Creating an empty list in python:
```python
my_list = [] # Instantiating empty list
```
## Special python lists methods

### .append()
There is method called .append() that allows to insert an item into the list: append(<object>)

```python
my_list = []

name = "Tom"
my_list.append(name)
print(my_list) # ['asdf']
```

### .count(obj)

Since there can be dublicated values within the list this function allows us to calculate the frequency of the item within the list
```python
my_list = [1, 1 ,2 ,3 ,4 ,5]
print(my_list.count(1)) # 2
```

### .insert()
as we have seen append always adds the value to the lists end, .insert() allows us to add the value to which ever index we want:
```python
my_list = [1, 1 ,2 ,3 ,4 ,5]
my_list.insert(1, 50)
print(my_list) # [1, 50, 1, 2, 3, 4, 5]
```

### .remove()
Name speaks for itself. with this method we will simply drop a particular value from the list:
```python
my_list = [1, 1 ,2 ,3 ,4 ,5]
my_list.remove(1)
print(my_list)
```
The function will remove the first occurence of the object found. If you want to remove particular item from the list, you can do that with slicing mechanism:
```python
my_list = [1, 1 ,2 ,3 ,4 ,5]
my_list.remove(my_list[-1]) # removing last item from the list
print(my_list) [1, 1, 2, 3, 4]
```

## Python built-in List functions
As we have already seen such functions as print and probably a few others along the way, Python lists also make use of quite a few of them so we do not have to reinvent the wheel each and every time.
### len()
Note that we do not have the "." symbol now, meaning that there are standalone functions that do not belong to a particular data type.

As we have previously discussed lists can be of whatever length, so it would be nice to know how big of a list we are dealing with. len() comes in handy here:
```python
my_list = ["name", 123, None, True]
print(len(my_list)) # 4
```

### max
if you have list of int, float values you may find out maximum value with this function:
```python
my_list = [50, 99, 1, -50]
print(max(my_list))
```

### min
if you have list of int, float values you may find out minimum value with this function:
```python
my_list = [50, 99, 1, -50]
print(min(my_list))
```

## iterating over elements within the list

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item)
```


# Tuple


