### abstract classes vs interfaces
- neither of these can be instantiated (you can't "new" them up)
    - you "extend" abstract classes, and then you can create objects from those subclasses
    - you "implement" interfaces, and then you can create objects from those subclasses
- abstract classes
    - some/all of the methods can be marked with abstract
    - abstract methods aren't implemented (i.e., they don't have bodies) in the abstract class, but in the subclasses they _must_ be implemented
    - the abstract class can have implemented methods, abstract methods and properties
    - if a subclass doesn't have a constructor, then when you create a new subclass object, Java will run the superclass' constructor
- interfaces
    - none of the methods in an interface are implemented, the interface only lists the signatures of the methods (name, return type, parameters)
    - if a subclass implements an interface, it must define each method listed in the interface
    - there are no properties defined in an interface

### implicit and explicit object conversion


### abstract and concrete classes and methods


###  final, public, protected, and private


### equals and toString methods for base, derived, and composed classes


### open-closed, interface segregation, and dependency inversion principles (SOLID)
- open-closed
    - a system can be extended but should not be modified
    - e.g., you can add a subclass but you can't (or don't have to) change the superclass
    - the superclass is generic enough that you can build off of it without changing it
- interface segregation
    - it's better to have a lot of small interfaces rather than one big one, so split classes up as much as possible
- dependency inversion
    - the coupling between two classes should be as low as possible, one class doesn't have to know about or bother with the implementation of another class it's using

### access modifiers

