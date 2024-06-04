### Python Exceptions 
**There are (at least) two distinguishable kinds of errors: syntax errors and exceptions**
## What are Exceptions? 
> Errors detected during execution are called exceptions and are not unconditionally fatal

### Exceptions come in different types, and the type is printed as part of the message:

1.BaseException: The base class for all built-in exceptions.

2.Exception: The base class for all built-in, non-system-exiting exceptions.

### built in Exceptions :
In Python, all exceptions must be instances of a class that derives from BaseException. In a try statement with an except clause that mentions a particular class, that clause also handles any exception classes derived from that class (but not exception classes from which it is derived). Two exception classes that are not related via subclassing are never equivalent, even if they have the same name.

### Handling Exceptions: 
It is possible to write programs that handle selected exceptions


#### BaseException:
The base class for all built-in exceptions.
> BaseException is the common base class of all exceptions. One of its subclasses, Exception, is the base class of all the non-fatal exceptions. Exceptions which are not subclasses of Exception are not typically handled, because they are used to indicate that the program should terminate. They include SystemExit which is raised by sys.exit() and KeyboardInterrupt which is raised when a user wishes to interrupt the program.

#### Exception context :
Three attributes on exception objects provide information about the context in which the exception was raised:

BaseException.__context__

BaseException.__cause__

BaseException.__suppress_context__

When raising a new exception while another exception is already being handled, the new exception’s __context__ attribute is automatically set to the handled exception. An exception may be handled when an except or finally clause, or a with statement, is used.

Exception can be used as a wildcard that catches (almost) everything. However, it is good practice to be as specific as possible with the types of exceptions that we intend to handle, and to allow any unexpected exceptions to propagate on.

The most common pattern for handling Exception is to print or log the exception and then re-raise it (allowing a caller to handle the exception as well):

### one of the ways to handle Exceptions : 

A try statement:
> may have more than one except clause, to specify handlers for different exceptions. At most one handler will be executed.

### The try statement works as follow:

First, the try clause (the statement(s) between the try and except keywords) is executed.

If no exception occurs, the except clause is skipped and execution of the try statement is finished.

If an exception occurs during execution of the try clause, the rest of the clause is skipped. Then, if its type matches the exception named after the except keyword, the except clause is executed, and then execution continues after the try/except block.

If an exception occurs which does not match the exception named in the except clause, it is passed on to outer try statements; if no handler is found, it is an unhandled exception and execution stops with an error message.