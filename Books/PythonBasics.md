# [Python Basics](https://www.goodreads.com/book/show/43448128-python-basics-dan-bader?ref=nav_sb_ss_4_13) by David Amoz

### Table of Contents

- [Python Basics](#Python-Basics)
    + [Table of Contents](#table-of-contents)
    + [Chapters 1-4](#chapters-1-4)
    + [Strings](#strings)
    + [Chapter 5](#chapter-5)
    + [Chapter 6](#chapter-6)
    + [Logic and Control Flow](#logic-and-control-flow)
      - [The Basics](#the-basics)
      - [Some Other Keywords](#some-other-keywords)
      - [Flow Control](#flow-control)
      - [Error Handling](#error-handling)
    + [Tuples, Lists, and Dictionaries](#tuples--lists--and-dictionaries)
      - [Tuples](#tuples)
      - [Lists](#lists)
      - [Extras](#extras)
      - [Dictionaries](#dictionaries)
      - [When To Use Each](#when-to-use-each)
    + [Object-Oriented Programming (OOP)](#object-oriented-programming--oop-)
      - [Classes](#classes)

### Chapters 1-4

*Skipped the first three chapters for prior knowledge.*

### Strings

**Data type** refers to what *kind* of data a value represents. A **string** (abbr. `str`) is a data type, equivalent to text. There are also fundamental data types—data types that can not be further broken down into smaller values of a different type. An example of a non-fundamental data type would also be a string: a string is a sequence of *characters*, and thus can be broken down into characters. 

Strings have three main properties:

1. They contain characters, as in, they are made up of individual letters or symbols.
2. Strings have a length, as in, the number of characters that make up the string.
3. And these characters are ordered in a sequence to form the relevant text, as in, each character has a numbered position in the string.

Strings can be created by surrounding some text in quotation marks. They can be both single and double quotes. Thes quotes are called delimiters; they limit its beginning and end so that the computer can understand where it begins and ends.

A string written out and surrounded in double quotes in your code is called a string literal. This is different from, say, a user inputted string because that *is not* written explicitly in your code.

Because python reads first for one delimiter and ends the string when it encounters the next, you can not use double quotes inside a double quotes delimited string.

e.g: Bad = print("Hello, "world"!"). Here, python thinks the string begins before 'H' and ends before 'w', Then, it reads 'world' and finds another string: "!". This leaves it with a non-variable word, world, which it can not interpret and the "!" which is not concatenated. Thus, it returns an error.

Instead, you should use single quotes in double quotes delimited strings and vice versa. e.g: print("Hello, 'world'!") or print('Hello, "world"!')

For strings that you want to take up multiple lines, you can add \n to a given point within the string to force the rest of the text to print on a newline. You can also use """ or ''' delimiters and just type on a newline as if you were writing in a word processor. Triple codes are less commonly used than newlines for multiline strings. Their main application is actually as comments and code descriptions.

As mentioned above, the second property of strings is that they have a length of characters. This can be determined with the function len(value). Using 'abc' as a parameter, the function returns a 3. You can also use this on variables.

There are three basic operations that you can perform on a string: concatenation, indexing, and slicing.

Two strings are combined, concatenated, with then + operator in much the same way as addition.

Since strings are merely sequences of characters and are *indexed*, ordered, with numbers, you can access a character by giving its index. For example, if you wanted to know the 5th character in a string, you would do:
- o = "orange"
  o[4] # Python is offset by -1 and starts counting at zero so 4 is actually the fifth letter if you count from one
- The result would be 'g'
- If you wanted to count from left-to-right, as opposed to right-to-left, you would use negative numbers.
- o[-1] would be e, and o[-2] would be g, etc

If you wanted to index multiple characters at once, you could use normal indexing or slicing
- ora = o[0] + o[1] + o[2] # Normal indexing
- ora = o[0:3] # Slicing
- Both return 'ora', but one is more efficient
- Note that slicing does index a bit differently. Instead of counting the first index number you ask it to (0, in our case) and ending with (3, in our case), it uses the two numbers as delimiiters and returns every string between them. You could view it as: string[start:end]

Finally, note that strings are immutable. Immutability means that they can not be *changed*. When you attempt to alter a character in a string (e.g: o[1] = 'a') it will return an error. You can, of course, just define it again (e.g: o = 'oaange') but this doesn't change the old string, **it creates an entirely new one with the same name**.

You can change a string's case with .lower() or .upper() method. 

You can remove whitespace with:
- .rstrip() removes all whitespace from the right of a string
- .lstrip() removes all whitespace from the left of a string
- .strip() removes whitespace from both sides of a string

Determine what characters a string starts with using the .startswith() method

You can take string input using the input() function

You can also assign input() to a variable after which the interpreter will immediately ask for an input from the user and assign it to the variable.
- e.g:
	age = input()
	print("How old are you? " + age)

Input() takes strings as inputs. You can not perform arithmetic operations on them. To convert an input() string into an integer, put the input within int() or float(). If the user inputs a floating point and you try to convert it using int(), it wil return a ValueError!

You can do the opposite using the str() function. In an f-string, they are automatically converted.
- e,g: str(age) # an example of str() function
- e.g: f"You are {age} years old." # an example of an f-string

You can find a string within a string, also known as a substring, using the .find() method on the main string and inserting the substring in the brackets. Find returns a -1 if it doesn't find the string. 

### Chapter 5

- Python has three numerical data types:
	- Integers - positive or negative whole numbers
		- defined with int() or by simply typing the number without any quotes
		- you can use underscores (_) to separate triple digits, like commas in normal arithmetic
			- e.g: 1_000_000 = 1,000,000 or 1000000

	- Floating points - a number with a decimal place
		- defined with float() or by explicitly giving a number decimal values
	
	- Complex numbers

- Arithmetic can be performed with the same operators
	- + for addition
		- e.g: 1 + 2 >> 3
	- - for subtraction
		- e.g: 2 - 1 >> 1
	- * for multiplication
		- e.g: 2 * 3 >> 6
	- / for division 
		- e.g: 6 / 2 >> 3
	- // for integer division, where the numbers are divided and the product rounded down
		- e.g: 6,0 // 2 >> 3.0
	- ** for exponentiations
		
		- e.g: 2 ** 2 >> 4
	- % for returning the remainder of a division operation
		- e.g: 5 % 3
	
- Asides from basic arithmetic, you can also write complex expressions
	- e.g: 2 * 3 - 1 >> 5
	- These follow the order of operations; known by BODMAS, BIDMAS, etc.

- There are a number of functions and methods to do with numbers
	- round() rounds a number to the nearest integer
	- abs() returns the absolute value of a number
	- power() returns the power (second parameter taken) of the base (first parameter taken).
	- the is_integer() method returns true if a floating point value is integral; has no actual decimal values
	

### Chapter 6

- Functions are convenient for when you have a piece of code that you are going to reuse multiple times in a software. You can just place it in the function and call the function when necessary.

- Functions are values that can be assigned to variables:
	+ ```python
	  type(len)  > <built-in function len>
	  ```
	
- You can even replace len()'s data type by assigning it a value. Doing this will stop you from accessing len() for the rest of your code, unless you 
	+ ```python
	  del len
	  ```
	
- Just running len won't work in a program. For functions, you have to put brackets at the end like len(). Inside those brackets will go parameters, or aguments. len() takes values or variables, but some functions don't take anything. Regardless, they must be run with those brackets, but this time empty.

- Once len(apple) is 'called', the function is executed with the argument apple. Finally, the result is 'returned' as the return value: 5. Thus, one cycle of the function is completed. 

- To create a function, you must give it a function signature:	
	+ def name(parameters):
		* where def is used to clarify that you're defining a function (a keyword), name is the name you will use to call on the function later, and  parameters are the values it needs.
	
- And then a body:
	product = parameters + parameters
	
- And finally, the value to return:
	+ return product
	
- Making up:

  ```python
  def name(parameters):
  	product = parameters + parameters
  	return product
  ```

- Note the indentations: if a line of code is indented after the declaration of a function, it automatically comes under the function. This is especially important in Python since there are no delimiters (e.g: {}) for functions. 

- Python is generally picky about indents. Make sure all of them are either spaced or tabbed, not both, and contain the same number of spaces/tabs. A good number is generally 4.

- Calling this function is the same as calling any other function, like print()

  ```python
  name(5)
  ```

- This will return 10, but nothing will be done with it. If you want to print it, for example, you can either:

  - ```python
    print(name(5))
    ```

  - Or, 

    ```python
    ten = name(5)
    print(ten)
    ```

- Some functions don't have a return statement. Usually, this type of function would be an action within itself.

- E.g:

  ```python
  def farewell(name):
      print("Goodbye, " + name)
  ```

- Here, calling the function would automatically print. You don't need to assign it to a variable or manually print. 

- If someone calls help(name) on a function, it generally returns a docstring of what the function does. User added functions don't contain these unless you manually add them:

  ```python
  def farewell(name):
      """Bids farewell to name"""
      print("Goodbye, " + name)
  ```

- Other than functions, there are also loops. A loop is merely a block of code that repeats for a specified number of times, or until a condition is met. 

- While loops are formatted as:

  ```Python
  while(1>0):
      print("1")
  ```

- Loops do not have names, as they are not objects supposed to be called. Here, the while loop is defined under the condition that 1 is greater than (>) 0. Since this condition is always true, this program will theoretically run forever (or until it is force closed). 

- For loops loop through a collection of items; for each item in the collection, they do something.

- Formatted as: 

  ```python
  for letter in "Hello, world!":
      print(letter)
  ```

- Here, the collection is the string "Hello, world!". Since strings are basically sequences of characters, each item in the string (in this loop known as a 'letter') will be a character. 

- If you want to limit the number of loops in a for loop with basic, simple numbers, you can use the range() function. range(1, 4) means the program will run four times, starting with the first number and ending with the second. You can also just leave a number like in range(2) and it will count from 1 till that number.

- If you wish, you can also put loops within loops, a phenomenon called nested loops. 

Skipped chapter seven for prior knowledge.

### Logic and Control Flow

#### The Basics

While in loops, the loop body continues repeating so long as the condition is *not satisfied*. In a conditional, the body only executes once, and executes only if the condition is satisfied; as in, it returns `true`.

Logic is a complex topic, but in computer programming it takes the simple format of comparing one value with another. 

```python
if (1 > 0):
    do stuff
```

is the essence of a conditional. 'if' is the keyword, everything within the round brackets will be the condition, the statement, that must be satisfied, and everything after the colon (and indented) will be the body of code executed if the condition is true.

There are a number of operators for logic statements in the python language. Ones you learned in school, like > (greater than), < (lesser than), and == (equals to). The equals to has two equals signs together; otherwise, the interpreter would confuse it for the assignment variable, a single =. There are also 'booleans', basically `True` and `False`. When you write the `1 > 0` statement a boolean, in this case `True` (because the statement is true), is returned. 

#### Some Other Keywords

Mathematical operators isn't the only way to express conditionals, though it is most common. There are special keywords too.

```python
if (1 > 0 and 2 > 1):
	print("1 is greater than 0, and 2 is greater than 1!")
```

The first is the `and` keyword. It is used when you need *two or more* conditions to ***all be true***. If all conditions, in this case `1 > 0` and `2 > 1`, are not true, then the condition returns `False` and the body of code does not execute. 

```python
if (1 > 0 or 2 > 1):
	print("1 is greater than 0, or 2 is greater than 0.")
```

The second is the `or` keyword. Here, only *one* of the however many conditions needs to return `True`. If one of them does, then the body of code will execute. 

```python
if (not 1 > 0):
	print("1 is not greater than 0.")
```

The `not` keyword basically reverses the boolean value of the condition. If `1 > 0` would normally return `True`, putting a `not` in front of it would make it `False`.

#### Flow Control

The `if` statement is just one of a couple of 'flow control' functions used in Python. Its format has already been outlined, but basically:

```python
if (a > b):
    do something
```

Of course, there could be a number of things other than a simple greater than statement in the brackets.

There is also the `else` keyword. Basically, if the main `if` condition  returns false, then the block of code under the `else` keyword is executed.

```python
if (a > b):
	do something
else: 
	do something else
```

If you wanted to add more conditions, then you could use the `elif` keyword.

```python
if (a > b):
	do something
elif (a == b):
	do something different
else:
	do something else
```

There can be as many `elifs` in an if statement as you wish. Note, however, that `elif` and `else` can not be used independently. They need to be used after an `if` statement, in the order `if>elif>else`. 

You can also nest if statements like you can while loops. 

#### Error Handling

In some programs, there are certain variables not in your hands like input. If a user were to input a string, for example, instead of a number, and you were to use a mathematical operator on it, the program would crash. In such cases, you can use error handling; instead of letting the error crash your program, you can pass it to the user in the form of text and ask for another input. 

```python
try:
	number = int(input("Enter a number: "))
except ValueError:
	print("That's not an integer!")
```

Here, the try block is executed first, and if it returns the specified error (in this case a `ValueError`), then the except is executed. If you wanted it to ask for input again, then you could use a while loop.

```python
while 1:
	try:
		number = int(input("Enter a number: "))
	except ValueError:
		print("That's not an integer!")
        continue
	break
```

Here, the continue forces the program into its next iteration; otherwise, it would read the break, which would close the loop.

### Tuples, Lists, and Dictionaries

A **data structure** is a collection of data. They take many forms, but in basic Python, the main types are:

#### Tuples

To define a tuple, we must define a sequence. A sequence is merely an ordered (or indexed) list of data; each specific 'data' is called an item of the sequence. Each item is assigned a number—an index—that denotes its position in the sequence. 

Strings are a type of sequence, as discussed in [Chapter 4](#Chapter-4). 

Now, a 'tuple', in mathematics, is a finite, ordered sequence of values. To denote a tuple, you use the format:

```python
example_tuple = (a, b, c, ...)
```

Here, a, b, and c, are all of the same data type. The distinguishing features of a tuple are the rounded brackets that delimit it, and the commas that separate each item. `example_tuple` is merely the variable the tuple is assigned to. 

To convert another data type into a tuple (like with `int()` or `str()`), use the `tuple()` function. 

```python
tuple("Python")
```

Tuples share many attributes with strings. They are immutable, can be indexed or sliced, have a len(), and are iterable using the for loop. 

You can also 'unpack' tuples onto variables:

```python
coordinates = (4.21, -0.75)
x, y = coordinates
```

Here, a tuple with two coordinates, an x and y position, is created. Then, its two values are assigned to the x and y variables. They are assigned to the variables in the order they are assigned (x first, y second).

#### Lists

Lists are another type of sequence data structure. Lists are also indexed, like tuples. The feature that distinguishes them from tuples and strings, however, is that they are **mutable.** Meaning, you can change a specific item in a list without having to replace the entire list.

```python
coordinates = [4.21, -0.75]
# or
list(4.21, -0.75)
```

The only distinguishing feature of a list definition is the fact that it is delimited by square brackets, unlike the round brackets of a tuple. They cam contain all python data types too.

Methods to utilize a lists' mutability:

```python
coordinates = ["up, down, left, right"]

coordinates = coordinates.split(",") # Split string into separate item wherever there is a comma

print(coordinates[1]) # Prints the 1 character in list (down)
print(coordinates[0:2]) # Splices characters 0:2 (up, down) and prints them
"left" in coordinates # checks if 'left' is in coordinates list (True)
for coordinate in coordinates: # for each coordinate in the list
    print(coordinate) # print coordinate
    # Basically iterates the list and prints every coordinate/item
coordinates[1] = 'up' # change the 1 item (down) in list to 'up'
coordinates[0:1] = ['up', 'down'] # Splices it back to normal
coordinates.insert(1, 'upright') # Inserts string 'upright' into index '1' in list 'coordinates' (doesn't replace 'down', just pushes it one index up)
coordinates.pop(1) # takes the value in index 1 ('upright') and removes it from the list
coordinates.extend("upright") # adds an item at the end of a list

sum([1, 2, 3, 4, 5]) # sum() is a simple function to sum all the contents of a sequence or variables

# Lists can also be created through mathematical formulas (this is called list comprehension)
numbers = [1, 2, 3, 4, 5]
cubes = [num**3 for num in numbers] # for each num in number, exponentiate (cube) it by three and make that an item in the list 'cubes'
# A list comprehension is formatted:
[do x for y in a]
```

#### Extras

You can also nest data structures:

```python
list = [[1, 2], [3, 4]]
```

Here, you would index or access each individual list with two indexes:

```python
list[1][2] # returns 2nd item in the first list
```

There are also special methods for copying lists. If you simply assigned one to another:

```python
fruits = ['banana', 'apple', 'mango']
foods = fruits
foods.insert("biryani")
```

and attempted to modify the new one, it would also modify the old list it was a copy of. Thus:

```python
fruits = ['banana', 'apple', 'mango', 'biryani']
# AND
foods = ['banana', 'apple', 'mango', 'biryani']
```

Sort of like a symlink.

Instead:

```python
foods = fruits[:]
```

works better. This slices all of the contents of the fruits list and *then* creates a foods list with them. You could also

```python
foods = fruits[0:]
```

Finally, you can sort lists with the `.sort()` method.

```python
foods.sort() # sorts foods in ascending order
```

You can specify *how* you want the list to be sorted by adding an optional parameter. This parameter must be a function, and the return values of the function will be used to sort the list in ascending order.

```python
foods.sort(key=len) # sorts the list according to the length of each item in ascending order
```

#### Dictionaries

Dictionaries are a data structure in Python, like tuples and lists. But they store information in pairs; **key-value pairs**, to be more specific. Each  item, also known as an object, in a dictionary has to parts: the key, and the value.

Compared to a layman dictionary, each key would be a word and the value would be its definition.

```python
foods = {
"Fruits": "Apple",
"Vegetables": "Celery",
"Savory": "Biryani",
}

foods["Fruits"] # Accesses each value under the "fruits" key
foods["Sweet"] = "Cake" # Dictionaries are mutable. This adds a value "Cake" under a new key "Sweet"

for food in foods:
    print(key + " " + foods[food])
    # To get a value when iterating over a dictionary, you need to specify the value as an index in the original dictionary name.
```

#### When To Use Each

Use a:

1. List - when you need order, mutability, and need the data to be iterated.
2. Tuple - when you need order, do **not** need mutability, and need the data to be iterated.
3. Dictionary - when you do not need order, need mutability, and plan to look up values; not iterate.

Basically, what distinguishes lists and tuples is mutability, while dictionaries are a whole data structure in their own.

### Object-Oriented Programming (OOP)

OOP is a method for structuring a program. In OOP, you have data and through 'objects', groups of similar methods and behaviors, you 'process' this data. 

#### Classes

Classes can be used to create custom data structures. Like with strings, you can also add methods to your classes that operate on the data that uses your structure. Classes, like functions, usually do not operate on *literals*. You are are instead supposed to define an 'instance' of that class later on when needed, and operate on any data with that. 

```python
class Worker: # class is the 'keyword', while Worker is the name of the class (you choose)
    # Everything after this is the body of the class:
    nationality = "Pakistani" # This is a class attribute; it is a value that all instances of a class will always share. As opposed to an instance attribute, which is different between each instance.
    def __init__(self, name, age, field): 
        """This 'instance method' (function of a class) is run everytime an instance of the Worker class is created (because of the keyword __init__).
    	The first parameter is what the function will use to refer to its own class. While an instance would simply use Worker.name, you have to refer to it as self.name here because Worker is not yet defined in this function--it is basically a placeholder.
        The next parameters are the 'instance attributes'. These are basically values that every Worker class contains; since __init__ is automatically run, you do not need to manually define these every time you want to create a Worker; you simply enter it as you would a parameter in a function when initially creating the instance""" 
        self.name = name # assigns the value of the parameter 'name' to the instance attribute self.name
        self.age = age # age of worker
        self.field = field # field of employment of worker
	
    def __str__(self): # Whatever this instance (keyword __str__) returns is outputted when an instance is print()-ed.
        return self.name+" is "+self.age+" years old." # It merely returns a formatted string
    
    def speak(self, speech): # This instance method takes a parameter 'speech'
        return self.name + " says " + self.speech + "." # It also returns a formatted string
        
# You can now create an instance of the Worker class
Raza = Worker("Raza", 24, "Chef") # Assigning an instance to a variable is the only way to keep it in memory

Danish = Worker("Danish", 18, "Fast Food")

print(Raza.field) # Note that, after assigning an instance to a variable, you interact with that instance using the variable name (here Raza). This is because every new Worker instance would override the previous if they all had the same name. 

print(Raza.nationality == Danish.nationality) # class attributes are referred to in the same way as instance attributes

Danish.nationality = "Indian" # Class attributes can be changed too

print(Danish.speak("Hello!")) # Instance methods are called like functions

print(Raza) # returns the value that Raza.__str__() returns 
```
