## generics
- generic types cannot be primitives
    - you have to use the wrapper classes Java provides (`Integer` instead of `int`, etc.)
    - this is called "boxing", putting a primitive into a value type
    - unboxing is where you convert a value type into a primitive
- `Collection`
    - it's an interface that extends `Iterable`
    - various data structures inherit `Collection`
    - its generic, so when you instantiate a collection you have to provide a type
    - unlike `Lists`, collections don't guarantee order
    - if you want to iterate over a collection, you have to create a class that implements `Iterator<T>`
        - _AND_ the collection class must implement `iterator()` that returns an instance of the `Iterator<T>` class
            - the requirement for `iterator()` comes from the `Iterable` interface
        - you can then instantiate and use that iterator in your collection class to loop over your collections
        - there should be a method in your collection class that returns a new `Iterator<T>` / `ConcreteIteratorClassYouMade`
        - if your collection class implements `Iterable` (i.e. it has a method `iterator()` that creates an `Iterator<T>`), then you should be able to use a for-each loop on it
            - `for ([whatever your collection type is] i : collection) { }`
        - the iterator class can have a `remove()` method
        ```
        public void remove() {
            if (!nextCalled) {
                throw new IllegalStateException("No prior call to next");
            }
            --index;
            data[index] = data[size - 1];
            data[size - 1] = null;
            --size;
            nextCalled = false;
        }
        ```
        - `nextCalled` is set to true each time `next()` is called because the element at `index` cannot be removed if it hasn't been iterated over using yet
            - you wouldn't know what you're removing if you don't call `next()` first
        - this design, where you have a method (`iterator()`) that returns a new object that can be called on to do a job is the **factory pattern**
            - the factory class is the concrete class that creates/implements `Iterator<T>`

## type parameters
A type parameter is essentially a variable that holds a reference to a type instead of a value. Generic classes are classes that take in a type parameter and create an instance of the class that uses that type parameter wherever it is used in the generic class definition. Example, you can create an instance of `SomeConcereteCollection<T>` that holds a collection of `Person` like this: `new SomeConcereteCollection<Person>()`.

## bound type parameter
The method `binarySearch()` needs to compare the values in the array `arr` in order to perform the search, so the array that gets passed in must be a type that implements `Comparable`. The bound parameter `T extends Comparable` makes sure of this.

## type erasure
Type erasure happens when the Java compiler replaces generic types with the concrete types implied by the parts of the code that instantiate the generic classes. By the time the JVM gets to runtime, the bytecode has no reference to generic types. Everything has been given concrete types.
