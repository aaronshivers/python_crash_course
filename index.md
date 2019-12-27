
# Python

## Setup Python

###  Check for previously installed versions of python
1. Open your terminal.
	* Type ```python3 --version``` to see if you have Python 3 already installed.
	* If you have Python 3 already, you'll see something like ```Python 3.7.3```, which tells us what version of python you have.
	* If that didn't work, try typing ```python --version```.
	* If neither option worked, then you need to install Python.

### Install Python
1. Go to [https://www.python.org/downloads/](https://www.python.org/downloads/)
2. Download and Install the latest version of Python for your specific operating system
3. Verify installation with the steps from the section titled "Check for previously installed versions of python"

## Accessing Python
1. Open your terminal.
1. Type  ```python3``` or ```python``` depending on how your operating system accesses Python.
1. When you're finished press ```ctrl + d``` or type ```exit()``` to exit Python.


## Basics

### Printing to the Console
Python provides a built-in method to print to the console. If we wanted to print a message like, "Hello Humanoids!", We should take the message, and surround it with quotation marks, then surround those with parentheses, then prefix it with the word print. Like this...
```py
print("Hello Humanoids!")
```

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/print?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

### Functions
If we wanted to create a function that prints our message it would look like this...
```py
def say_hello():
	print("Hello Humanoids!")
```

We define the function by writing "def" followed by the name of the function, then a set of parentheses, and finally a colon.

Underneath that we indent the next line with four spaces exactly, then we put our print method with our message.

We can now use the say_hello function anywhere in our program instead of typing the whole print method with the message.

Now to invoke the function...
```py
say_hello()
```

This will print "Hello Humanoids!" to the console.

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/sayhello1?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

### Arguments and Parameters

I think we should make our function more dynamic. What if we're not talking with Humanoids? That's where arguments and parameters come in to play.

Let's take our function and add a parameter called "species".

```py
def say_hello(species):
	print("Hello Humanoids!")
```

Now we'll use the format feature in python to use the new parameter inside of our print method.

First put the letter "f" in front of the quotes, then replace "Humanoids" with species surrounded by curly braces.

```py
def say_hello(species):
	print(f"Hello {species}!")
```

Now we'll add an argument to the function invocation for each species that we want to say hello to.
```py
say_hello("Humanoids")
say_hello("Cyborgs")
say_hello("Arachnids")
```

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/sayhello2?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

I just realized that not all species understand the word "hello", so we should add a second argument and parameter for that. Make sure that the order of your arguments in the invocation matches the order of the parameters in the function definition.

```py
def say_hello(greeting, species):
	print(f"{greeting} {species}!")


say_hello("Hello", "Humanoids")
say_hello("0100100001100101011011000110110001101111", "Cyborgs")
say_hello("Click Click Click", "Arachnids")
```

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/sayhello3?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

### Challenge 1

You are a grade school teacher, and it's time to do your morning roll call, but it's not enough to just say each student's name. You need to say each student's name in reverse order.

Create a function that takes a student's first and last name as arguments, and prints the name in reverse order.

#### Example:
If you invoke the function
```py
roll_call("Bobby", "Hill")
```
it should print...
```Hill, Bobby```

and,
```py
roll_call("Joseph", "Gribble")
```
should print...
```Gribble, Joseph```

### Basic Operators
Let's look at some of the basic operators Python has to offer.

#### Arithmetic Operators
We can...

**add**
```py
4 + 3
```
**subtract**
```py
6 - 3
```
**multiply**
```py
2 * 3
```
**divide**
```py
8 / 2
```

Let's make some functions that use arithmetic operators.

**add**
```py
def add(num1, num2):
	return num1 + num2
```
**subtract**
```py
def subtract(num1, num2):
	return num1 - num2
```

We can now pass the numbers we want to calculate into these functions...
```py
add(2, 4) # 6
subtract(5, 2) # 3
```

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/arithmeticoperators?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

## Assignment Operators

You can assign values to variables by using assignment operators.

**=**
```py
hungry = True
eye_balls = 2
favorite_color = "green"
```

You can even reassign values.

Start with a variable
```py
vacation_days = 2
```
You can give it a completely different value.
```py
vacation_days = 4
```
You can take the existing value, then use one of the arithmetic operators to get a new value.
```py
vacation_days = vacation_days + 3
```
You can also use the shorthand version of the previous example. This takes the existing value, adds it to the value on the right of the operator, and reassigns the variable to the new value.
```py
vacation_days += 4
```

<iframe height="400px" width="100%" src="https://repl.it/@aaronshivers/assignmentoperators?lite=true" scrolling="no" frameborder="no" allowtransparency="true" allowfullscreen="true" sandbox="allow-forms allow-pointer-lock allow-popups allow-same-origin allow-scripts allow-modals"></iframe>

### Challenge 2

You work at an ice cream parlor. How many scoops of ice cream you serve each customer depends on their age group. There are three age groups:
* ```children``` = 1 scoop
* ```adults``` = 2 scoops
* ```seniors``` = 3 scoops

When a family places an order. What is the total number of scoops you should serve them?

#### Examples
```py
scoop_it(3, 2, 1) # 10
scoop_it(1, 1, 3) # 11
scoop_it(2, 4, 0) # 10
```

#### Notes
* Just print the result to the console.
* The order that the customers are served is ```scoop_it(children, adults, seniors)```
* Remember that we're looking for the total number of scoops served.
