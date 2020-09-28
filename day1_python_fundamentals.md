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

</details>

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

### For Loops

We use a `for loop` when we know how many times we want to loop.<br>
<br>

We can use for loops to interate through:

<ul>
 <li>Range</li>
 <li>Lists</li>
 <li>Dictionaries</li>
</ul>

```py
# This will loop for ten times.
for i in range(0,10,1):
    print(i)

list = [1,2,3,4,5]

#looping through a list.
for x in range(0,len(list)):
    print(list[x])

ninja = { 'name': 'Adrien' , 'age' : 38, "is_cool": True }

#looping through a dictionary.
for key,val in ninja.items():
    print(f"{key} : {val}")

```

### While Loops

We use while loops when we want our code to do something for an unknown amount of times.<br>
<br>

```py

is_adrien_cool = True
count = 0

while is_adrien_cool:
    if count == 5:
        is_adrien_cool = False
    count ++

```

## Functions

Functions are blocks of code that we can package up and reuse over and over again.


```py
# Basic setup
# This is how we define our functions.
def square_root(list):
    output = []
    
    for i in list:
        output.append(list[i] * list[i])

    # return statements always end a function
    return output


nums = [1,2,3,4]

# Callig a function, This is where the code in the fuction runs.
def square_root(nums)

# we can even assign the return value of a function to another variable

squares = square_root(nums)

print(squares)
# outputs [1,4,9,16]
```

***THINGS TO WATCH OUT FOR***
<ul>
    <li>indentation</li>
    <li>return statements</li>
</ul>
