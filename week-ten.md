## stacks


## infix and postfix
- infix notation
    - e.g. 3 + 7 * 2 - 8 / (6 - 2)
    - it's easy for humans to perform because we jump back and forth and easily follow order of opperations
    - but computers don't have the same top-down view of the problem like we do
- postfix notation
    - e.g. 3 7 2 * + 8 6 2 - / -
        - you loop over the expression, left to right
        - you add each element to a stack (3, then 7, then 2, then *)
        - when you reach an opperand, you pop the last two numbers off the stack and perform the opperation on them
            - pop off 2 and 7 and multiply them
        - then you add the result to the stack
            - the stack now looks like 3, 14
        - you end up with one number on the stack, the final answer
    - this is easy for a computer to calculate
    - a computer simply goes through the characters/numbers one at a time
    - it doesn't have to have a top-down view of the problem or jump around to figure out the order in which opperations have to be done
    - you can use a stack to evaluate the expressionwith a simple algorithm
