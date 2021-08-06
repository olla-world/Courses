# Python OOP, Mutable vs Immutable and Two Pointer Technique

## Object-oriented programming (OOP)

object-oriented programming is a programming paradigm based on the concept of `object`  and `class`. A class can be thought of as a `blueprint` for objects which can contain data and code: data as attributes or properties , and code in form of methods. Object-oriented programming has some advantages over other design patterns. Many of the most widely used programming languages _(such as C++, Java, Python, etc.)_ are multi-paradigm and they support object-oriented programming to a greater or lesser degree.

### Objects and Classes

Languages that support object-oriented programming (OOP) typically use inheritance for code reuse and extensibility in the form of either classes or prototypes. Those that use classes support two main concepts:

**Classes** : the definitions for the data format and available procedures _(methods)_ for a given type or class of object; may also contain data and procedures _(known as class methods)_ themselves, i.e. classes contain the data members and member functions.

**Objects** : instances of classes.Each object is a `instance variables` of a particular class.

### Four Principles of OOP

The four pillars of object-oriented programming are:

**Inheritance** : child classes inherit data and behaviors from parent class.

**Encapsulation** : containing information in an object, exposing only selected information.

**Abstraction** : only exposing high level public methods for accessing an object.

**Polymorphism** : many methods can do the same task.

## Object-Oriented Programming (OOP) in Python

### Create a class

`class` keyword is used to define a class in Python. Inside the class, an `__init__` has to be defined with `def`.This is the initializer to instantiate objects. It takes one argument: `self`, which refers to the object itself.
Lets create a `Fruit` class

```Python
    class Fruit:
        def __init__(self, name, color, taste):
            self.name = name
            self.color = color
            self.taste = taste
```

### Create an instance

To create `instance` of a class, have to call the class using class name and pass the arguments in its `__init__` method. For Example

```Python
    mango = Fruit("Mango", "Red", "Sweet")
```

Here `mango` is an object of `Fruit`.

> To access an object's attributes in Python, need to use the `dot notation`. This is done by typing the name of the object, followed by a dot and the attribute's name.

```Python
    print(mango.name)
```

### Define a methods in a class

Any class may have multiple methods except the `__init__` method. Class-methods have to be defined with `def` and each of them must have the `self` argument.

```Python
    class Fruit:
        def __init__(self, name, color, taste):
            self.name = name
            self.color = color
            self.taste = taste
        
        def intro(self):
            print(self.name + " is tasted " + self.taste)
```

> Here, `intro` is a class-method. Any instance of Fruit class may access this method using the dot notation.

```Python
    mango.intro()
```





