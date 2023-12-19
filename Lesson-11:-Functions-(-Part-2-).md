## `Continue`
One of the powerful yet less popular feature of Python are the `*args` and the `**kwargs` arguments, `lambda function`.

### `*args`, `**kwargs`
So, what are the `*args` and `**kwargs` arguments? On a high level, they allow functions to _accept optional arguments_ providing us with the flexibility to call a function with any number of arguments. Therefore, using them allows us to write more flexible classes and modules.

A simple example : 🔽 

```python
def check_arguments(mandatory: Any, *args, **kwargs) -> None:
    print(mandatory)
    if args:
        print(args)
    if kwargs:
        print(kwargs)
```

Above function `check_arguments` requires at least one argument called “mandatory” but it can accept extra `positional` and `keyword` arguments as well.
If we call the function with additional arguments, `args` will collect extra _positional arguments_ as a **tuple** because the parameter name has a * prefix.

Likewise, `kwargs` will collect extra keyword arguments **as a dictionary** because the parameter name has a ** prefix. Both `args` and `kwargs` will be empty if no extra arguments are passed to the function.
Let’s invoke our `check_arguments` method with different arguments to understand the `args` and `kwargs` behaviour:

```python
>>> check_arguments():
TypeError:
"check_arguments() missing 1 required positional arg: 'mandatory'"
>>> check_arguments('welcome')
welcome

>>> check_arguments('welcome', 1, 2, 3)
welcome
(1, 2, 3)

>>> toy_fun('welcome', 1, 2, 3, name='Sarah', age=26)
welcome
(1, 2, 3)
{'name': 'Sarah', 'age': 26}
```
👨‍🏫  ❗ **GOOD TO KNOW** ❗ 
** `args` and `kwargs` is simple a naming convention. Above example would work just fine if we called them `*parms` and `**argv` or anything for that matter. Actual syntax is just the asterisk (*) or double asterisk (**).**

👨‍🏫  ❗ **ATTENTION!** ❗ 
** While using `*args` or `**kwargs` with other parameters or using them together, we should keep in mind that the arguments should follow the given order ⬇️ .**

1. **Formal arguments**
2. ***args**
3. **keyword arguments**
4. ****kwargs**

```python
def my_func(a:int, b:int, *args, c: int = 5, d: int = 9, **kwargs) -> None:
    print (a, b)
    print (type(args), args)
    print (c, d)
    print (type(kwargs), kwargs)

>>> my_func(1, 2, 3, 4, 5, e=6, f = 7)
1, 2
<class 'tuple'> (3, 4, 5)
5, 9
<class 'dict'> {'e': 6, 'f': 7}
```

## `Lambda function`
**Lambda Functions** are _anonymous_ function in Python. Lambda functions are similar to regular functions. The difference between regular function and lambda function is that they can be **defined without a name** but the normal functions are defined with `def` keyword.
**_lambda_** keyword is used to define an anonymous or lambda function.
If we could compare a lambda function with normal function:

* A `lambda` function can take any number of arguments, but can only have one expression while regular function have exact number of arguments that we declare at the time of defining.
* `Lambda` functions are one line functions. its body contain expression in the same line in which it is defined. In normal functions, functions contains body blocks in which some statements are defined to execute.
* As `lambda` is a single line function so it can be invoke instantly but normal function needs to call itself and take time to call.

The simple multiplication function: 

```python
def multiply(x: int,y: int) -> int:
    return x * y

print(multiply(2,3))
>>> 6
```
we can re-write as a `lambda` function:

```python
multiplication =  lambda  x,y :  x * y
print(multiplication(2,3))
>>> 6
```
We can pass the arguments to function by surrounding the function and its argument with parentheses:

```python
multiplication = (lambda  x,y :  x * y)(2,3)
print(multiplication)
>>> 6
```

### `Usage`
The `lambda` function is preferred:

* When you want one-time usage of the function.
* When there is a single expression in the function definition.
* When you want to write clear syntax with a few lines of code.

However, it is not suitable:

* When you need to reuse the function again and again.
* When there are many or complex expressions in the function definition.

## Exercises: 
🧠 : Repeat the [Data Structures (part 1)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-3:-Data-Structures-(Part-1)), [Data Structures (part 2)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-5:-Data-Structures-(Part-2)), [Conditional Statements](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Loops](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops) to finish these task.

1) Write a function that takes two `lists` and adds the first element in the first `list` with the first element in the second `list`, the second element 
   in the first `list` with the second element in the second `list`, etc, etc. Return `True` if all element combinations add up to the same number. 
   Otherwise, return `False`.
   Example: 

   ```python
   puzzle_pieces([1, 2, 3, 4], [4, 3, 2, 1]) ➞ True
   # 1 + 4 = 5;  2 + 3 = 5;  3 + 2 = 5;  4 + 1 = 5
   # Both lists sum to [5, 5, 5, 5]
   puzzle_pieces([1, 8, 5, 0, -1, 7], [0, -7, -4, 1, 2, -6]) ➞ True
   puzzle_pieces([1, 2], [-1, -1]) ➞ False
   puzzle_pieces([9, 8, 7], [7, 8, 9, 10]) ➞ False
   ```

2) There's a great war between the even and odd numbers. Many numbers already lost their lives in this war and it's your task to end this. You have to 
  determine which group sums larger: the evens or the odds. The larger group wins.

  Create a function that takes a list of integers, sums the even and odd numbers separately, then returns the difference between the sums of the even and 
  odd numbers.

  Example: 
  ```python
  war_of_numbers([2, 8, 7, 5]) ➞ 2
  # 2 + 8 = 10
  # 7 + 5 = 12
  # 12 is larger than 10
  # So we return 12 - 10 = 2
  war_of_numbers([12, 90, 75]) ➞ 27
  war_of_numbers([5, 9, 45, 6, 2, 7, 34, 8, 6, 90, 5, 243]) ➞ 168
  ```

3) You are given an input array of bigrams, and an array of words. Write a function that returns True if every single bigram from this array can be found 
   at least once in an array of words.
   
  Example:
  ```python
  can_find(["at", "be", "th", "au"], ["beautiful", "the", "hat"]) ➞ True
  can_find(["ay", "be", "ta", "cu"], ["maybe", "beta", "abet", "course"]) ➞ False
  # "cu" does not exist in any of the words.
  can_find(["th", "fo", "ma", "or"], ["the", "many", "for", "forest"]) ➞ True
  can_find(["oo", "mi", "ki", "la"], ["milk", "chocolate", "cooks"]) ➞ False
  ```
4) Reimplement some previous solutions using the lambda function. 
## 🌐  Extra reading:

* [Type Annotations in Python 3.8](https://medium.com/analytics-vidhya/type-annotations-in-python-3-8-3b401384403d)

* [Real Phyton](https://realpython.com/defining-your-own-python-function/)

* [Real Python Youtube](https://www.youtube.com/watch?v=Q93bwyZoXk0)
***
