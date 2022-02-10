## Explain the purpose and use of exception handling for error detection and correction.
- exception handling is used when the point at which an exception occurs is different from the point at which that error can or could have been corrected
- uncaught exceptions terminate the program

## Differentiate between checked and unchecked exceptions.
- unchecked exceptions are exceptions that are due to programmer error
    - the programmer can write code to avoid these exceptions
- checked exceptions are exceptions that are explicitly thrown in the code

## Use the keywords throws, try, throw, catch, and finally to implement exception handling.
- `throw` indicates you've found an error, something that you can't fix
- `try` blocks wrap code that _might_ throw an exception
- you can then `catch` exceptions in the catch block
- a caught exception doesn't terminate the program
- you can chain `catch` blocks to catch specific exception types
- the `finally` block always runs, whether an exception was thrown or not
```
try
{
    var result = methodThatMightThrowException();
}
catch (SomeExceptionType e)
{
    // handle error here
}
catch (RuntimeException e)
{
    // handle error here
}
finally
{
    // this code will run no matter what
}
```
- `throws`

## Define and use a domain-specific exception hierarchy.

Read and write text files.
Read and write binary files.
Read and write serialized object files.
Define and explain the Serializable interface
Distinguish between random and sequential access files.
