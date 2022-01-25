### inheritance
- what it is
    - a heirarchy of classes, each one defining a more specific subset of the parent class
```
vehicle
│   land-based
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
    - e.g., in the example heirarchy above, all the subclasses will have a method `move()` but they'll be implemented differently

### overload vs. override

### organize classes into an inheritance hierarchy

### calling superclass methods

### polymorphism

### late binding

### Liskov substitution principle, aka SOLID
