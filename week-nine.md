## decorator pattern
- a decorator class implements some interface
    - it _is an_ [insert interface name here]
- BUT it also _has an_ instance of that interface
- "decoratee" is the instance of the interface that the decorator class has
- if you extend the decorator class...
    - instances of this concrete class can make the instance in the decorator class _immutable_
    - IF you `@Override` all the methods that modify the decoratee
    - this way you can safely make an instance of the concrete decorator that has an immutable [insert interface name here]
- any subclasses the interface requires must also be decorated, both in the decorator class and any concrete classes that extend the decorator

## decorator example (from Dr. Whittaker)
- `CollectionDecorator`
    - the decorator class itself
    - implements `Collection`
    - has an instance of `Collection`
    - also has a subclass `IteratorDecorator` that implements `Iterator` and has an instance of `Iterator`
- `UnmodifiableCollection`
    - extends `CollectionDecorator`
    - overrides all of its methods
    - leaves methods that modify the collection unimplemented (i.e. they throw `Unimplemented` exceptions)
    - also has a subclass `UnmodifiableIterator` that extends `IteratorDecorator`
        - the iterator methods that modify the collection (`remove`, `add`, etc.) throw `Unimplemented` exceptions
