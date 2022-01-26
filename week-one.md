### inheritance
- what it is
    - a hierarchy of classes, each one defining a more specific subset of the parent class (or "superclass")
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
│       │   cannoue
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
    - each subclass can have its own properties and methods (state and behavior), along with the methods/properties from the superclass
- how to use it
    - `public class Hourly extends Employee`
    - write a constructor for the subclass
    - you can call the superclass' constructor from the subclass with `super();`
    - you can call any public method from the subclass with `super.nameOfMethod()`
    - parent methods and properties need to be `public` for them to be accessible in subclasses
- every class implicitly extends Java's base Object class

### override and overload
- `@Override`
    - tells the compiler that the name and signature of the tagged method is the same as one in the superclass
    - when called by an instance of the subtype, the subtype/overridden version of the method will be run
    - if a method in a superclass doesn't need an implementation, you can mark it `abstract`
    - this forces any subclass to have to implement their own version of the method
    - if a method is marked `abstract` then the class must also be marked `abstract`
- `@Overload`
    - within the same class, you can have multiple versions of the same method by tagging them with `@Overload`
    - the return types and names must be the same, but the types, number and order of the parameters can be different

### polymorphism
- what it means
    - you can call the same methods and/or use the same logic with objects of different types
    - a different method is called depending on the type of the object

### late binding

### open-close principle
- what it says
    - a system can be extended but not modified
    - e.g., you can add a subclass but you can't (or don't have to) to change the superclass
    - the superclass is generic enough that you can build off of it without changing it

### Liskov substitution principle, aka SOLID
- what it states
    - anywhere where a type T can be used, an S can be used, where S is a subtype of T
    - doesn't necessarily work the other way around, the subtype S can have methods/properties not included in T, so using a T in place of an S can cause errors if something only in S is called on an instance of T
