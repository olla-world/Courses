# Python OOP, Mutable vs Immutable and Two Pointer Technique

## Overview of Object-oriented programming (OOP)

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


## Brief on class and object in Python

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

## Mutable and immutable data types in python

Some of the `mutable` data types in Python are **list**, **dictionary**, **set** and **user-defined classes**.
On the other hand, some of the `immutable` data types are **int**, **float**, **decimal**, **bool**, **string**, **tuple**, and **range**.
To get started, it’s important to understand that every object in Python has an ID (or identity), a type, and a value, as shown in the following snippet:

```Python
    age = 42
    print(id(age))    # id
    print(type(age))  # type
    print(age)        # value
    
    
    [Out:]
    10966208
    <class ‘int’>
    42
```
Once created, the ID of an object never changes. It is a unique identifier for it, and it is used behind the scenes by Python to retrieve the object when we want to use it.
The type also never changes. The type tells what operations are supported by the object and the possible values that can be assigned to it.
The value can either change or not. If it can, the object is said to be mutable, while when it cannot, the object is said to be immutable.
Let’s take a look at an example:

```Python
    age = 42
    print(id(age))
    print(type(age))
    print(age)
    age = 43
    print(age)
    print(id(age))
    
    
    [Out:]
    10966208
    <class ‘int’>
    42
    43
    10966240
```
Has the value of `age` changed? Well, no. `42` is an integer number, of the type `int`, which is immutable. So, what happened is really that on the first line, `age` is a name that is set to point to an `int` object, whose value is `42`.
When we type `age = 43`, what happens is that another object is created, of the type `int` and value `43` (also, the `id` will be different), and the name `age` is set to point to it. So, we didn’t change that `42` to `43`. We actually just pointed `age` to a different location.
As you can see from printing `id(age)` before and after the second object named `age` was created, they are different.
Now, let’s see the same example using a mutable object.


```Python
    x = [1, 2, 3]
    print(x)
    print(id(x))
    x.pop()
    print(x)
    print(id(x))
    
    
    [Out:]
    [1, 2, 3]
    139912816421064
    [1, 2]
    139912816421064
```
For this example, we created a list named `m` that contains 3 integers, `1`, `2`, and `3`. After we change `m` by “popping” off the last value `3`, the ID of `m` stays the same!
So, objects of type `int` are immutable and objects of type `list` are mutable. Now let’s discuss other immutable and mutable data types!

### Mutable data types

Mutable sequences can be changed after creation. Some of Python’s mutable data types are: **lists**, **byte arrays**, **sets**, and **dictionaries**.

#### Lists

As you saw earlier, lists are mutable. Here’s another example using the `append()` method:

```Python
    a = list(('apple', 'banana', 'clementine'))
    print(id(a))
    a.append('dates')
    print(id(a))

    [Out:]
    140372445629448
    140372445629448
```

#### Byte Arrays

Byte arrays represent the mutable version of `bytes` objects. They expose most of the usual methods of mutable sequences as well as most of the methods of the `bytes` type. Items are integers in the range `[0, 256)`.
Let’s see a quick example with the bytearray type to show that it is mutable:

```Python
    b = bytearray(b'python')
    print(id(b))
    b.replace(b'p', b'P')
    print(id(b))

    [Out:]
    139963525979808
    139963525979808
```

#### Sets

Python provides two set types, `set` and `frozenset`. They are unordered collections of immutable objects.

```Python
    c = set((‘San Francisco’, ‘Sydney’, ‘Sapporo’))
    print(id(c))
    c.pop()
    print(id(c))
    
    [Out:]
    140494031990344
    140494031990344
```

As you can see, `sets` are indeed mutable. Later, in the **Immutable Data Types** section, we will see that `frozensets` are immutable.

#### Dictionaries

```Python
    d = {
        'a': 'alpha',
        'b': 'bravo',
        'c': 'charlie',
        'd': 'delta',
        'e': 'echo'
    }
    print(id(d))
    d.update({
        'f': 'foxtrot'
    })
    print(id(d))

    [Out:]
    14007111431940
    14007111431940
```

### Immutable data types

Immutable data types differ from their mutable counterparts in that they can not be changed after creation. Some immutable types include **numeric data types**, **strings**, **bytes**, **frozen sets**, and **tuples**.

#### Numeric

You have already seen that integers are immutable; similarly, Python’s other built-in numeric data types such as booleans, floats, complex numbers, fractions, and decimals are also immutable!

#### Strings and Bytes

Textual data in Python is handled with `str` objects, more commonly known as **strings**. They are immutable sequences of **Unicode code points**. Unicode code points can represent a character.
When it comes to storing textual data though, or sending it on the network, you may want to encode it, using an appropriate encoding for the medium you’re using. The result of an encoding produces a `bytes` object, whose syntax and behavior is similar to that of strings.
Both strings and bytes are immutable, as shown in the following snippet:

```Python
    # string
    e = 'Hello, World!'
    print(id(e))
    e = 'Hello, Mars!'
    print(id(e))

    [Out:]
    140595675113648
    140595675113776
    # bytes
    unicode = 'This is üŋíc0de'  # unicode string: code points
    print(type(unicode))
    f = unicode.encode('utf-8')  # utf-8 encoded version
    print(type(f))
    print(id(f))
    f = b'A bytes object'        # a bytes object
    print(id(f))

    [Out:]
    <class 'str'>
    <class 'bytes'>
    140595675068152
    140595675461360
```

In the bytes section, we first defined `f` as an encoded version of our `unicode` string. As you can see from `print(type(f))` this is a `bytes` type. We then create another `bytes` object named `f` whose value is `b'A bytes object'`. The two `f` objects have different IDs, which shows that bytes are immutable.

#### Frozen Sets

As discussed in the previous section, `frozenset`s are similar to `set`s. However, `frozenset` objects are quite limited in respect of their mutable counterpart since they cannot be changed. Nevertheless, they still prove very effective for membership test, union, intersection, and difference operations, and for performance reasons.

#### Tuples

The last immutable sequence type we’re going to see is the tuple. A tuple is a sequence of arbitrary Python objects. In a tuple, items are separated by commas. These, too, are immutable, as shown in the following example:

```Python
    g = (1, 3, 5)
    print(id(g))
    g = (42, )
    print(id(g))

    [Out:]
    139952252343784
    139952253457184
```

## Coding exercise

### [Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

```Python
    class Solution(object):
        def isPalindrome(self, s):
            mod_s = [c.lower() for c in s if c.isalnum()]

            start = 0
            end = len(mod_s) - 1
            while start <= end:
                if mod_s[start] != mod_s[end]:
                    return False
                
                start = start + 1
                end = end - 1

            return True
```
> Time Complexity `O(n)`
>
> Memory Complexity: `O(n)`.

### [Two Sum II - Input array is sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

```Python
    class Solution(object):
        def twoSum(self, numbers, target):
            result = []

            start = 0
            end = len(numbers) - 1
            while start <= end:
                tow_sum = numbers[start] + numbers[end]
                if target == tow_sum:
                    result = [start + 1, end + 1]
                    break
                elif tow_sum > target:
                    end = end - 1
                elif tow_sum < target:
                    start = start + 1

            return result
```
> Time Complexity `O(n)`
>
> Memory Complexity: `O(1)`.

#### Mathmatical proof

```
given,          an incrementally sorted array  
                &  a target value ‘t’
                
assume,         i < j    	        where ‘i’ and ‘j’ are two indexes of that array
so, 	        a[i] <= a[j]  	    where ‘a[i]’, ’a[j]’  are two elements of that given array 

have to find 	a[i] + a[j] = t

if 	a[i] + a[j] != t  
a[i] + a[j] > t    or   a[i] + a[j] < t

we know,            a[i] < a[j]                 or              a[i] = a[j]
              =>    t - a[j] < a[i] < a[j]                =>    a[j] > t - a[j]
              =>    t - a[j] < a[j]                       =>    t < a[j]
              =>    t < a[j]
              
              from this we can say that we need to reduce the value of j to get the smaller value than a[j]
              
again,
                    a[i] < a[j]                 or              a[i] = a[j]   
               =>   a[i] < a[j] < t - a[i]                =>    a[i] < t - a[i]        
               =>   a[i] < t- a[i]                        =>    a[i] < t
               =>   a[i] < t
               
               from this we can say that we need to increase the value of i to get the bigger value than a[i]
```

