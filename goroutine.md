Note: All references to programming syntax and language describe [[Go]] unless otherwise specified.

A goroutine is any procedure preceded by the `go` keyword in [[Go]], as well as the main thread of execution. 

These procedures communicate solely via [[channel (concurrency)|channels]] and do not return anything. Therefore all procedures called a goroutines must be void functions.

Goroutines are logically [[concurrency|concurrent]], but may not be physically so. Instead, the Go runtime schedules goroutines on threads, waking and sleeping them as necessary. This usually makes them many times more computationally efficient than threads, and allows hundred or thousands of goroutines to be run 'at once' without significant performance detriment. 
Every goroutine has its own [[stack]]. 

`main()` is a goroutine, and when it terminates any other goroutine is also terminated. Therefore starting a goroutine as the last command in `main()` will achieve no result. 

#concurrency