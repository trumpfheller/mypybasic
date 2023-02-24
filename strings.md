---
title: Strings
category: Strings
layout: post
---
> [Strings](./strings.html) || [Variables](./variables.html) || [Lists](./lists.html) || [Tuples](./tuples.html) || [Dictionary](./dictionary.html) ||
>  [Control](./control.html) || [Function](./function.html)|| [Files](./files.html) || [OOP](./oop.html) ||

***
### What is a string? 
- is a data type that's used to represent a piece of text. 
- It's written between quotes, either double quotes or single quotes. 
- can be as short as zero characters, usually called an empty string or really long. 
- strings are immutable.

```python
name = "Mike"
pet = ""
Pet = 'looooooooooooooooooooooooong cat'
```
### Operations

| String operations        | what it does          
|:-------------|:------------------|
| len(string) | Returns the length of the string | 
| for character in string | Iterates over each character in the string   | 
| if substring in string           | Checks whether the substring is part of the string      | 
| string[i]           | Accesses the character at index i of the string, starting at zero | 
| string[i:j]           | Accesses the substring starting at index i, ending at index j-1. If i is omitted, it's 0 by default. If j is omitted, it's len(string) by default. |

#### Concatenating
- using the plus sign to build longer strings.

#### len function
- the number of characters contained in the string. 

#### Example
Modify the double_word function so that it returns the same word repeated twice, followed by the length of the new doubled word. => double_word("hello") should return hellohello10.

```python
def double_word(word):
	return word + word + str(len(word) * 2)

    return

print(double_word("hello")) 
# Should return hellohello10
print(double_word("abc"))   
# Should return abcabc6
print(double_word(""))      
# Should return 0
```

#### substring in string

```python
pets = "Cats & Dogs"
"Dragons" in pets
	False
```


#### String Indexing and Slicing
- to access just a specific character or characters? 
- to access a portion of a string, called a slice or a substring
- using square brackets and the location, or index, of the character you want to access. 


```python
	name = "Mike"
	print(name[2])
	#OUTPUT
	k
```

```python
fruit = "Mangosteen"
fruit[1:4]
#OUTPUT
'ang'

fruit[:5]
#OUTPUT
'Mango'
```

```python
fruit = "Pineapple"
print(fruit[:4])
# OUTOUT
Pine
print(fruit[4:])
# OUTOUT
apple
```

#### negative indexes. 

```python
text = "Random staring with a lot of characters"
print(text[-1])
print(text[-2])
OUTPUT
s
r
```

- don't know the length of the string (it doesn't matter). 
- Negative indexes lets us access the positions in the string starting from the last. 
- If you try to access an index that’s larger than the length of your string, you’ll get an IndexError.

#### Changing a character in a string
- strings in Python are immutable. => create a new string based on the old one.
- You don't replace a string, but create a new variable.

```python
message = "A kong string with a silly typo"
new_message = message[0:2] + 'l' + message[3:]
print(new_message)
A long string with a silly typo
```


#### index() Method Find character to change
- how are we supposed to know which character to change? 
- returns just the first position that matches.

```python
pets = "Cats & Dogs"
pets.index("&")
# OUTPUT
5
```


### String methods

| String methods | what it does | 
|:-------------|:------------------|:------|
| string.lower() / string.upper()           | Returns a copy of the string with all lower / upper case characters | 
| string.lstrip() / string.rstrip() / string.strip() | Returns a copy of the string without left / right / left or right whitespace   | 
| string.count(substring)           | Returns the number of times substring is present in the string      | 
| string.isnumeric()           | Returns True if there are only numeric characters in the string. If not, returns False. | 
| string.isalpha()           | Returns True if there are only alphabetic characters in the string. If not, returns False. |
| string.split() / string.split(delimiter)           | Returns a list of substrings that were separated by whitespace / delimiter | 
| string.replace(old, new) | Returns a new string where all occurrences of old have been replaced by new.   | 
| delimiter.join(list of strings)           | Returns a new string with all the strings joined by the delimiter       | 

- string method lower will return the string with all characters changed to lowercase.
- The inverse of this is the upper method, which will return the string all in uppercase. Just like with previous methods, we call these on a string using dot notation, like "this is a string".upper(). This would return the string "THIS IS A STRING". This can be super handy when checking user input, since someone might type in all lowercase, all uppercase, or even a mixture of cases.
- strip method to remove surrounding whitespace from a string. Whitespace includes spaces, tabs, and newline characters. 
- lstrip and rstrip methods to remove whitespace only from the left or the right side of the string, respectively.
- count() method can be used to return the number of times a substring appears in a string. This can be handy for finding out how many characters appear in a string, or counting the number of times a certain word appears in a sentence or paragraph.
- endswith() method: to check if a string ends with a given substring. This will return True if the substring is found at the end of the string, and False if not.

```python
"Forest".endswidth("rest")
#OUTPUT
True

txt = "Hello, welcome to my world."
x = txt.startswith("Hello")
print(x)
```

- The isnumeric method can check if a string is composed of only numbers. If the string contains only numbers, this method will return True. We can use this to check if a string contains numbers before passing the string to the int() function to convert it to an integer, avoiding an error. Useful!

#### string.lower() method

```python
answer = 'YES'
	if answer.lower() =="yes":
		print("User said yes")
```


[docs.python.org](https://docs.python.org/3/library/stdtypes.html#string-methods)

***

### Formatting

[w3schools](https://www.w3schools.com/python/python_string_formatting.asp)

#### %-formatting

```pyton
>>> name = "Eric"
>>> "Hello, %s." % name
'Hello, Eric.'
```
#### str.format()

```python
>>> person = {'name': 'Eric', 'age': 74}
>>> "Hello, {name}. You are {age}.".format(name=person['name'], age=person['age'])
'Hello, Eric. You are 74.'
```


#### f-Strings
```python
>>> name = "Eric"
>>> age = 74
>>> f"Hello, {name}. You are {age}."
'Hello, Eric. You are 74.'
```

```python
>>> name = "Eric"
>>> profession = "comedian"
>>> affiliation = "Monty Python"
>>> message = (
...     f"Hi {name}. "
...     f"You are a {profession}. "
...     f"You were in {affiliation}."
... )
>>> message
'Hi Eric. You are a comedian. You were in Monty Python.'
```

### print() function
```python
# basic print() function
values=["one", "two", "three", "four", "five"]
print(*values)

# use the 'sep' argument to control the separator between values:
print(*values, sep=' -- ')

# use the 'end' argument to control the line ending characters
# let's auto-print the current line number along with each item!
for i in range(0, len(values)):
    print(values[i], end=f" [line: {str(i+1)}]\n")

# you can even redirect print() output to a file:
newfile = open("output.txt","w")
print(*values, sep=' -- ', file=newfile, flush=True)
newfile.close()

```
> [docs.python](https://docs.python.org/3/library/functions.html#print)