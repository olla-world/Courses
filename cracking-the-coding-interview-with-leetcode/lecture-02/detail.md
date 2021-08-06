# Python OOP, Mutable vs Immutable and Two Pointer Technique

## Object-Oriented Programming (OOP)

object-oriented programming is a programming paradigm based on the concept of __object__  and __class__. A class can be thought of as a _blueprint_ for objects which can contain data and code: data as attributes or properties , and code in form of methods. Object-oriented programming has some advantages over other design patterns. Many of the most widely used programming languages _(such as C++, Java, Python, etc.)_ are multi-paradigm and they support object-oriented programming to a greater or lesser degree.

### Objects and Classes

Languages that support object-oriented programming (OOP) typically use inheritance for code reuse and extensibility in the form of either classes or prototypes. Those that use classes support two main concepts:

**Classes** : the definitions for the data format and available procedures _(methods)_ for a given type or class of object; may also contain data and procedures (known as class methods) themselves, i.e. classes contain the data members and member functions.

**Objects** : instances of classes.Each object is a _instance variables_ of a particular class.

### Four Principles of OOP

The four pillars of object-oriented programming are:

**Inheritance** : child classes inherit data and behaviors from parent class.

**Encapsulation** : containing information in an object, exposing only selected information.

**Abstraction** : only exposing high level public methods for accessing an object.

**Polymorphism** : many methods can do the same task.

## Object-Oriented Programming (OOP) in Python

### Create a Class

_class_ keyword is used to define a class in Python. Inside the class, an _ __init__ _ has to be defined with _def_.This is the initializer to instantiate objects. It takes one argument: _self_, which refers to the object itself.
Lets create a _Fruit_ class
```Python
  class Fruit:
    def __init__(self, name, color, taste):
      self.name = name
      self.color = color
      self.taste = taste
```

