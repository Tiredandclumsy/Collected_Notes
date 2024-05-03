Go is a programming language developed by Google, supporting simple concurrent programming in a C-like syntax.

Go uses [[channel|channels]] to allow [[concurrency|concurrent]] execution, via the [[Message Passing Model]].  The `go` keyword followed by a procedure executes that procedure as a [[goroutine]], dispatching it to execute concurrently then immediately returning to the main thread of execution. The procedure cannot return a value, and instead communicates by sending messages along any number of channels.

# Syntax
## Functions
Functions are variables of type `func`, specifically `func(inputType1, ...) outputType1, ...`. They are initialised differently to regular variables, however:
``` Go
func myFunc (myInput1 inputtype1, myInput2 inputtype2, ...) outputtype {
	...
	return myOutput
}
```

This syntax allows [[goroutine|goroutines]] to be anonymous functions: `go func myFunc(inputType1, ...) outputType1, ...`

The variable nature of functions allows for simple implementation of higher order functions, simply by passing them as arguments:
``` Go
func myHighLevel (myFunction func(inputtype1) outputtype1, ...) outputtype2 {
	...
	return myOutput
}
```

## Make()
`make(t Type, size... IntegerType) Type` returns an object (in reality, a pointer) of the specified type and size on the heap.  For example, creating an array of `int`s of a size dependent on a variable requires `make()` in the following way:
``` Go
newArray := make([]int, desiredLength)  
```

# Communication
Go supports the [[Message Passing Model]] by default, as described above. However, the [[Shared Memory Model]] can be implemented by passing pointers to goroutines through channels. Therefore the SMM is facilitated by the MPM in Go.


#languages