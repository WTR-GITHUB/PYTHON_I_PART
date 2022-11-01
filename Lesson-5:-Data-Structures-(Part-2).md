1. Sets
1. Dictionary


# Dictionary

a very powerful data structure which is going to be used a lot. Dictionary hold key: value pairs, with which we can access it's attributes.

Creating dictionary and adding values to it

Examples:

```python
my_dictionary = {}
my_dictionary["name"] = "Tom"
print(my_dictionary["name"])
```

```python
my_dictionary = {"name": "Tom"}
print(my_dictionary["name"])
```

## Access dictionary values

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"name: {my_dictionary["name"]})"
print(f"surname: {my_dictionary["surname"]})
```

Similarly as with lists, dictionaries may hold anything in it's key and values. But usually keys would be string values and values could be anything at all.

## Changing values in dictionary

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
my_dictionary["name"] = "Charles"
print(f"name: {my_dictionary["name"]})
```

## Droping key from dictionary

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
del my_dictionary ["name"]
print(my_dictionary)
```



