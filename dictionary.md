---
title: Dictionary
category: Dictionary
layout: post
---
> [Strings](./strings.html) || [Variables](./variables.html) || [Lists](./lists.html) || [Tuples](./tuples.html) || [Dictionary](./dictionary.html) ||
>  [Control](./control.html) || [Function](./function.html)|| [Files](./files.html) || [OOP](./oop.html) ||

***
### SEQUENCES
- are iterables that support element access using integer indices 

### Dictionaries 
- are indexed by keys.

### Dictionaries Defined
- Data in a dictionary is organized into pairs of keys and values.
- Dictionaries are used to organize elements into collections (like lists). 
- Dictionaries map keys to values and store them in an array or collection.
- The keys must be of a hashable type, which means that they must have a hash value that never changes during the key’s lifetime.

### Syntax
 ```python
	x = {key1:value1, key2:value2} 
```

```python
	x = {} 
	print(type(x))
	<class 'dict'>
```

Unlike lists, you don't access elements inside dictionaries using their position. 
Instead, the data inside dictionaries take the form of pairs of keys and values. 
To get a dictionary value we use its corresponding key. 

You can use a bunch of different data types as keys, like 
strings, integers, floats, tuples, and more. (in a list the index must be a number)

In an English language dictionary the word comes with a definition.
In the language of a Python dictionary, the word would be the key and the definition would be the value.  
example. 


data in a dictionary isn't accessed based on its position. 

You use the key to access the corresponding value. 
Where a list index is always a number, a dictionary key can be a different data type, like a string, integer, float, or even tuples.
When creating a dictionary, you use curly brackets: {}. 
When storing values in a dictionary, the key is specified first, followed by the corresponding value, separated by a colon. For example, animals = { "bears":10, "lions":1, "tigers":2 } creates a dictionary with three key value pairs, stored in the variable animals. The key "bears" points to the integer value 10, while the key "lions" points to the integer value 1, and "tigers" points to the integer 2. 
You can access the values by referencing the key, like this: animals["bears"]. This would return the integer 10, since that’s the corresponding value for this key.
To check if a key is contained in a dictionary using the in keyword. Just like other uses of this keyword, it will return True if the key is found in the dictionary; otherwise it will return False.

Dictionaries are mutable, (can be modified by adding, removing, and replacing elements in a dictionary, similar to lists. 
To add a new key value pair to a dictionary by assigning a value to the key, like this: animals["zebras"] = 2. This creates the new key in the animal dictionary called zebras, and stores the value 2. 

To modify the value of an existing key by doing the same thing. So animals["bears"] = 11 would change the value stored in the bears key from 10 to 11. 

del keyword: To remove elements from a dictionary => del animals["lions"] removes the key value pair from the animals dictionary.



#### Creating initialized dictionaries 
- instead of a series of slots with values in them, we have a series of keys that point at values. 
- use colons and between the key and the value and separate each pair by commas.

#### Example 

```python
file_counts ={"jpeg":10, "txt":14, "csv":2, "py":23}
print(file_counts)
{'jpeg': 10, 'txt': 14, 'csv': 2, 'py': 23}
```

In this file_counts dictionary, we've stored keys that are strings, like jpg, that point at integer values, like 10. 

example 
we're using a dictionary to store the number of files corresponding to each extension. It makes sense to encode the file extension formatting in a string, while it's natural to represent a count as an integer number. 

Let's say you want to find out how many text files there are in the dictionary. 
- use the key txt to access its associated value. 

```python
file_counts = {"jpeg": 10, "txt": 14, "csv": 2, "py": 23}
file_counts["txt"]
#OUTPUT 
14
```

### comment
- in pycharm it doesn’t show 14
- IDLE gives me 14

#### the "**in**" keyword 
 - check if a key is contained in a dictionary
```python
file_counts = {"txt": 14, "csv": 2, "py": 23}
"jpeg" in file_counts
True
"html" in file_counts 
False
```

#### add entry
- Dictionaries are mutable (can add remove and replace entries). 
- To add an entry in a dictionary, just use the square brackets to create the key and assign a new value to it. 

```python
file_counts = {'txt': 14, 'csv': 2, 'py': 23, 'cfg': 8} 
file_counts["cfg"] = 8 
print(file_counts)
# OUTPUT
{'txt': 14, 'csv': 2, 'py': 23, 'cfg': 8} 
```

#### keys inside of a dictionary are unique. 
If we try to store two different values for the same key, we'll just replace one with the other.
When you use a key that already exists to set a value, 
the value that was already paired with that key is replaced. 

```python
file_counts["csv"] = 17
print(file_counts)
# Before
{'txt': 14, 'csv': 2, 'py': 23, 'cfg': 8}
# After
{'txt': 14, 'csv': 17, 'py': 23, 'cfg': 8}
```

#### delete entry
- delete elements from a dictionary with the del keyword by passing the dictionary and the key to the element as if we were trying to access it. 
```python
file_counts ={'jpeg': 10, 'txt': 14, 'csv': 17, 'py': 23, 'cfg': 8}
del file_counts["cfg"]
print(file_counts)
file_counts ={'jpeg': 10, 'txt': 14, 'csv': 17, 'py': 23}
```

### Iterating over the Contents of a Dictionary
- Iterating Through Keys Directly
- Iterating Through .items()
- Iterating Through .keys()
- Iterating Through .values()

#### dir()
To visualize the methods and attributes of any Python object. 
```python 
dir({})
['__class__',  ... , **'__iter__'**, ...]
```
For mappings (like dictionaries), .__iter__() should iterate over the keys: 
=> if you put a dictionary directly into a for loop, 
Python will automatically call .__iter__() on that dictionary, 
and you’ll get an iterator over its keys:

```python
file_counts ={'jpeg': 10, 'txt': 14, 'csv': 17, 'py': 23}
for key in file_counts: 
	print(key)
#OUPUT
jpg
txt
csv
py
```
#### to get access to the values, use the indexing operator [] with the dictionary and its keys
```python
>>> for key in a_dict:
...     print(key, '->', file_counts[key])
jpeg -> 10
txt -> 14
csv -> 17
py -> 23
```
### Iterating Through .items() method 
- returns a new view of the dictionary’s items:
```python
a_dict = {'color': 'blue', 'fruit': 'apple', 'pet': 'dog'}
d_items = a_dict.items()
d_items  # Here d_items is a view of items
dict_items([('color', 'blue'), ('fruit', 'apple'), ('pet', 'dog')])
```
- d_items provides a dynamic view on the dictionary’s entries => when the dictionary changes, the views reflect these changes.
alternative using the **view object** returned by .items():

```python
for item in a_dict.items():
...     print(item)
...
('color', 'blue')
('fruit', 'apple')
('pet', 'dog')
```

```python
for item in a_dict.items():
	print(type(item))
#OUTPUT
('color', 'blue')
<class 'tuple'>
('fruit', 'apple')
<class 'tuple'>
('pet', 'dog')
<class 'tuple'>
```

Now you can do tuple unpacking to iterate through the keys and values of the dictionary you are working with.

```python
for key, value in a_dict.items():
...     print(key, '->', value)
...
color -> blue
fruit -> apple
pet -> dog
# now more readable and Pythonic.
```

values() and .keys() return view objects just like .items(),

### Iterating Through .keys() method
```python
a_dict = {'color': 'blue', 'fruit': 'apple', 'pet': 'dog'}
>>> keys = a_dict.keys()
>>> keys
dict_keys(['color', 'fruit', 'pet'])
```
```python
for key in a_dict.keys():
...     print(key)
...
color
fruit
pet
```
```python
for key in a_dict.keys():
...     print(key, '->', a_dict[key])
...
color -> blue
fruit -> apple
pet -> dog
```

### Iterating Through .values() method
```python
a_dict = {'color': 'blue', 'fruit': 'apple', 'pet': 'dog'}
values = a_dict.values()
values
dict_values(['blue', 'apple', 'dog'])
```
```python
for value in a_dict.values():
...     print(value)
...
blue
apple
dog
```

So if you use a dictionary in a for loop, the iteration variable will go through the keys in the dictionary.
to access the associated values, you can either use the keys as indexes of the dictionary 
or 
you can use the items method which returns a tuple for each element in the dictionary. 
The tuple's first element is the key. 
Its second element is the value. 

```python
file_counts ={'jpeg': 10, 'txt': 14, 'csv': 2, 'py': 23}
for ext, amount in file_counts.items(): 
  print("there are {} files with the .{} extension".format(amount, ext)) 

#OUTPUT
> there are 10 files with the .jpgextension
> there are 14 files with the .txtextension
> there are 2 files with the .csvextension
> there are 23 files with the .pyextension
```

To access the keys of a dictionary or the values with their corresponding dictionary methods
 
```python
print(file_counts.keys())
dict_keys(['jpg', 'txt', 'csv', 'py'])

print(file_counts.values())
dict_values([10, 14, 2, 23])
```
These methods return special data types related to the dictionary. You just need to iterate them as you would with any sequence.
```python 
for value in file_counts.values(): 
   print(value)
10
14
2
23
```
* use items to get key value pairs, file_counts.items()
* keys to get the keys, and file_counts.keys()
* values to get the values. file_counts.values()




### Iterating Over Dictionaries
> You can iterate over dictionaries using a for loop, just like with strings, lists, and tuples. This will iterate over the sequence of keys in the dictionary. 

> to access the corresponding values associated with the keys, you could use the keys as indexes. 
Or 
> you can use the items method on the dictionary, like dictionary.items(). This method returns a tuple for each element in the dictionary, where the first element in the tuple is the key and the second is the value.

> to access the keys in a dictionary, you could use the keys() method on the dictionary: dictionary.keys(). 

> to access the values, you could use the values() method: 
dictionary.values().

***

### learn how to tell when to use dictionaries and when to use lists.

### Dictionaries vs. Lists

When is it best to use a list and when is the dictionary the way to go? 
Think about the kind of information you can represent in each data structure. 
If you've got a list of information you'd like **to collect and use in your script** then the list is probably the right approach. 

For example, 
if you want to store a series of IP addresses to ping, you could put them all into a list and iterate over them. 
ip_addresses = [“192.168.1.1”, “127.0.0.1”, “8.8.8.8”]
Or 
if you had a list of host names and their corresponding IP addresses, you might want to pair them as key values in a dictionary.
host_addresses = {“router”: “192.168.1.1”, “localhost”: “127.0.0.1”, “google”: “8.8.8.8”}

Because of the way dictionaries work, it's super easy and fast **to search for an element** in them. 
Let's say you have a dictionary that has usernames as keys, and the groups they belong to as values. 
It doesn't matter if you have 10 users or 10,000 users, accessing the entry for a given user will take the same time. 
Amazing, but this isn't true for lists. If you've got a list of 10 elements, and you need to check if one element is in the list, it'll be a very fast check but if your list has 10,000 elements it'll take significantly longer to check if the element you're looking for is there. 

So in general, 
- use dictionaries when you plan on searching for a specific element. 

Another interesting difference is the types of values that we can store in lists and dictionaries. 
- In lists, you can store any data type. 
- In dictionaries, we can store any data type for the values but the keys are restricted to specific types. 

### rule of thumb, 
you can use any immutable data type; numbers, booleans, strings and tuples as dictionary keys. 
But you can't use lists or dictionaries for that. 
On the flip side, like we said, the values associated with keys can be any type, including lists or even other dictionaries. You can use them to represent more complex data structures like directory trees in the file system. 

There's a ton of different key value pairs that we need to work with in system administration.
So I use dictionaries all the time. They're especially useful with large data sets. 
When I need to write a script that gets specific keys out of it to manipulate or modify the associated value.

In Python, a dictionary can only hold a single value for a given key. 
To workaround this, our single value can be a list containing multiple values. 
A dictionary called "wardrobe" with items of clothing and their colors. 
Fill in the blanks to print a line for each item of clothing with each color, for example: "red shirt", "blue shirt", and so on.

```python
wardrobe = {"shirt":["red","blue","white"], 
			"jeans":["blue","black"]}
for key, value in wardrobe.items():
    for i in value:
        print("{} {}”.format(value, key))

#Output:
['red', 'blue', 'white'] shirt
['red', 'blue', 'white'] shirt
['red', 'blue', 'white'] shirt
['blue', 'black'] jeans
['blue', 'black'] jeans
```

```python
wardrobe = {"shirt":["red","blue","white"], 
			"jeans":["blue","black"]}
for key, value in wardrobe.items():
    for i in value:
        print("{} {}”.format(i, key))

# Output:
# red shirt
# blue shirt
# white shirt
# blue jeans
# black jeans
```

*** 

| Operations        |  what it does          | 
|:-------------|:------------------|
| len(dictionary)           | Returns the number of items in the dictionary | 
| for key in dictionary | Iterates over each key in the dictionary   | 
| for key, value in dictionary.items() | Iterates over each key,value pair in the dictionary | 
| if key in dictionary           | Checks whether the key is in the dictionary | 
| dictionary[key] | Accesses the item with key key of the dictionary | 
| dictionary[key] = value | Sets the value associated with key | 
| del dictionary[key] | Removes the item with key key from the dictionary | 


| Methods        | what it does         |
|:-------------|:------------------|
| dict.get(key, default) | Returns the element corresponding to key, or default if it's not present |
| dict.keys() | Returns a sequence containing the keys in the dictionary   | 
| dict.values() | Returns a sequence containing the values in the dictionary  | 
| dict.update(other_dictionary) | Updates the dictionary with the items coming from the other dictionary. Existing entries will be replaced; new entries will be added. | 
| dict.clear()           | Removes all the items of the dictionary | 

[documentation for dictionary operations and methods](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)

*** 


### Tutorial 
*  [docs.python.org](http://docs.python.org/tutorial/)

### Style Guide for Python Code
* [python.org](http://www.python.org/dev/peps/pep-0008/)


#### Formatting
- can be messy with all the quotation marks.
- single for the dict and double for formatting. 

```python
>>> comedian = {'name': 'Eric Idle', 'age': 74}
>>> f"The comedian is {comedian['name']}, aged {comedian['age']}."
The comedian is Eric Idle, aged 74.
```