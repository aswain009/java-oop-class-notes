## queues
- queues are FIFO structures (first in, first out)
- they're an array of elements where you can only add to the beginning and remove from the end
- examples of real-world queues
- methods that queues (should) implement
    - `bool queue(E data)` adds `data` to the begining of the array
    - `E enqueue()` removes and returns the last element in the array
    - `E peek()` returns the last element in the array without removing it
    - `bool isEmpty()` tells whether the array has any elements in it (obviously)
