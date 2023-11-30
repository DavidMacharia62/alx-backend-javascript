# Class Definition and Method Usage

## Table of Contents
1. [Defining a Class](#defining-a-class)
2. [Adding Methods to a Class](#adding-methods-to-a-class)
3. [Static Methods](#static-methods)
4. [Class Inheritance](#class-inheritance)
5. [Metaprogramming and Symbols](#metaprogramming-and-symbols)

---

## Defining a Class

### What is a Class?
In object-oriented programming (OOP), a class is a blueprint for creating objects. Objects are instances of a class, and each object has attributes (data) and methods (functions) associated with it.

### Syntax for Class Definition:
```python
class ClassName:
    # Class attributes

    def __init__(self, parameter1, parameter2):
        # Constructor method
        # Initialize object attributes

    def regular_method(self, parameter):
        # Regular instance method

# Creating an instance of the class
obj = ClassName(argument1, argument2)
```

### Explanation:
- `class ClassName:`: Defines a class named `ClassName`.
- `__init__(self, parameter1, parameter2)`: Constructor method, called when an object is created. Initializes object attributes.
- `regular_method(self, parameter)`: Regular instance method, takes `self` as the first parameter, representing the instance itself.

---

## Adding Methods to a Class

### Instance Methods
Instance methods are functions that operate on the instance of the class.

```python
class MyClass:
    def __init__(self, data):
        self.data = data

    def print_data(self):
        print(self.data)

# Creating an instance
obj = MyClass("Hello")
obj.print_data()  # Output: Hello
```

### Class Methods
Class methods are methods that are bound to the class and not the instance of the class.

```python
class MyClass:
    class_variable = 0

    def __init__(self, data):
        self.data = data

    @classmethod
    def increment_class_variable(cls):
        cls.class_variable += 1

# Using class method
MyClass.increment_class_variable()
print(MyClass.class_variable)  # Output: 1
```

### Explanation:
- `@classmethod`: Decorator to define a class method.
- `cls`: Conventionally named parameter representing the class itself.

---

## Static Methods

### Why Static Methods?
Static methods don't have access to the instance or class itself. They are used when a method doesn't depend on instance-specific data.

### How to Add a Static Method:
```python
class MyClass:
    @staticmethod
    def static_method():
        print("This is a static method")

# Using static method
MyClass.static_method()  # Output: This is a static method
```

### Explanation:
- `@staticmethod`: Decorator to define a static method.
- No `self` or `cls` parameter is required.

---

## Class Inheritance

### Extending a Class
Inheritance allows a new class (subclass/derived class) to inherit attributes and methods from an existing class (superclass/base class).

```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        print("Woof!")

# Creating an instance
dog_obj = Dog()
dog_obj.speak()  # Output: Woof!
```

### Explanation:
- `class Dog(Animal)`: Indicates that `Dog` is a subclass of `Animal`.
- `def speak(self)`: Overrides the `speak` method from the base class.

---

## Metaprogramming and Symbols

### Metaprogramming
Metaprogramming involves writing code that manipulates or generates code. Python supports metaprogramming through features like decorators and dynamic code execution.

### Symbols
Symbols are immutable, unique objects often used as keys in dictionaries. They are created using the `symbol` module.

```python
import symbol

my_symbol = symbol.Symbol("my_symbol")
```

### Metaprogramming Example: Decorator
```python
def my_decorator(func):
    def wrapper():
        print("Something is happening before the function is called.")
        func()
        print("Something is happening after the function is called.")
    return wrapper

@my_decorator
def say_hello():
    print("Hello!")

say_hello()
```

### Explanation:
- `@my_decorator`: Applies the `my_decorator` to the `say_hello` function.
- The decorator `wrapper` modifies the behavior of `say_hello` by adding print statements.

---
