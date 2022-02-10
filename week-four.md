## Explain the purpose and use of exception handling for error detection and correction.
- exception handling is used when the point at which an exception occurs is different from the point at which that error can or could have been corrected
- uncaught exceptions terminate the program
- the place where an exception is thrown is always different than the place it gets caught
    - because you can't or don't want to fix the error in the same place where it happened

## Differentiate between checked and unchecked exceptions.
- unchecked exceptions are exceptions that happen during runtime
    - unchecked exceptions are subclasses of `RuntimeException`
    - they happen due to programmer error
    - the programmer can write code to avoid these exceptions
- checked exceptions are exceptions that are explicitly thrown in the code
    - checked exceptions are subclasses of `Exception`
    - they account for things that happen that are outside of the programmer's control
    - all checked exceptions must be caught or declared to be thrown
        - `throws` is used to show that a method throws checked exceptions
        - `public void someMethod() throws FileNotFoundException, SomeOtherCheckedException`
        - wherever the function is called, it has to either be in a method that is marked with `throws` or it has to catch the exception/s

## Use the keywords throws, try, throw, catch, and finally to implement exception handling.
- `throw` indicates you've found an error, something that you can't fix
- `try` blocks wrap code that _might_ throw an exception
- you can then `catch` exceptions in the catch block
- a caught exception doesn't terminate the program
- you can chain `catch` blocks to catch specific exception types
    - when chaining, you have to put the catch blocks in order of most to least specific exception types
    - e.g., put `IOException` after `FileNotFoundException` because `FileNotFoundException` is a subclass of `IOException`
        - if you caught them in the other order, `IOException` first, all `IOExceptions` _and_ `FileNotFoundExceptions` would be caught by the fist block (`IOException`), since `FileNotFoundException` _is an_ `IOException`
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

## Define and use a domain-specific exception hierarchy.
- **???**

## Read and write text files.
```

```

## Read and write binary files.
## Read and write serialized object files.
## Define and explain the Serializable interface
## Distinguish between random and sequential access files.
