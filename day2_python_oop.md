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
    def __init__(self,name,dojo,belts):
        self.name = name
        self.dojo = dojo
        self.num_of_belts = belts
    
    def printInfo(self)"
        print(f"Name: {self.name}\nDojo Location: {self.dojo}\n# of Belts: {self.num_of_belts}")


# Then we can create an instance of a ninja down here.
chris = Ninja("Chris","Chicago",4)
print(chris)
```