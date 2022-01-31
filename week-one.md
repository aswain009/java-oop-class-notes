### inheritance
- what it is
    - a hierarchy of classes, each one defining a more specific subset of the parent class (or "superclass")
    - the subclass "is a" version of the superclass
```
vehicle
└─── land-based
│   └─── powered
│       │   train
│       │   car
│   └─── unpowered
│       │   bicicle
│       │   snowboard
│
└─── sea-based
│   └─── powered
│       │   yacht
│       │   cruise ship
│   └─── unpowered
│       │   canoe
│   
└─── air-based
│   └─── powered
│       │   plane
│       │   rocket
│   └─── unpowered
│       │   glider
```
- when to use it
    - if you're using if-elses over and over in your class, based on the "type" of the object
    - each type (subclass) has the same methods, but the logic inside of them is different
        - e.g., in the example design above, all the subclasses will have a method `move()` but they'll be implemented differently
    - each subclass has its own properties and methods (state and behavior), along with the methods/properties from the superclass
- how to use it
    - `public class Student extends Person`
    - you can call the superclass' constructor from the subclass with `super();`
    - you can call any public method from the subclass with `super.nameOfMethod()`
    - parent methods and properties need to be `public` for them to be accessible in subclasses (or by actual instances of the subclass)
- every class implicitly extends Java's base Object class; Object is the parent class of all classes

### override and overload
- override (decorator: `@Override`)
    - you're "overriding" when you make a method with the same name and signature of a method in the superclass
    - when called by an instance of the subtype, the subtype/overridden version of the method will be run
    - if a method in a superclass doesn't need an implementation (i.e., you only need to have logic for it in its subclasses), you can mark it `abstract`
    - this forces every subclass to implement their own version of the method
    - if a method is marked `abstract` then the class must also be marked `abstract`
- overload
    - within the same class, you can have multiple versions of the same method
    - the return types and names must be the same, but the types, number and order of the parameters can be different

### polymorphism
- what it means
    - you can call the same methods and/or use the same logic with objects of different types
    - a different method is called depending on the type of the object
- dynamic method lookup
    - an object gets its type checked and then the correct override of a method is chosen and invoked
    - this happens dynamically, during runtime

### late binding
- what it is
    -  Late binding means that the compiler should perform no argument checks,
       no type checks on a method call and should leave it all to the runtime.
       This is the inherent functionality of Java for implementing polymorphism
       and overriding methods.
       Reference [here](https://stackoverflow.com/questions/22391915/late-binding-in-java)

### Liskov substitution principle and SOLID
- what SOLID stands for
    - single responsibility principle: each class should represent one thing, each method should do only one thing, etc.
    - open-closed principle
        - a system can be extended but should not be modified
        - e.g., you can add a subclass but you can't (or don't have to) change the superclass
        - the superclass is generic enough that you can build off of it without changing it
    - Liskov substitution principle
        - also the "substitution principle"
        - "... every derived class should be substitutable for its parent class." ([The Importance of SOLID Design Principles](https://www.bmc.com/blogs/solid-design-principles/))
        - anywhere where a type T can be used, an S can be used, where S is a subtype of T; this is because the S _is a_ T
    - interface segregation principle: it's better to have a lot of small interfaces rather than one big one, so split classes up as much as possible
    - dependency inversion principle: the coupling between two classes should be as low as possible; one class doesn't have to know about or bother with the implementation of another class it's using
