1. Sets
1. Dictionary


# Dictionary

a very powerful data structure which is going to be used a lot. Dictionary hold key: value pairs, with which we can access it's attributes.
Dictionaries are: 

1. mutable ✔️ (can be changed)
1. dynamic ✔️ (can grow and shrink in size)
1. nested ✔️ (can contain other dictionaries or other complex structures)

main difference between python list is that values in dictionaries are accessed by keys.
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
print(f"name: {my_dictionary['name']}")
print(f"surname: {my_dictionary['surname']}")
```

If the value is non existent we shall get a KeyError as such key does not exist:
```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"favourite car: {my_dictionary['car']}")
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


## <a name="complex"></a>More complex structures!
As with the lists, we have seen that lists can contain other lists, it so happens that the dictionary can have a value of another diciotnary and we can built a complex hierarchies like that
```python
user_info = {
	"name": "Albert",
	"surname": "Einstein",
	"occupation": {
		"role": "Professor",
		"workplace": "University of Berlin"
	},
        "languages": ["German", "Latin", "Italian", "English", "French"]
}
```

let's say we wanted to print all the languages one by one, we could do something like this:
```python
user_info = {
	"name": "Albert",
	"surname": "Einstein",
	"occupation": {
		"role": "Professor",
		"workplace": "University of Berlin"
	},
        "languages": ["German", "Latin", "Italian", "English", "French"]
}

for language in user_info["languages"]:
    print(language)
```
The possibilities here are unlimited, we can go deeper and deeper.


## Dictionary to list of tuples with .items()

There will be a lot of situations, mostly when we want to iterate through dictionary we will be using in-built .items() method of dictionary.

```python
d = {'a': 10, 'b': 20, 'c': 30}
print(list(d.items()))
```

## .keys()

returns us all the dictionary keys:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.keys())
```

## .values()
```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.values())
```

## .pop

```python
d = {'a': 10, 'b': 20, 'c': 30}
d.pop('a')
print(d)
```

## .update(<obj>)

If <obj> is a dictionary, d.update(<obj>) merges the entries from <obj> into d. For each key in <obj>:
If the key is not present in d, the key-value pair from <obj> is added to d.
If the key is already present in d, the corresponding value in d for that key is updated to the value from <obj>.

Examples:

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d2 = {'b': 200, 'd': 400}
d1.update(d2)
print(d1)
```

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d1.update([('b', 200), ('d', 400)])
print(d1)
```

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d1.update(b=200, d=400)
print(d1)
```

## Iterating through dictionary

Example:
```python
d = {'a': 10, 'b': 20, 'c': 30}
for key, value in d.items():
    print(key, value)
```

# Exercises

1. Write python program that asks user to enter name, surname, age. Put these values into a dictionary and print dictionary
1. Try creating structure like one here: [link](#complex) from an empty dictionary: `my_dict = {}`
1. 



