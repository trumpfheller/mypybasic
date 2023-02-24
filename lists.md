---
title: Lists
category: Lists
layout: post
---

***

> [Strings](./strings.html) || [Variables](./variables.html) || [Lists](./lists.html) || [Tuples](./tuples.html) || [Dictionary](./dictionary.html) ||
>  [Control](./control.html) || [Function](./function.html)|| [Files](./files.html) || [OOP](./oop.html) ||

***

### SEQUENCES
- Strings are sequences of characters and are immutable. 
- Lists are sequences of elements of any type and are mutable. 
- Tuples are sequences of elements of any type that are immutable.
- Methods used
    - iterating over them using for-loops, 
    - indexing using the len function to know the length of the sequence, 
    - using plus to concatenate two sequences and 
    - using in to verify if the sequence contains an element. 

- Sequences have similar properties, like 
    * being able to iterate over them using for loops; 
    * support indexing; 
    * using the len function to find the length of the sequence; 
    * using the plus operator + in order to concatenate; and 
    * using the in keyword to check if the sequence contains a value.

#### Common sequence operations
* len(sequence) 
    - Returns the length of the sequence
* for element in sequence 
    - Iterates over each element in the sequence
* if element in sequence 
    - Checks whether the element is part of the sequence
* sequence[i] 
    - Accesses the element at index i of the sequence, starting at zero
* sequence[i:j] 
    - Accesses a slice starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(sequence) by default.
* for index, element in enumerate(sequence) 
    - Iterates over both the indexes and the elements in the sequence at the same time

### List
- Lists are ordered.
    - the items have a defined order, and that order will not change.

### Lists Defined
- Define lists by using square brackets and the elements stored in the list separated by commas: 
```python
	list = ["This", "is", "a", "list"]. 
    #its contents is a list of strings.
```

#### Common list operations
- len(list) 
    * returns the number of elements in a list: would return 4. 

- to check the type of x using the type function 
	```python
    type(x)
	<class list>
    ```
- print function: 
    - to show the contents of the whole list. 

- keyword “in”: 
    - to check if a list contains a certain element 
        * If the element is present, it will return a True boolean. 
        * If the element is not found in the list, it will return False.  
    - result of this check is a Boolean, which we can use as a condition for branching or looping.
#### Example
 ```python
	x = ["This", "is", "a", "list"]
    "Today" in x
    #OUTPUT
    False
    #"This" in list would return True.
```

* indexing 
    
    Syntax
    ```
    list.index(elmnt)
    ```
    - to access individual elements depending on their position in the list: 
        - use the index we want to access (like with strings). 
        - if we try to access an element after the end of the list We get an index error. We can't go over the end of the list. 

    ```python
        fruits = ['apple', 'banana', 'cherry']
        x = fruits.index("cherry")
        print(x)
        #OUTOUT
        2
    ```

* slice
    - use indexes to create a slice of the list. 
``` 
x[1:3] 
```
So the range starts at index one and goes up to the second index minus one.
``` 
x[:2] 
```
First value defaults to zero and the second value to the length of the list.

* split() method 
    - splits a string into a list.

    ```python
        # Example 1
        txt = "welcome to the wild"
        x = txt.split()
        print(x)

        #OUTPUT
        #['welcome', 'to', 'the', 'wild']
    ```


### Modifying Lists
Most of these methods come from the fact that lists are mutable sequences.
* lists are mutable (we can add, remove, or modify elements in a list.) 
* strings are not mutable. 
* Changing the list means we keep the same box and we add, remove, or change the elements inside that box.

#### List-specific methods [w3schools](https://www.w3schools.com/python/python_ref_list.asp)

| method | what it does |  
|:-------------|:------------------| 
| list[i] = x | Replaces the element at index i with x |  
| list.append(x) | Inserts x at the end of the list |  
| list.insert(i, x) | Inserts x at index i |  
| list.pop(i) | Returns the element a index i, also removing it from the list. If i is omitted, the last element is returned and removed. | 
| list.remove(x) | Removes the first occurrence of x in the list | 
| list.sort() | Sorts the items in the list | 
| list.reverse() | Reverses the order of items of the list | 
| list.clear() | Removes all the items of the list | 
| list.copy() | Creates a copy of the list | 
| list.extend(other_list) | Appends all the elements of other_list at the end of list | 


#### append() method 

- adding an element to a list (adds a new element at the end of the list.)
- list.append("New data") would add the string "New data" to the end of the list.

```python
	fruits = ["apple", "banana", "cherry"]
	fruits.append("orange")
	print(fruits)
	['apple', 'banana', 'cherry', 'orange']
```

#### insert() method
- If you want to add an element to a list in a specific position, instead of at the end.
- The method takes two parameters: 
    - an index as the first parameter 
    - element as the second parameter. 

```python
list.insert(0, "New data") 
```
- would add the string "New data" to the front of the list. 
- This wouldn't overwrite the existing element at the start of the list. 
- It would just shift all the other elements by one. 
- If you specify an index that’s larger than the length of the list, the element will simply be added to the end of the list.

```python
fruits = ["Pineapple", "Banana", "Apple", "Melon"]
fruits.insert(0,"Orange")
print(fruits)
["Orange", "Pineapple", "Banana", "Apple", "Melon"]
```
What happens if we use a number larger than the length of the list?
```python
fruits.insert(25,"Peach")
print(fruits)
["Orange", "Pineapple", "Banana", "Apple", "Melon", "Peach"]
```
No errors. If an index higher is than the current length, the element just gets added to the end. Y
- usually, you either 
    - add at the beginning using insert() at the zero index 
    - add at the end using append(). 

```python 
fruits = ["Orange", "Pineapple", "Banana", "Kiwi","Peach"]
fruits[2] = "Strawberry"
print(fruits)
["Orange", "Pineapple", "Strawberry", "Banana", "Kiwi","Peach"]

```

#### replace via indexing
you can change an element in a list
to overwrite the value stored at the specified index. 
For example, you can enter 
```python
    list[0] = "Old data" 
```
    to overwrite the first element in a list with the new string "Old data".

#### pop() method 
* Another way we can remove elements 
* method receives an index.
* pop method returns the element that was removed at the index that was passed.
* to change an item by assigning something else to that position, 
Syntax
    ```
    list.pop(pos)
    ```

```python
fruits = ["Orange", "Pineapple", "Banana", "Apple"]
fruits.pop(3)
print(fruits)
["Orange", "Pineapple", "Banana"]
```

#### remove() method
- remove elements from the list using the value of the element we want to remove. 
- removes the first occurrence of the element from the list.
- If the element is not in the list - we get a value error ("element isn't in the list"). 

- Syntax 
    ```python
        list.remove(elmnt)
    ```
This method takes an element as a parameter, and removes the first occurrence of the element. 
If the element isn’t found in the list, you’ll get a ValueError error explaining that the element was not found in the list.

```python
fruits = ["Orange", "Pineapple", "Banana", "Apple"]
fruits.remove("Apple")
print(fruits)
["Orange", "Pineapple", "Banana"]
```

#### same result accomplished with pop()
```python
	fruits = ['apple', 'banana', 'cherry']
	fruits.pop(1)
	print(fruits)
	['apple', 'cherry']
```
This method differs from the remove method in that it takes an index as a parameter, and returns the element that was removed. 
This can be useful if you don't know what the value is, but you know where it’s located. 
This can also be useful when you need to access the data and also want to remove it from the list.

#### Use cases
- If the list contains hosts on a network, you could add or remove hosts as they come online or offline. 
- If the list contains users authorized to run a certain process, you could add or remove users when permissions are granted or removed and so on. 
- you'll use a list whenever you need to write a program that'll handle a variable amount of elements
- You will use whenever you need to write a programm that'll handle a sequence of a fixed amount of elements.

#### reversed() method
-  specify the sequence in a forward direction
```python
    for i in reversed(range(1, 10, 2)):
        print(i)
#OUTPUT
9
7
5
3
1
```

#### extend() method.
- adds the specified list elements (or any iterable) to the end of the current list.

```python
	fruits = ['apple', 'banana', 'cherry']
	cars = ['Ford', 'BMW', 'Volvo']
	fruits.extend(cars)
	print(fruits)
	['apple', 'banana', 'cherry', 'Ford', 'BMW', 'Volvo']
```


#### Enumerate - [Iterating Over Lists](https://docs.python.org/3/tutorial/datastructures.html?highlight=enumerate)
- When looping through a sequence, the position index and corresponding value can be retrieved at the same time.
- to access the elements in a list, along with the index of the element in question.
- takes a list as a parameter and returns a tuple for each element in the list. 
The first value of the tuple is the index and the second value is the element itself.

```python
>>> for i, v in enumerate(['tic', 'tac', 'toe']):
...     print(i, v)
0 tic
1 tac
2 toe
```

#### List Comprehensions
- creating lists in a shorter way. 
- create new lists based on sequences or ranges.
-  to create a list based on a range like in this example. Or based on the contents of a list a tuple a string or any other Python sequence. 
- The syntax tries to copy how you would express these concepts with natural language. 

Syntax: 
```
newlist = [expression for item in iterable if condition == True]
```

to create a list with multiples of 7 from 7 to 70.
```python
multiples = []
	for x in range(1,11):
	multiples.append(x*7)
print(multiples)
[7, 14, 21, 28, 35, 42, 49, 56, 63, 70]
```
=> same in just one line - with list comprehension.
```python
multiples = [ x * 7 for x in range(1,11)] 
print(multiples)
[7, 14, 21, 28, 35, 42, 49, 56, 63, 70]
```


#### Example #2 
* a list of strings with the names of programming languages 
* generate a list of the length of the strings. 

We could iterate over the list and add them using a pen like we did before. 
```python
languages = ["Python", "Ruby", "Java", "Perl", "Go"]
lengths = [len(language) for language in languages]
print(lengths)
[6, 4, 4, 4, 2]
```
Or we could use a list comprehension like this

#### List comprehensions and conditional clause. 
* all the numbers that are divisible by 3 between 0 and a 100. 

```python
z = [x for x in range(0,101) if x % 3 == 0] 
print(z)
[0, 3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, 36, 39, 42, 45, 48, 51, 54, 57, 60, 63, 66, 69, 72, 75, 78, 81, 84, 87, 90, 93, 96, 99]
```
In this case we just want the element x to be a part of the list, 
but we only want the numbers where the remainder of the division by 3 is 0. 
So we add the conditional clause after the range. 

Using list comprehensions when programming in Python is totally optional. 
Sometimes it can make the code look nicer and more readable, at other times it can have the opposite effect, 
especially if we try to pack too much information together. 
In general, it's a good idea to know that list comprehensions exist, 
especially when you're trying to understand someone else's code. 

to create a new list from a sequence or a range in a single line 
[You can create lists from sequences using a for loop].
For example,
```python
	x*2 for x in range(1,11) 
```
This would iterate over the range 1 to 10, and multiply each element in the range by 2. This would result in a list of the multiples of 2, from 2 to 20.

 to build even more complex and powerful statements: appending an if statement to the end of the comprehension. 
 ```python
	x for x in range(1,101) if x % 10 == 0 
```
would generate a list containing all the integers divisible by 10 from 1 to 100. The if statement we added here evaluates each value in the range from 1 to 100 to check if it’s evenly divisible by 10. If it is, it gets added to the list.

List comprehensions can be really powerful, but they can also be super complex, resulting in code that’s hard to read. Be careful when using them, since it might make it more difficult for someone else looking at your code to easily understand what the code is doing.



[expression for variable in sequence] Creates a new list based on the given sequence. Each element is the result of the given expression.
[expression for variable in sequence if condition] Creates a new list based on the given sequence. Each element is the result of the given expression; elements only get added if the condition is true. 



***

#### For more info 
* [pythong.org - lists](https://docs.python.org/3/library/stdtypes.html#lists)
* [pythong.org - mutable-sequence-type](https://docs.python.org/3/library/stdtypes.html#mutable-sequence-types)
* [w3schools - comprehension](https://www.w3schools.com/python/python_lists_comprehension.asp)




