# Python Notes

This repo will contain short notes, snippets, challenges and solutions I encounter while learning Python.

## Why I'm learning Python

Javascript is a great language and I know enough to be dangerous (majorly React and some NodeJS on the backend). There's abundance of jobs with this stack. I would even argue most programming jobs come in this stack. Despite this, limiting myself to Javascript is a bad idea. Here's a few facts I've understood lately

- Extremely good engineers are not bound by languages
- More languages help build a stronger CS background
- Python is great for futuristic stuff

So I'm giving this a shot 🔫. I'll start by going atleast 2 hours daily and will begin with [this tutorial](https://www.youtube.com/playlist?list=PL-osiE80TeTt2d9bfVyTiXJA-UTHn6WwU)

The main reason I'm documenting these is to atleaset, help one person learning Python in the future.

---

## Installing Python on Windows

![Python download](/images/python-download.png)

- Go to the [Python website](https://www.python.org/)
- Download the latest version
- Run the `exe`. Usually named `python-3.9.4-amd64.exe`

  > Ensure you check the `Add Python to PATH` option before installations.

   <br>

  ![Installation option](images/python-installation-options.png)

- To confirm installation, open command prompt and type `python --version`

> I'm aware there can be a lots of problems during installation, I'm thankful I haven't faced any yet. I'll update this document if I do.

## Running my first Python program

- Created a file `hello-world.py` and added the following
- compiled the typescript `python ./hello-world.py` in the terminal runs the code in the `hello-world.py` file.

```py
print('Hello world')

# outputs Hello World
```

## Working with Textual Data (Strings)

- Python does not use semi-colons 💃🏼 and operates on white spaces only
- `snake_case` is the convention for naming variables in python
- variables are declared without any keywords (That's weird coming from Javascript)

```py
hello_world = 'Hello world'
print(hello_world)
```

- print multi-sentence sentences by using triple semi-colons instead

```py
hello_message = """Paragraph across many
lines"""

print(hello_message)

# prints
# Hello world
```

- We can use single or double quotes interchangeably depending on if double or single quotes are used in the string

```py
hello_message = 'Hello"s world' # Single quotes because double quotes are used in sentence
hello_message2 = "Hello's world" # Double quotes because single quotes are used in sentence

print(hello_message)
print(hello_message2)

# prints
# Hello World
# Hello World
```

- We can escape characters too

```py
hello_message = 'Hello\' world'

print(hello_message)
# prints
# Hello' world
```

- get the length of a string with the `leng()` function

```py
hello_message = 'Hello world'

print(len(hello_message))
# prints 11
```

- **String indexes**: Strings are just like arrays and we can access characters at different indexes.

```py
hello_message = 'Hello world'

print(hello_message[0])
# prints H
```

### Strings Slicing in Python

- We can also print a range from a string. More like the `substr()` function in Javascript

```py
hello_message = 'Hello world'

# prints from 0 - 4th index of the string (excluding 4th index)
print(hello_message[0:4])
# prints Hell
```

- Leaving out the zero in the index will still produce the same result.

```py
hello_message = 'Hello world'

# prints from 0 - 4th index of the string (excluding 4th index)
print(hello_message[:4])

# prints from the 6th index to the end of the string
print(hello_message[6:])
# prints Hell
# prints world
```

- uppercase and lowercase strings with the `upper()` and `lower()` methods on the string. This is also very similar to what `toUpperCase()` and `toLowerCase()` in javascript.

```py
hello_message = 'Hello World'
print(hello_mesage.tolower())
print(hello_mesage.upper())

# prints
# hello world
# HELLO WORLD
```

- If we want to count the occurrence of characters in a string, we use the `count()` method

```py
hello_message = 'Hello world'
print(hello_message.count('l'))

# prints 3
```

- We can get the index of certain characters by using the `find()` method passing in the character to find. It prints the index of just the first occurrence and returns 0 if it doesn't exist.

```py
hello_message = 'Hello world'
print(hello_message.find('w'))
print(hello_message.find('z'))

# prints 3
# prints -1
```

- The `replace()` function exists to replace sections of a string

```py
hello_message = 'Hello World'

new_message = hello_message.replace('World', 'Universe')

print(new_message)

# prints Hello Universe
```

### Concatenating multiple strings

- We can format string output with the `format()` method to avoid manually concatenating strings

```py
greetings = 'Hello'
name = 'Micheal'
message = '{}, {}. Welcome!'.format(greeting, name)

print(message)
```

- `F-strings` in Python allow robust manipulation of strings. More like backticks in Javascript

> F-strings are available only in Python 3.6 and above

```py
greeting = 'Hello'
name = 'Micheal'

message = f'{greeting}, {name}. Welcome!'
print(message)
# Hello, Micheal. Welcome!

```

- We can also write code inside of the F-strings

```py
greeting = 'Hello'
name = 'Micheal'

message = f'{greeting}, {name.upper()}. Welcome!'
print(message)
# Hello, Micheal. Welcome!

```

### dir and help functions

- We can find out available functions on a function by using the `find` and `help` functions.

```py
name = 'Micheal'

# available methods on a string
print(dir(name))

# available methods on a type
print(help(str.lower))

# Prints out a lot of things 🤷🏼‍♀️
```

---

## Integers and Floats

- In Python, numbers are normally represented in Integer & floats. An integer is a whole number and a float is a decimal.
- Python has a `type()` function that prints out the type of a value. Similar to `typeof` operator in javascript

```py
num = 3
float_num = 3.14

print(type(num))
print(type(float_num))

# prints
# <class 'int'>
# <class 'float'>
```

- basic arithmetics in Python

```py
# addition 3+2 = 5
# subtraction 3-2 = 1
# multiplication 3*2 = 6
# division 3/2 = 1.5
# division without remainder 3//2 = 1
# power 3**2 = 9
# modulus 3%2 = 1 (returns only the remainder of a division)
```

> **Differences between the `/` and `//` sign**. The `/` sign divides and returns the remainder (3/2 = 1.5) while the `//` returns just the whole number and throws away the remainders (3//2 = 1).

- We can get the absolute value of a number (remove the negative sign) with the `abs` function(). Also round up decimal numbers with the `round()` function. `round` takes a second argument that specifies the number of numbers after the digit (places).

```py
print(abs(-3.4))
print(round(3.75))
print(round(3.75, 1))

# prints
# 3.4
# 4
# 3.8
```

### Conditional operators

- Most conditional operators will return a boolean: either `true` or `false`

```py
# Equal: 3 == 2 =
# Not Equal: 3 != 2
# Greater Than: 3 > 2
# Less Than: 3 < 2
# Greater or Equal: 3 >= 2
# Less or Equal: 3 <= 2
```

- cast a string to an integer by using the `int()` function

```py
num_1 = '100'
num_2 = '200'

num_1 = int(num_1)
num_2 = int(num_2)

print(num_1 + num_2)
```

## Lists, Tuples and Sets

- Lists and tuples allow us to work with sequencial data and sets are unordered collection of values with no duplicates.

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

print(courses[0:3])
print(courses[3:])
print(courses[:])

# prints
# ['History', 'Math', 'Physics']
# ['Computer Science']
# ['History', 'Math', 'Physics', 'Computer Science']

```

- We can add a new member to a list with the `append()` & `insert()` methods

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

# insert the new member at the specified index
courses.insert(0, 'Art')
print(courses)

# insert the new member at the end of the array
courses.append('Art')
print(courses)

# prints
# ['Art', 'History', 'Math', 'Physics', 'Computer Science']
# ['Art', 'History', 'Math', 'Physics', 'Computer Science', 'Art']
```

- We can combine multiple arrays into one with the `extend()` method. Much like `Array.flat()` in javascript.

```py
courses_1 = ['History', 'Math', 'Physics', 'Computer Science']
courses_2 = ['History', 'Math', 'Physics', 'Computer Science']
courses_add = ['Art', 'Education']

courses_1.insert(0, courses_add)

print(courses_1)
# prints
#

courses_2.extend(courses_add)
print(courses_2)

# [['Art', 'Education'], 'History', 'Math', 'Physics', 'Computer Science']
# ['History', 'Math', 'Physics', 'Computer Science', 'Art', 'Education']
```

- remove values from a list with the `remove()` method

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

courses.remove('Math')
print(courses)

# ['History', 'Physics', 'Computer Science']
```

- The `pop()` method removes the last value from our list

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

# we can also get the popped out value
popped = courses.pop()

print(popped)
print(courses)

# prints
# Computer Science
# ['History', 'Physics', 'Computer Science']

```

- There's a `reverse()` method on lists that reverses them.

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

# we can also get the popped out value
courses.reverse()
print(courses)

# ['Computer Science', 'Physics', 'Math', 'History']
```

- `sort()` method sorts lists

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

# sorts the list alphabetically by default if it's text and by magnitude if it's a number
courses.sort()
print(courses)

# ['Computer Science', 'History', 'Math', 'Physics']
```

- We can change the order to descending by passing `reverse=True` to the `reverse()` and `sort()` function

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

courses.sort(reverse=True)
print(courses)

# ['Physics', 'Math', 'History', 'Computer Science']
```

- Most times, you'd not want to alter the initial list, but create a new version of the list. We can use the `sorted()` function to do that instead.

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

sorted_courses = sorted(courses)
print(courses)
print(sorted_courses)


# ['Physics', 'Math', 'History', 'Computer Science']
# ['Computer Science', 'History', 'Math', 'Physics']
```

- other utility lists methods

```py
nums = [1, 2, 3, 4, 5]

# print the minimum of nums
print(min(nums))

# print the maximum of nums
print(max(nums))

# print the sum of nums
print(sum(nums))

# prints
# 1
# 5
# 15
```

- Find the index of a value in list with the `index()` nethod

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

print(courses.index('Computer Science'))
# prints 3
```

- There's also an easier way to know if a value exists in an array with the `in` construct

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

print('Art' in courses)
# prints False
```

- the `join()` function can be used to break up an array into a string separated by any value

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

courses_str = ', '.join(courses)
courses_str_1 = ' - '.join(courses)

print(courses_str)
print(courses_str_1)

# prints
# History, Math, Physics, Computer Science
# History - Math - Physics - Computer Science
```

- We can furthermore convert a string back to an array

```py
courses = ['History', 'Math', 'Physics', 'Computer Science']

courses_str = ' - '.join(courses)
new_list = courses_str.split(' - ')

print(courses_str)
print(new_list)

# prints
# History - Math - Physics - Computer Science
# ['History', 'Math', 'Physics', 'Computer Science']
```
