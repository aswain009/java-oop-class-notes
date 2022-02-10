## Explain the purpose and use of exception handling for error detection and correction.
- exception handling is used when the point at which an exception occurs is different from the point at which that error can or could have been corrected
- uncaught exceptions terminate the program

## Differentiate between checked and unchecked exceptions.
- checked exceptions are exceptions that are explicitly thrown in the code
- unchecked exceptions are 

## Use the keywords throws, try, throw, catch, and finally to implement exception handling.
- `throw` indicates you've found an error, something that you can't fix
- `try` blocks wrap code that _might_ throw an exception
- you can then `catch` exceptions in the catch block
- a caught exception doesn't terminate the program
```
try
{
    var result = methodThatMightThrowException();
}
catch (ExceptionType e)
{
    // handle error here
}
```

## Define and use a domain-specific exception hierarchy.

Read and write text files.
Read and write binary files.
Read and write serialized object files.
Define and explain the Serializable interface
Distinguish between random and sequential access files.
