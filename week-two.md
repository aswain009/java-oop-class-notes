### abstract classes vs interfaces
- neither of these can be instantiated (you can't "new" them up)
    - you "extend" abstract classes, and then you can create objects from those subclasses
    - you "implement" interfaces, and then you can create objects from those subclasses
- classes derived from interfaces or abstract classes are called "concrete classes"; these are classes that can be instantiated (i.e. you can create objects from them)
- abstract classes
    - abstract classes can have implemented methods, abstract methods and properties
    - abstract methods aren't implemented (i.e., they don't have bodies) in the abstract class, but in the subclasses they _must_ be implemented
    - if a subclass doesn't have a constructor, then when you create a new subclass object, Java will run the superclass' constructor
- interfaces
    - none of the methods in an interface are implemented, the interface only lists the signatures of the methods (name, return type, parameters)
    - if a subclass implements an interface, it must define each method listed in the interface
    - there are no properties defined in an interface

### implicit and explicit object conversion
- implicit
    - objects of a subclass can be used anywhere that a superclass object can be used without having to be cast into the parent type
    - if you have a Student object, it can be used anywhere a Person object is required (assuming Student extends/implements Person)
- explicit
    - explicit conversion is when an object is cast into another type
    - a Person object has to be cast with `(Student)personObject` if you want to use Student methods on it

###  final, public, protected, and private


### equals and toString methods for base, derived, and composed classes
- the default `equals()` method in the Object class only returns true if the objects being compared are the exact same object
```
Person x = new Person("tony");
Person y = x;
x.equals(y); // returns true
Person a = new Person("tony");
Person b = new Person("tony");
x.equals(y); // returns false since a and b are pointing to different locations in memory, two seperate objects that happen to have the same name property
```
- you can override `equals()` for your class and make it compare properties instead of literal equality


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

