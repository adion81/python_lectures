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

<details>
    <summary>Different Primitives</summary>
    <ol>
        <li>Boolean</li>
        <li>Number</li>
        <li>Floats</li>
        <li>String</li>
    </ol>

    ```py

    # Boolean is a binary type that is either True or False.
    is_Cool = True

    # Numbers can sometimes be called integers.
    num = 10

    # Floats are numbers with decimal places.
    pi = 3.14

    # Strings are a series of alphanumeric characters.
    name = "Benny Bob"

    ```
</details>


### Composite Data Types

<details>
    <summary>3 Composite Types</summary>
    <ol>
        <li>Tuples</li>
        <li>Lists</li>
        <li>Dictionaries</li>
    </ol>

    ```py

    # Tuples are immutable composite types that act like an array in JavaScript.  But you can't reassign the values.
    tup_banana = ("apple",3,true,(4,5))
    
    # Lists are equivalent to arrays in JavaScript.  They can hold any data type you want.
    food_list = ["Gummy Bears","Pie","Nutella"]

    # Dictionaries are Key Value pair types.
    ninja = { 'name': 'Adrien' , 'age' : 38, "is_cool": True }

    ```
    Helpful hint : You can find the length of a list with the `len()` method.<br>
    <br>

    ```py
    list = [1,2,3,4,5]
    print(len(list))
    # prints out 5

    ```
</details>


## Conditionals

Conditionals allow us to do things under certain conditions.  One of the most common way we can write a contional statement is with  `if, else, elif` statements.

```py

is_funny = False

# Remember that we need to indent when writing blocks of code!
if is_funny:
    print("HAHAHAHAHAHA)
else
    print("cricket cricket cricket")

x = 10

if x < 10:
    print("The number is less than 10")
elif x == 10:
    print("The number is 10")
else
    print("The number is greater than 10")

```

## Loops

Loops are a great way that we can repeat behavior in our code for as long as we want.<br>
<br>
***REMEMBER TO WORK SMARTER, NOT HARDER***
<br>





## Functions

