### <u>BOOK HISTORY</u>

Python Basics by David Amos, et. al is a programming guide book for the Python programming language. It is divided into 19 chapters and 117 sub-chapters.

### <u>BOOK SCHEDULE</u> 

At a rate of 1 chapter per day, on alternate days, I can finish this book 38 days after picking it up.

### <u>SOME CRITERIA</u>	

1. Python Basics is a practical programming guide book for the python programming language. It contains exercises, and is for the sore beginner.
2. Python Basics is for the sore beginner. It contains many exercises and has pratical use applications as well. It is only a beginner book, howewver.

### <u>SUMMARIZE</u>

*Skipped the first three chapters for prior knowledge.*

#### CHAPTER 4

- **Data type** refers to what *kind* of data a value represents. 	
- A string is a data type, equivalent to text.
- Fundamental data types are data types that can not be further *broken* down into smaller values of a different type. (SEE: Ch. 9)

- Types often have an abbreviated name. String is abbreviated str, for example. You can figure this out by typing type(data) to figure out both the data type of a value or variable and its abbreviation.

- Strings have three main properties:
	- They contain characters, as in, they are made up of individual letters or symbols.
	- Strings have a length, as in, the number of characters that make up the string.
	- And these characters are ordered in a sequence to form the relevant text, as in, each character has a numbered position in the string.

- Strings can be created by surrounding some text in quotation marks. They can be both single and double quotes. Thes quotes are called delimiters; they limit its beginning and end so that the computer can understand where it begins and ends.

- A string written out and surrounded in double quotes in your code is called a string literal. This is different from, say, a user inputted string because that *is not* written explicitly in your code.

- Because python reads first for one delimiter and ends the string when it encounters the next, you can not use double quotes inside a double quotes delimited string.
	- e.g: Bad = print("Hello, "world"!"). Here, python thinks the string begins before 'H' and ends before 'w', Then, it reads 'world' and finds another string: "!". This leaves it with a non-variable word, world, which it can not interpret and the "!" which is not concatenated. Thus, it returns an error.
	- Instead, you should use single quotes in double quotes delimited strings and vice versa. e.g: print("Hello, 'world'!") or print('Hello, "world"!')

- For strings that you want to take up multiple lines, you can add \n to a given point within the string to force the rest of the text to print on a newline. You can also use """ or ''' delimiters and just type on a newline as if you were writing in a word processor. Triple codes are less commonly used than newlines for multiline strings. Their main application is actually as comments and code descriptions.

- As mentioned above, the second property of strings is that they have a length of characters. This can be determined with the function len(value). Using 'abc' as a parameter, the function returns a 3. You can also use this on variables.

- There are three basic operations that you can perform on a string: concatenation, indexing, and slicing.
	- Two strings are combined, concatenated, with then + operator in much the same way as addition.
	- Since strings are merely sequences of characters and are *indexed*, ordered, with numbers, you can access a character by giving its index. For example, if you wanted to know the 5th character in a string, you would do:
		- o = "orange"
		  o[4] # Python is offset by -1 and starts counting at zero so 4 is actually the fifth letter if you count from one
		- The result would be 'g'
		- If you wanted to count from left-to-right, as opposed to right-to-left, you would use negative numbers.
		- o[-1] would be e, and o[-2] would be g, etc
	- If you wanted to index multiple characters at once, you could use normal indexing or slicing
		- ora = o[0] + o[1] + o[2] # Normal indexing
		- ora = o[0:3] # Slicing
		- Both return 'ora', but one is more efficient
		- Note that slicing does index a bit differently. Instead of counting the first index number you ask it to (0, in our case) and ending with (3, in our case), it uses the two numbers as delimiiters and returns every string between them. You could view it as: string[start:end]

- Finally, note that strings are immutable. Immutability means that they can not be *changed*. When you attempt to alter a character in a string (e.g: o[1] = 'a') it will return an error. You can, of course, just define it again (e.g: o = 'oaange') but this doesn't change the old string, **it creates an entirely new one with the same name**.

- You can change a string's case with .lower() or .upper() method. 

- You can remove whitespace with:
	- .rstrip() removes all whitespace from the right of a string
	- .lstrip() removes all whitespace from the left of a string
	- .strip() removes whitespace from both sides of a string

- Determine what characters a string starts with using the .startswith() method

- You can take string input using the input() function

- You can also assign input() to a variable after which the interpreter will immediately ask for an input from the user and assign it to the variable.
	- e.g:
		age = input()
		print("How old are you? " + age)

- Input() takes strings as inputs. You can not perform arithmetic operations on them. To convert an input() string into an integer, put the input within int() or float(). If the user inputs a floating point and you try to convert it using int(), it wil return a ValueError!

- You can do the opposite using the str() function. In an f-string, they are automatically converted.
	- e,g: str(age) # an example of str() function
	- e.g: f"You are {age} years old." # an example of an f-string

- You can find a string within a string, also known as a substring, using the .find() method on the main string and inserting the substring in the brackets. Find returns a -1 if it doesn't find the string. 

#### CHAPTER 5

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
	

#### CHAPTER 6

- Functions are convenient for when you have a piece of code that you are going to reuse multiple times in a software. You can just place it in the function and call the function when necessary.

- Functions are values that can be assigned to variables:
	+ ```python
	  type(len)  > <built-in function len>
	  ```
	
- You can even replace len()'s data type by assigning it a value. Doing this will stop you from accessing len() for the rest of your code, unless you 
	+ ```python
	  del len
	  ```
	
- Just running `len` won't work in a program. For functions, you have to put brackets at the end like `len()`. Inside those brackets will go parameters, or aguments. `len()` takes values or variables, but some functions don't take anything. Regardless, they must be run with those brackets, but this time empty.

- Once `len(apple)` is 'called', the function is executed with the argument `apple`. Finally, the result is 'returned' as the return value: `5`. Thus, one cycle of the function is completed. 

- To create a function, you must give it a function signature:	
	+ `def name(parameters):`
		* where `def` is used to clarify that you're defining a function (a keyword), name is the name you will use to call on the function later, and  parameters are the values it needs.
	
- And then a body:
	`product = parameters + parameters`
	
- And finally, the value to return:
	+ `return product`
	
- Making up:

  ```python
  def name(parameters):
  	product = parameters + parameters
  	return product
  ```

- Note the indentations: if a line of code is indented after the declaration of a function, it automatically comes under the function. This is especially important in Python since there are no delimiters (e.g: {}) for functions. 

- Python is generally picky about indents. Make sure all of them are either spaced *or* tabbed, not both, and contain the same number of spaces/tabs. A good number is generally 4.

- Calling this function is the same as calling any other function, like `print() `

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

- If someone calls `help(name)` on a function, it generally returns a *docstring* of what the function does. User added functions don't contain these unless you manually add them:

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