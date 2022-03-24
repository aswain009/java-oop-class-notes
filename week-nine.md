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
    - 
- `UnmodifiableCollection`
    - 
