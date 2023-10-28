## Dictionary

A very powerful _data structure_ which is going to be used a lot. `Dictionary` hold **key: value** pairs, with which we can access it's attributes.
Dictionaries are: 

1. mutable ✔️ (**can be changed**)
1. dynamic ✔️ (**can grow and shrink in size**)
1. nested ✔️ (**can contain other dictionaries or other complex structures**)

A `dictionary` is a _collection_ which is **ordered, changeable and do not allow duplicates**.

Main difference between python `list` and `dictionary` is that **values** in dictionaries **are accessed by keys**.

Creating a dictionary and adding values to it is as simple as: 

```python
my_dictionary = {}
my_dictionary["name"] = "Tom"
print(my_dictionary["name"])
```

```python
my_dictionary = {"name": "Tom"}
print(my_dictionary["name"])
```

### Access dictionary values

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"name: {my_dictionary['name']}")
print(f"surname: {my_dictionary['surname']}")
```

If the value is `non existent` we shall get a `KeyError` as such `key` does not exist:

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"favourite car: {my_dictionary['car']}")
# KeyError: 'car'
```

Dictionaries may use any `immutable type` as it's `key` (so no `list` as for example) and any type as its `values`:
### Changing `values` in `dictionary`

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
my_dictionary["name"] = "Charles"
print(f"name: {my_dictionary["name"]}")
```

### Droping `key` from `dictionary`

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
del my_dictionary ["name"]
print(my_dictionary)
```


### More complex, `nested` structures 
As with the `lists`, we have seen that lists can contain other `lists`, it so happens that the dictionary can have a value of another `diciotnary` and we can built a complex hierarchies like that:

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

Let's say we wanted to print all the languages one by one, we could do something like this:

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
The possibilities are almost endless, we can go deeper and deeper.


### `.items()`

There will be many of situations, that we will want to iterate through `dictionary`. We will be using in-built `.items()` method for `dictionaries`.

```python
d = {'a': 10, 'b': 20, 'c': 30}
print(list(d.items()))
```

### `.keys()`

This method returns dictionary keys:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.keys())
```

### `.values()`
This method returns dictionary values:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.values())
```

### `.pop`

This method pops the `key value` pair based on `key`:


```python
d = {'a': 10, 'b': 20, 'c': 30}
d.pop('a')
print(d)
```

### `.update(obj)`

If `obj` is a `dictionary`, `my_dictionary.update(obj)` merges the entries from `obj` into `dictionary my_dictionary`.
If the `key` **is not present** in a `dictionary` `my_dictionary`, the `key-value` pair from `obj` is added to `my_dictionary`,
otherwise, the corresponding value in `my_dictionary` for that `key` **is updated** with the `value` from `obj`.

Examples:

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_two = {'b': 200, 'd': 400}
dict_one .update(dict_two )
print(dict_one )
```

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_one .update([('b', 200), ('d', 400)])
print(dict_one )
```

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_one .update(b=200, d=400)
print(d1)
```

### Iterating through `dictionary`

Example:
```python
d = {'a': 10, 'b': 20, 'c': 30}
for key, value in d.items():
    print(key, value)
```

### Converting two `lists` into a `dictionary`

Note that `lists` must be of the same size here:

```python
test_keys = ["Albert", "Tom", "Stephen"]
test_values = [1, 4, 5]
my_dictionary= dict(zip(test_keys, test_values))
print(my_dictionary)
```

## Sets

`Sets` are used to store multiple items in a single `variable`.
A `set` is a collection which is **unordered**, **unchangeable**, and **unindexed**.

**Note: Set items are unchangeable, but you can remove items and add new items.**

Notation:

```python
my_set = {1, 2, 3}
```


Another important property is that in `sets` we can't store duplicates values:

```python
my_set = {1, 2, 3, 1}
print(my_set)
# {1, 2, 3}
```

For example, getting unique values from python `list`:
```python
numbers_list = [1, 2, 3, 4, 5, 5, 5, 6]
numbers_set = set(numbers_list)
print(numbers_set)
```

## 🧠Exercises

1. Write python program that asks user to enter `name`, `surname`, `age`. Put these values into a dictionary and print it.
2. Try creating structure like one here: [link](#complex) from an empty `dictionary`: `my_dict = {}`.
3. Create a program, that would take a few sentences from the `input` and create a `dictionary` where they `keys` represents `letters` and `values`
   the frequency those letters appeared in those sentence. The program must demand that user should enter `3` or more sentences. 


## 🌐  Extra reading:
* [More on Python Data structures](https://corporatefinanceinstitute.com/resources/data-science/python-data-structures/)

* [Edureka](https://www.edureka.co/blog/data-structures-in-python/)

