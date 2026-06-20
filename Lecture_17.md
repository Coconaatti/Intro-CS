- dunder methods are magic methods
- you can compare alphabetic letters using ``<`` and ``>`` operators, very efficient for sorting names.
- an abstract data type is a type of an object (can be made by YOU) that contains operations (methods) and objects (attributes) for it.
- OOP helps very much in manipulation of data. It's like functions, avoids copying for them. But it adds also the ability to avoid copying attributes/variables, and it provides polymorphism, inheritance, encapsulation, abstraction and decomposition, helps in fulfilling software designs, etc.
- You can compare instances, and do some crazy operations on them that you can't do with functions (or at least you're limited).
> " The interface defines the behavior of the operations—what they do, but not how they do it. "
- Classes create objects of type ``type``
- attributes can - somehow - refer to methods or the actual variables in a class, while data attributes refer to the actual variables.
- instance variables are these that get created with each new instance, while class variables are these that are not. they typically dont have the 'self'.
- **starting the names of an attribute in a class with and underscore mark them as private variables (They shouldn't be accessed directly). example ``self._elems = []``**
- When defining classes, using the doc strings in the class definition indiacte the class' abstraction, meanwhile the comments below that abstraction description refer to the explanation of the implementation. *" That information is aimed at programmers who might want to modify the implementation or build subclasses of the class, not at programmers who might want to use the abstraction."*

- Example:
```py
class int_set(object):
  """ An Int_set is a set of integers. """
  # Info about the implementation (not the abstraction):
  # Value of a set is represented by a list of ints, self._vals.
  # Each int in a set occurs in self._vals exactly once.
```
