# Day 2 - Python Object Oriented Programming

<img src="https://github.com/adion81/python_lectures/blob/master/assets/python.png" alt="Python" width="200px" > 

### OOP Questions

1. <details>
    <summary>Four Pillars of OOP</summary>
    <ul>
        <li>Encapsulation</li>
        <li>Abstraction</li>
        <li>Polymorphism</li>
        <li>Inheritance</li>
    </ul>
</details>

2. <details>
    <summary>What are the benefits of OOP?</summary>
    <ul>
        <li>Resuability</li>
        <li>Simplicity</li>
        <li>Easily Maintainable</li>
        <li>Security for Class Variables</li>
    </ul>
</details>


## Classes

Classes are a way that we can write custom data types, and they are an important component in OOP.  It's like creating our own object, and we can define the values that is has, and even how it behaves with methods.<br>
<br>

This is how we define a class in python:

```py

# A class is just a blue print of a custom object we want to create.
class Ninja:
    # This is a constructor function that initializes the class.
    def __init__(self,name,dojo):
        # These are attritbutes that we assign to the class.
        self.name = name
        self.dojo = dojo
        # This is how we can default our attributes.  Now every ninja starts with 0 belts.
        self.num_of_belts = 0
    
    # Methods are functions on a class that initiate behavior of the class
    def printInfo(self):
        print(f"Name: {self.name}\nDojo Location: {self.dojo}\n# of Belts: {self.num_of_belts}")

    def getRedBelt(self,did_pass):
        if(did_pass):
            self.num_of_belts += 1
        else:
            print("Shake it off, and try again")

# Then we can create an instance of a ninja down here.
chris = Ninja("Chris","Chicago",4)
print(chris)
```

### Attributes

Notice that in the __init__ function, we take in parameters so that we can assign them to the attributes of the class.<br>
<br>

Attributes are the variables that hold the data about the class.  For a Ninja, it has a name, dojo location, and number of belts.<br>
<br>


### Methods

If attributes are variable that hold data on the class, then Methods are functions that change the data on the class.  They also give the class the ability to have behviors.<br>
<br>

So if you wanted your ninja to be able to give a sweet tornado kick, then you would add a method onto the class!!!<br>
<br>

<details>
    <summary>Click for Sweet Tornado Kick</summary>
    <img src="https://github.com/adion81/python_lectures/blob/master/assets/chuck.jpg" alt="Tornado Kick" width="900px" >
</details>




