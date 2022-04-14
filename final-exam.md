# final exam topics

## essay questions
- Value of implementing Data Structures and Code reuse. These questions are sort of ‘in your opinion’ questions and what I would be looking for is to use your knowledge of those topics and provide to me a response of a particular question. No coding required for those two questions.
- Know...
    - the ‘Shunting-yard algorithm’
        - e.g. 3 + 7 * 2 - 8 / (6 - 2)
        - e.g. 3 7 2 * + 8 6 2 - / -
    - the idea of semaphores
    - the shortest path algorithm
    - the structured programming movement

## short answer questions
1) stack Big(O)
2) Queue principles
3) Adapter design principles
4) Decorator design pattern principle
5) ArrayList principles
6) Lists and Big(O)
7) LinkedList principles
8) Know your interfaces and what they do: iterator, iterable, listIterator, Collection, list

## multiple-choice
1) ArrayList and LikedList efficiencies - efficiencies for removing, adding , etc
2) Choose best collection to apply for a given situations: storing payroll calculations, program to track progress in a maze, keeping track of customers in alphabetical order, Driving dispatching system like uber

Basically make sure you know the ins and outs of the following data structures: ArrayList, LinkedList, Queue, or Stack

## coding problems

### Decorator Pattern coding problem:
1) Desc: Need to create a system to allow for basic seat reservations and decorations for adding wifi.
2) You're given a UML diagram where you'll need to implement a few classes.  
3) What you need to do is to look at the UML diagram and simply implement the methods using the decorator method
4) You will be given an sample of what your output should look like.
5) you will be given a 'RunMe.java' file with starter code.
Go over what the Decorator classes do:
1) Remember to declare your main object, FightSeat
2) then just code up your getters and remember to instantiate the constructor for the Classes extending the decorator classes
1) just call the super class (FltSeatDecorator) and do your modifications locally

### Stacks problem
1) Desc: The given problem is about balancing parentheses, obv you have to make sure each parentheses has it's open and respective closed parentheses
2) Example: "[{}], {}, ([{}])" are balanced, [{}, {, ({) are NOT
3) Using a stack you need to check if a particular string is balanced or not.  Return a true or false
4) tips: perhaps a string of opening strings, like {({
5) have a string of closing strings like })]
6) What you need to do is to iterate through the tokens
7) if the tokens are starting strings then push to the stack
8) if not then see that means it is an ending string so see if that particular string matches the top of the stack
9) work your way through the rest of the tokens
10) return false if any of the above steps don't work.
11) if the stack is empty then you know it's true, so return that
12) Conclusion: know how stacks work and know your stacks methods: empty(), push(), pop()

### Queues problem
1) Desc - Need to implement a publish/subscribe model (like YouTube, etc) by implementing two classes 
2) Will be given a UML diagram for the methods and variable for each class you need to implement.  There are links to APIs you may need embedded in the specification
3) You will be given a Queue object of a particular class will need to do such things as reading and removing oldest notifications (poll) , getting number of notifications(size),
check if two subscribers are equal
4) Conclusion: pretty simple problem, know how to use poll and size methods of queue.

### Lists problem
1) Desc:  Implement two methods using the List class. Links to the applicable Java API will be available.
2) You will do the following:
- Reverse a list in place in O(n) time, should not need to create any new lists.
- Merge two sorted lists in O(n+m) time. same as what was done in the Polynomial HW. result should be ordered ascending.
3) Need to know the following interfaces: List and ListIterator methods and understand what they do.  
3) So how do you reverse a list?  Possibly have two list iterators from List class and iterate between both lists with one list starting from the end?
4) How do you merge a list?  May need to do some comparisons.  Again call list iterator from each list 
5) How do you declare a ListIterator obj? `ListIterator<E> blah = somelist.listIterator();`
6) Then manipulate blah to do the merge operation. You're comparing each letter in each list to see if one comes before the other in alphabet and take that one and add to result.
