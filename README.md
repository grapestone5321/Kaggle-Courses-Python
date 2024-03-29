# Kaggle-Courses-Python


-------

This course covers the key Python skills you’ll need, so you can start using Python for data science. 

The course is ideal for someone with some previous coding experience who wants to add Python to their repertoire. 

If you're a first-time coder, you are encouraged to check out our ***Intro to Programming course***, which is designed for complete beginners who would like to get started with Python.

We'll start with a brief overview of ***Python syntax, variable assignment, and arithmetic operators***.



### 1 Hello, Python
A quick introduction to Python syntax, variable assignment, and numbers

- Hello, Python!

Python was named for the British comedy troupe ***Monty Python***, so we'll make our first Python program a homage to their skit about Spam.

      spam_amount = 0

***Variable assignment:*** Here we create a variable called spam_amount and assign it the value of 0 using ***=***, which is called ***the assignment operator***.

***Function calls:***. ***print*** is a Python function that displays the value passed to it on the screen. We call functions by putting parentheses after their name, and putting the inputs (or arguments) to the function in those parentheses.

      # Ordering Spam, egg, Spam, Spam, bacon and Spam (4 more servings of Spam)
      spam_amount = spam_amount + 4

The first line above is a ***comment***. In Python, comments begin with ***the # symbol***.

Next we see an example of reassignment. Reassigning the value of an existing variable looks just the same as creating a variable - it still uses ***the = assignment operator***.

- Numbers and arithmetic in Python

***"Number"*** is a fine informal name for the kind of thing, but if we wanted to be more technical, we could ask Python how it would describe the type of thing.

***The // operator*** gives us a result that's rounded down to the next integer.

- Order of operations

The arithmetic we learned in primary school has conventions about the order in which operations are evaluated. 

Some remember these by a mnemonic such as ***PEMDAS*** - ***Parentheses, Exponents, Multiplication/Division, Addition/Subtraction***.

- Builtin functions for working with numbers

***min and max*** return the minimum and maximum of their arguments, respectively...

***abs*** returns the absolute value of an argument.

In addition to being the names of Python's two main numerical types, ***int and float*** can also be called as functions which convert their arguments to the corresponding type.

***The colon (:)*** at the end of the if line indicates that a new ***code block*** is starting. Subsequent lines which are indented are part of that code block.

***The * operator*** can be used to multiply two numbers (3 * 3 evaluates to 9), but we can also multiply a string by a number, to get a version that's been repeated that many times. 

Python offers a number of cheeky little time-saving tricks like this where operators like * and + have a different meaning depending on what kind of thing they're applied to. (The technical term for this is operator overloading.)

### 2 Functions and Getting Help
Calling functions and defining our own, and using Python's builtin documentation

You've already seen and used functions such as print and abs. But Python has many more functions, and defining your own functions is a big part of python programming.

In this lesson, you will learn more about using and defining functions.


- Getting Help

***The help() function*** is possibly the most important Python function you can learn. 

If you can remember how to use help(), you hold the key to understanding most other functions.

Here is an example:

      help(round)
      
Help on built-in function round in module builtins:

round(number, ndigits=None)
 
Round a number to a given precision in decimal digits.
    
The return value is an integer if ndigits is omitted or None.  

Otherwise the return value has the same type as the number.  ndigits may be negative.
 
help() displays two things:

1. the header of that function round(number, ndigits=None). In this case, this tells us that round() takes an argument we can describe as number. Additionally, we can optionally give a separate argument which could be described as ndigits.

2. A brief English description of what the function does.
 
***Common pitfall***: when you're looking up a function, remember to pass in the name of the function itself, and not the result of calling that function.

What happens if we invoke help on a call to the function ***round()***? Unhide the output of the cell below to see.

      help(round(-2.01))
 
 Python evaluates an expression like this from the inside out. First it calculates the value of ***round(-2.01)***, then it provides help on the output of that expression.

(And it turns out to have a lot to say about integers! After we talk later about objects, methods, and attributes in Python, the help output above will make more sense.)

***round*** is a very simple function with a short docstring. ***help*** shines even more when dealing with more complex, configurable functions like ***print***. 

Don't worry if the following output looks inscrutable... for now, just see if you can pick anything new out from this help.

- Defining functions

Builtin functions are great, but we can only get so far with them before we need to start defining our own functions. 

Functions start with a header introduced by the def keyword.

he indented block of code following the ***:*** is run when the function is called.

***return*** is another keyword uniquely associated with functions. 

When Python encounters a ***return*** statement, it exits the function immediately, and passes the value on the right hand side to the calling context.

Python isn't smart enough to read my code and turn it into a nice English description. 

However, when I write a function, I can provide a description in what's called the ***docstring***.

- Docstrings

The docstring is a triple-quoted string (which may span multiple lines) that comes immediately after the header of a function. 

When we call ***help()*** on a function, it shows the docstring.

Good programmers use docstrings unless they expect to throw away the code soon after it's used (which is rare). 

So, you should start writing docstrings, too!

- Functions that don't return

Here's something that's powerful, though it can feel very abstract at first. 

You can supply functions as arguments to other functions. 

Python allows us to define such functions. The result of calling them is the special value ***None***. (This is similar to the concept of "null" in other languages.)

- Default arguments

When we called help(print), we saw that the print function has several optional arguments. 

For example, we can specify a value for sep to put some special string in between our printed arguments.

By default, max returns the largest of its arguments. 

But if we pass in a function using the optional key argument, it returns the argument x that maximizes key(x) (aka the 'argmax').

- Functions Applied to Functions

Here's something that's powerful, though it can feel very abstract at first. You can supply functions as arguments to other functions.

Functions that operate on other functions are called "higher-order functions." 

You probably won't write your own for a little while. 

But there are higher-order functions built into Python that you might find useful to call.

By default, ***max*** returns the largest of its arguments. 

But if we pass in a function using the optional key argument, it returns the argument x that maximizes ***key(x)*** (aka the 'argmax').

### 3 Booleans and Conditionals

Using booleans for branching logic

- Booleans

Python has a type of variable called bool. It has two possible values: ***True*** and ***False***.

Rather than putting ***True*** or ***False*** directly in our code, we usually get boolean values from ***boolean operators***. 

These are operators that answer yes/no questions. 

We'll go through some of these operators below.

- Comparison Operations

      Operation	Description		            Operation	Description
       a == b	a equal to b	            a != b	a not equal to b
       a < b	a less than b	            a > b  	a greater than b
       a <= b	a less than or equal to b	a >= b	a greater than or equal to b



Comparison operators can be combined with the arithmetic operators we've already seen to express a virtually limitless range of mathematical tests. 

For example, we can check if a number is odd by checking that the modulus with 2 returns 1.

      def is_odd(n):
          return (n % 2) == 1

      print("Is 100 odd?", is_odd(100))
      print("Is -1 odd?", is_odd(-1))

Remember to use == instead of = when making comparisons. If you write n == 2 you are asking about the value of n. 

When you write n = 2 you are changing the value of n.

- Combining Boolean Values

You can combine boolean values using the standard concepts of "and", "or", and "not". 

In fact, the words to do this are: ***and***, ***or***, and ***not***.

With these, we can make our can_run_for_president function more accurate.

ou could try to memorize the order of precedence, but a safer bet is to just use liberal parentheses. Not only does this help prevent bugs, it makes your intentions clearer to anyone who reads your code.

- Conditionals

Booleans are most useful when combined with conditional statements, using the keywords ***if***, ***elif***, and ***else***.

Conditional statements, often referred to as if-then statements, let you control what pieces of code are run based on the value of some Boolean condition. 

The if and else keywords are often used in other languages; its more unique keyword is elif, a contraction of "else if". 

In these conditional clauses, elif and else blocks are optional; additionally, you can include as many elif statements as you would like.

- Boolean conversion

We've seen ***int()***, which turns things into ints, and ***float()***, which turns things into floats, so you might not be surprised to hear that Python has a ***bool()*** function which turns things into bools.



### 4 Lists
Lists and the things you can do with them. Includes indexing, slicing and mutating

- Lists

Lists in Python represent ordered sequences of values.

- Indexing

You can access individual list elements with square brackets.

Which planet is closest to the sun? Python uses zero-based indexing, so the first element has index 0.

- Slicing

What are the first three planets? We can answer this question using slicing.

- Changing lists

Lists are "mutable", meaning they can be modified "in place".

One way to modify a list is to assign to an index or slice expression.

- List functions

Python has several useful functions for working with lists.

len gives the length of a list.

- Interlude: objects

I've used the term 'object' a lot so far - you may have even read that everything in Python is an object. What does that mean?

In short, objects carry some things around with them. You access that stuff using Python's dot syntax.

For example, numbers in Python carry around an associated variable called imag representing their imaginary part. 

(You'll probably never need to use this unless you're doing some very weird math.)

- List methods

list.append modifies a list by adding an item to the end.

- Searching lists

Where does Earth fall in the order of planets? We can get its index using the list.index method.

- Tuples

Tuples are almost exactly the same as lists. They differ in just two ways.

***1***: The syntax for creating them uses parentheses instead of square brackets

***2***: They cannot be modified (they are immutable).





### 5 Loops and List Comprehensions
For and while loops, and a much-loved Python feature: list comprehensions

- Loops

Loops are a way to repeatedly execute some code.

      range()
      
      while loops

while loops:

The other type of loop in Python is a while loop, which iterates until some condition is met.

- List comprehensions

List comprehensions are one of Python's most beloved and unique features. 

***The Zen of Python***
https://en.wikipedia.org/wiki/Zen_of_Python

Readability counts.

Explicit is better than implicit.

So, use these tools to make compact readable programs. But when you have to choose, favor code that is easy for others to understand.

### 6 Strings and Dictionaries
Working with strings and dictionaries, two fundamental Python data types

- Strings

One place where the Python language really shines is in the manipulation of strings. 

This section will cover some of Python's built-in string methods and formatting operations.

Such string manipulation patterns come up often in the context of data science work.

- String syntax

Double quotes are convenient if your string contains a single quote character (e.g. representing an apostrophe).

Similarly, it's easy to create a string that contains double-quotes if you wrap it in single quotes.

- Strings are sequences

Strings can be thought of as sequences of characters. Almost everything we've seen that we can do to a list, we can also do to a string.

- String methods

Like list, the type str has lots of very useful methods.

- Going between strings and lists: .split() and .join()

str.split() turns a string into a list of smaller strings, breaking on whitespace by default. 

This is super useful for taking you from one big string to a list of words.

- Building strings with .format()

Python lets us concatenate strings with the + operator.

- Dictionaries

Dictionaries are a built-in Python data structure for mapping keys to values.


### 7 Working with External Libraries
Imports, operator overloading, and survival tips for venturing into the world of external libraries

In this tutorial, you will learn about ***imports*** in Python, get some tips for working with unfamiliar libraries (and the objects they return), and dig into ***operator overloading***.


- Imports

So far we've talked about types and functions which are built-in to the language.

But one of the best things about Python (especially if you're a data scientist) is the vast number of high-quality custom libraries that have been written for it.

Some of these libraries are in the "standard library", meaning you can find them anywhere you run Python. Other libraries can be easily added, even if they aren't always shipped with Python.

Either way, we'll access this code with imports.

We'll start our example by importing math from the standard library.

- Other import syntax

If we know we'll be using functions in math frequently we can import it under a shorter alias to save some typing (though in this case "math" is already pretty short).

- Submodules

We've seen that modules contain variables which can refer to functions or values. Something to be aware of is that they can also have variables referring to other modules.

- Oh the places you'll go, oh the objects you'll see

So after 6 lessons, you're a pro with ints, floats, bools, lists, strings, and dicts (right?).

Even if that were true, it doesn't end there. As you work with various libraries for specialized tasks, you'll find that they define their own types which you'll have to learn to work with. For example, if you work with the graphing library matplotlib, you'll be coming into contact with objects it defines which represent Subplots, Figures, TickMarks, and Annotations. pandas functions will give you DataFrames and Series.

- Three tools for understanding strange objects

      1: type()
  
      2: dir()
 
      3: help()

- Operator overloading

We might think that Python strictly polices how pieces of its core syntax behave such as +, <, in, ==, or square brackets for indexing and slicing. 

But in fact, it takes a very hands-off approach. When you define a new type, you can choose how addition works for it, or what it means for an object of that type to be equal to something else.

The designers of lists decided that adding them to numbers wasn't allowed. 

The designers of numpy arrays went a different way (adding the number to each element of the array).

Here are a few more examples of how numpy arrays interact unexpectedly with Python operators (or at least differently from lists).



- When does 1 + 1 not equal 2?

Things can get weirder than this. You may have heard of (or even used) tensorflow, a Python library popularly used for deep learning. 

It makes extensive use of operator overloading.

- Curious how it all works?

Have you ever called help() or dir() on an object and wondered what the heck all those names with the double-underscores were?

### Bonus Lessons
Apply what you've learned

These lessons aren’t required for your certificate, but bridge the gap between courses and applying your new skills!





-------

