### abstract classes vs interfaces
- classes and abstract classes define what an object _is_; an interface defines what an object can _do_
- neither of these can be instantiated (you can't "new" them up)
    - you "extend" abstract classes, and then you can create objects from those subclasses
    - you "implement" interfaces, and then you can create objects from those subclasses
        - **but** you can assign an object that implements, say, the Measurable interface to a variable of type Measurable; you can't instantiate a Measurable, but you can use it as a variable type
- classes derived from interfaces or abstract classes are called "concrete classes"; these are classes that can be instantiated (i.e. you can create objects from them)
- abstract classes
    - abstract classes can have implemented methods, abstract methods and properties
    - abstract methods aren't implemented (i.e., they don't have bodies) in the abstract class, but they _must_ be implemented in the subclasses
    - if a subclass doesn't have a constructor, then when you create a new subclass object, Java will run the superclass' constructor
- interfaces
    - an interface defines how we interact with the object (what the object can do)
    - none of the methods in an interface are implemented, the interface only lists the signatures of the methods (name, return type, parameters)
    - if a subclass implements an interface, it must define each method listed in the interface
    - there are no properties defined in an interface
- a class can `extend` only one class, but it can `implement` as many interfaces as needed
- you can design a program to have an interface the then an abstract superclass that implements the interface, then subclasses that extend the abstract class
    - let's say we have an `interface Person`, that describes what each `Person` type _has_ to be able to do
    - then an abstract class (`AbstractPerson`) either implements each method from the interface _or_ marks it abstract to force the subclasses to implement them
    - each subclass that extends `AbstractPerson` must implement any methods marked as abstract in `AbstractPerson`

### implicit and explicit object conversion
- implicit
    - objects of a subclass can be used anywhere that a superclass object can be used without having to be cast into the parent type
    - if you have a `Student` object, it can be used anywhere a `Person` object is required (assuming `Student` extends/implements `Person`)
- explicit
    - explicit conversion is when an object is cast into another type
    - a `Person` object has to be cast with `(Student)personObject` if you want to use `Student` methods on it

### overriding equals method
- the default `equals()` method in the `Object` class only returns true if the objects being compared are the exact same object
```
Person x = new Person("tony");
Person y = x;
x.equals(y); // returns true
Person a = new Person("tony");
Person b = new Person("tony");
x.equals(y); // returns false since a and b are pointing to different locations in memory, two seperate objects that happen to have the same name property
```
- you can override `equals()` for your class and make it compare properties instead of literal equality
```
@Override
public boolean equals(Object object)
{
    if (object != null && object instanceof Person)
    {
        Person incomingPerson = (Person)object; // because we know object is instanceof Person, we won't get an error when .name is checked below
        return name.equals(incomingPerson.name); // equals() on a string directly compares the strings themselves
    }
    else
    {
        return false;
    }
}
```
- don't forget you can use `super.equals(incomingObject)` to use the superclass' `equals()` inside your subclass' `equals()` to minimize code duplication!
- `equals()` for doubles and floats
    - you should check to see if the values are "close enough", since they could vary by tiny amounts
    - `Math.abs(oneValue - otherValue) < 1e-6`

### types of classes
- concrete: a regualr class; it can be instantiated (you can "new" it up)
- base: a parent class, a class that another class extends
- derived: a child class, a class that extends another class
- abstract: a class that has one or more abstract methods in it
- static: you can't create an object from a static class; you use a member defined in a static class with `ClassName.MethodName()/PropertyName`; 
- final: creates an immutable class; values remain the same throughout the program; cannot be extended/subclassed; final methods cannot be overriden; final variables can only be assigned once
- (interfaces aren't classes, they're more like blueprints for classes)

### composition
- **???**

### callback methods
- **???**

### open-closed, interface segregation, and dependency inversion principles (SOLID)
- open-closed
    - a system can be extended but should not be modified
    - e.g., you can add a subclass but you can't (or don't have to) change the superclass
    - the superclass is generic enough that you can build off of it without changing it
- interface segregation
    - it's better to have a lot of small interfaces rather than one big one, so split classes up as much as possible
- dependency inversion
    - high-level modules shouldn't depend on low-level modules, they shouldn't have to know what's going on in them
    - another way to put it, the coupling between two classes should be as low as possible, one class doesn't have to know about or bother with the implementation of another class it's using
    - changing one of the classes shouldn't change how the other class (the dependent class) uses it

### cohesion and coupling
- the goal: classes should have strong cohesion, weak coupling
- cohesion: each class should do only one thing
- coupling
    - you should have one place to define, abstractly, what a thing should do (with and interface) and one place where those methods are actually defined (in a concrete class)
    - classes shouldn't depend on the details of another class, the classes should work independently
    - changing how one of them works shouldn't break the other

### access modifiers
![access modifiers](https://github.com/ruthrootz/java-oop-class-notes/blob/main/access-modifiers.png)
