## I.12.4.2.1 Exceptions thrown by the CLI

CLI instructions can throw the following exceptions as part of executing individual instructions. The documentation for each instruction lists all the exceptions the instruction can throw (except for the general purpose `System.ExecutionEngineException` described below that can be generated by all instructions).

Base Instructions (see [Partition III](#todo-missing-hyperlink))

 * `System.ArithmeticException`

 * `System.DivideByZeroException`

 * `System.ExecutionEngineException`

 * `System.InvalidAddressException`

 * `System.OverflowException`

 * `System.SecurityException`

 * `System.StackOverflowException`

Object Model Instructions (see [Partition III](#todo-missing-hyperlink))

 * `System.TypeLoadException`

 * `System.IndexOutOfRangeException`

 * `System.InvalidAddressException`

 * `System.InvalidCastException`

 * `System.MissingFieldException`

 * `System.MissingMethodException`

 * `System.NullReferenceException`

 * `System.OutOfMemoryException`

 * `System.SecurityException`

 * `System.StackOverflowException`

The `System.ExecutionEngineException` is special. It can be thrown by any instruction and indicates an unexpected inconsistency in the CLI. Running exclusively verified code can never cause this exception to be thrown by a conforming implementation of the CLI. However, unverified code (even though that code is conforming CIL) can cause this exception to be thrown if it might corrupt memory. Any attempt to execute non-conforming CIL or non-conforming file formats can result in unspecified behavior: a conforming implementation of the CLI need not make any provision for these cases.

There are no exceptions for things like 'MetaDataTokenNotFound.' CIL verification (see [Partition III](#todo-missing-hyperlink)) will detect this inconsistency before the instruction is executed, leading to a verification violation. If the CIL is not verified this type of inconsistency shall raise `System.ExecutionEngineException`.

Exceptions can also be thrown by the CLI, as well as by user code, using the `throw` instruction. The handling of an exception is identical, regardless of the source.
