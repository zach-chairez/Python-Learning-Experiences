# Introduction to Object-Oriented Programming (OOP) in Python

## Motivation
Previously, at the end of a technical interview, I asked:  
**"What Python concepts would you recommend for someone like me applying to this (Data Scientist) role to study more of?"**

His answer?  **Object Oriented Programming**.

And because of that, here we are!  I hope this introduction and soft exploration helps you as much as it's helped me.  

## What is Object-Oriented Programming?
Object-Oriented Programming (OOP) is a programming style that structures programs using **objects**, which bundle both **data (attributes)** and **functions (methods)** together. 
This approach improves code organization, readability, and may help with understanding how real world structures work.   

Here are some resources I found useful while making this page and for general reading:

### Practice Problems
- [OOP Practice Problems](https://www.w3resource.com/python-exercises/oop/index.php)
- [More OOP Practice](https://pynative.com/python-object-oriented-programming-oop-exercise/)
- [Even More OOP Practice!](https://www.geeksforgeeks.org/python-exercises-practice-questions-and-solutions/#python-oops-exercises)
### High Level Overview
- [OOP in Python](https://www.geeksforgeeks.org/python-oops-concepts/)
- [OOP in Python for Beginners (Video)](https://www.youtube.com/watch?v=JeznW_7DlB0)
- [Another Video!](https://www.youtube.com/watch?v=0XR_91AfgZI)

### Why Use OOP?
Think about how we interact with the world. You don't need to know the inner workings of a car engine to drive—it just has a steering wheel, gas pedal, and brakes. OOP follows the same idea: it hides complexity and lets us interact with objects in an intuitive way.

- **Encapsulation**: Bundle data and behavior together while restricting direct access to internal details. 
  - Example: Imagine a bank account. You can deposit and withdraw money, but you don’t need direct access to the database storing your balance.
- **Abstraction**: Simplify complex systems by exposing only relevant functionalities.
  - Example: Your smartphone hides all the technical details—you just tap on icons to use apps.
- **Inheritance**: Allow new classes to derive from existing ones, promoting code reuse.
  - Example: Think of a blueprint for a house. You can make modifications while keeping the basic structure intact.
- **Polymorphism**: Enable different classes to share a common interface with varied implementations.
  - Example: A USB port can work with a keyboard, mouse, or flash drive—all different devices, but they share the same interface.

## Getting Started with OOP in Python

### Defining a Simple Class
Have you ever thought about how you would model real-world objects in code? Imagine you're trying to describe an animal. How would you structure its characteristics and behaviors?

A **class** is a blueprint for creating objects in order to create a reusable, organized, and elegant way to store functions and data.  

```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self, sound):
        return f"{self.name} the {self.species} says {sound}!"

# Creating an animal instance
dog = Animal("Bartholomew", "Dog")
cat = Animal("Captain Bowtie", "Cat")

print(dog.make_sound("Bark Bark"))  # Output: Bartholomew the Dog says Bark Bark!
print(cat.make_sound("Meoooooww"))  # Output: Captain Bowtie the Cat says Meoooooww!
```

Since we made: ```class Animal```, we can create an endless number of combinations of instances of it by creating the variables ```dog``` and ```cat``` with their own unique inputs.  

Can we think of other types of relationshsips like the example above that would call for a ```Class```? 

### Encapsulation: Protecting Data
Encapsulation attempts to protect a class's instance by restricting direct modifications, ensuring that changes occur only through controlled interactions. 

Consider a bank account where deposits and withdrawals should be the ONLY way to update your balance, i.e., you should never modify the balance directly. Instead, encapsulation allows you to enforce this rule by restricting direct access and requiring all changes to go through well-defined methods. 

However, there is nuance to this.  We'll say now that it's ***not really protected***, but merely made more difficult to access.  

```python
class BankAccount:
    def __init__(self, opening_balance):
        # Double underscore denotes a private attribute.
        self.__balance = opening_balance  
    
    def deposit(self, amount):
        self.__balance += amount

    def withdraw(self,amount):
        if amount > self__balance:
          return "Insufficient funds!"
        else:
          self.__balance -= amount
    
    def get_balance(self):
        return self.__balance

# Creating an account
account = BankAccount(1000)
account.deposit(500)
print(account.get_balance())  # Output: 1500
account.withdraw(200)
print(account.get_balance()) # Output: 1300
print(account.balance()) # Output:  BankAccount' object has no attribute 'balance'
```

We see that the attribute ```balance``` is not directly accessible, but in actuality it is accessible if the user knows that balance is a private attribute.  They could directly modify ```balance``` as follows:

```python
account.__balance = -2356
print(account.__balance) # Output: -2356
```

Python simply "name-mangles" balance so that it's harder to access, but not impossible.
Its utility is still not completely clear to me - what do you think about Encapsulation?


### Abstraction: Hiding the Complexity
Abstraction helps simplify complex systems by hiding unnecessary details and exposing only what's needed. Think about a TV remote—you press a button to change channels, but you don’t need to know how the remote sends signals to the TV.

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def start_engine(self):
        pass

class Car(Vehicle):
    def start_engine(self):
        return "Engine started with a key!"

class ElectricCar(Vehicle):
    def start_engine(self):
        return "Engine started with a button!"

# The user doesn't need to know the details, just how to start the engine
my_car = Car()
my_tesla = ElectricCar()

print(my_car.start_engine())  # Output: Engine started with a key!
print(my_tesla.start_engine())  # Output: Engine started with a button!
```
## Conclusion
OOP is like organizing your code into smart containers that interact with each other. Mastering OOP will help you write cleaner, more efficient programs. So go ahead—experiment, break things, and have fun learning!
