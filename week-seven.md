## List the common operations and properties of all lists as distinct from collections.
- lists
    - ordered
    - operations happen at a particular index
    - grow/shrink to accommodate add/remove actions
    - `List<T>` extends `Collection<T>` and `Iterable<T>`
- collections
    - unordered
    - have size limits
    - can be equal to each other even if the order of the elements is different
    - `Collection<T>` extends `Iterable<T>`
- `ListIterator<T>`
    - extends `Iterator<T>`
    - adds `hasPrevious()`, `next/previousIndex()`, etc.
    - can be initialized at specific indexes

## autoboxing
- this is when Java automatically converts primitive types into their `Object`/wrapper types
- example where this would be needed: when adding an `int` to an `ArrayList<Integer>`
- primitive -> object is "boxing"
- object -> primitive is "unboxing"

## Extend the AbstractCollection implementation into AbstractList and ArrayList implementations and justify design decisions.


## Analyze the ArrayList implementation to determine algorithmic efficiency.


## Use an ArrayList data structure to solve a problem.

