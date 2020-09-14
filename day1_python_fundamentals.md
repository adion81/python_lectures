# Python Fundamentals

<img src="https://github.com/adion81/python_lectures/blob/master/assets/python.png" alt="Python" width="350px" > 


## Syntax & Printing
<br>
Indentation is the most import when it comes to writing Python.  It is how we can define where blocks of code begin and end.<br>
There are no semicolons to end statements.<br>
<br>

Example of a block of code
```py
# Examples of blocks of code
# Function  The function ends  after the return statement because the endentation stops on that line.
def add (num1,num2):
    sum = num1 + num2
    return sum

# If Else statements
if x > y:
    print("Hello")
else:
    pring("world")

# this is not a part of a block of code.
add(1,2)
```
<br>
We use the `print()` method to print out stuff to the console.


```py
# There are many different ways we can print variable out to the console.

print("Hello World")

name = "Mr. Nibbles"
# Comma separated print statement
print("Hello" , name)

# Concatenation (notice there is an extra space at the end of the string)
print("Hello " + name )

# String Interpolation   This is where we can inject variables right into the string.
print(f"Hello {name}")

# Formatting These are the old way of string interpolation
print("Hello {}".format(name))
print("Hello %s" % (name))
```

## Data Types

### Primitive Data Types

### Composite Data Types

## Conditionals

## Loops

## Functions

