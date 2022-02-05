## Explain what design patterns are and how they are used.
- design patterns are "common solutions to common problems"
- they're tried-and-true ways to organize classes and behaviors

## Recognize and apply the Template Method design pattern to solve a given problem.
- you have a fixed algorithm that does different things for different types
- a method takes objects of any class that implements some interface and calls a method defined in that interface
- that method calls a different version of the interface method depending on the specific subclass/type of the object being passed in

## Recognize and apply the Strategy design pattern to solve a given problem.
- only some animals fly, so don't put `fly()` in an `Animal` class
- also, you should try to avoid creating interfaces just to force the creation of a method/action
- a change in a superclass/interface shouldn't break the subclasses
- use strategy pattern
    - create an interface `Flies` with `flies()`
    - create two classes that implement `Flies`, one called `CanFly` and one called `CantFly`
    - add an instance of `Fly` called `flyingType` to `Animal`
    - then write a method `tryToFly()` that calls `flyingType.fly()`
    - you can also add `setFlyingAbility()` to `Animal` so you can change the flying type for each animal
    - all the subclasses of `Animal`, you can now set `flyingType` to an instance of whichever `Flies` subclass is appropriate
- this doesn't break old classes and allows us to add multiple types of flying (e.g., can fly, can't fly, can flap, can fly when it reaches a certain age, etc.)

## Explain how interfaces reduce coupling while increasing code reuse.
- interfaces reduce coupling and code duplication by allowing all classes that implement the same interface to be used by the same methods
- instead of writing a different method for each class, you can write one that takes in arguments of the interface type
