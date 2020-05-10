## I.12.3.2.3 Variable argument lists

The CLI works in conjunction with the class library to implement methods that accept argument lists of unknown length and type ("vararg methods"). Access to these arguments is through a type-safe iterator in the library, called `System.ArgIterator` (see [Partition IV](#todo-missing-hyperlink)).

The CIL includes one instruction provided specifically to support the argument iterator, `arglist`. This instruction shall only be used within a method that is declared to take a variable number of arguments. It returns a value that is needed by the constructor for a `System.ArgIterator` object. Basically, the value created by `arglist` provides access both to the address of the argument list that was passed to the method and a runtime data structure that specifies the number and type of the arguments that were provided. This is sufficient for the class library to implement the user visible iteration mechanism. From the CLI point of view, vararg methods have an array of arguments like other methods. But only the initial portion of the array has a fixed set of types and only these can be accessed directly using the `ldarg`, `starg`, and `ldarga` instructions. The argument iterator allows access to both this initial segment and the remaining entries in the array.