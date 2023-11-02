Channels in [[concurrency|concurrent programming]] are a method by which concurrent processes can communicate, specified in the [[Message Passing Model]].
A process can pass a message along a channel, where it can be read by another process. The read message is then removed from the channel.

Reading from and writing to channels is blocking, and as such execution on a thread will halt until either the channel being read from has a message passed down it, or the channel being written is emptied by a read.

Channels can be buffered, meaning they can store multiple sent messages. Reading from a buffered channel returns the oldest message, in a FIFO system. 
An unbuffered channel has a buffer of length 0, and always block on successive writes or reads.

A system with no buffered channels is said to implement the synchronous approach of the MPM, and if buffers exist then the system used the asynchronous approach.
Asynchronous (buffered) channels are generally more desirable, as they allow further computational independence, but they are more difficult to reason about.

Channels are theoretically lossless, as every written item can be read, and an item can only be removed by reading its value.
# Go
[[Go]] implements the MPM as a manifestation of the philosophy of Rob Pike, one of Go's co-creators:
> "Do not communicate by sharing memory; instead, share memory by communicating."

Channels are created in [[Go]] via the `make()` command. For example, a channel of integers is created with `myChannel := make(channel int)` This is similar to `malloc()` in C, and technically returns a pointer to the memory location allocated for the channel. 
A buffered channel is made by specifying a non-zero size of buffer as a third argument. 
Writing to and reading from a channel is done with `<-`:
- Writing - `myChannel <- myData`
- Reading - `myData := <- myChannel` or `mydata = <- myChannel`

The concrete implementation of channels in Go involves the [[Shared Memory Model]]. 
Every unbuffered channel is a struct containing a memory location and a [[mutual exclusion#Mutex lock|mutex lock]]. 

## Buffered channels
Every buffered channel is a struct containing a circular queue of n indexed locations, a send index, a receive index, and a mutex lock.
When an item is sent to a buffered channel it is copied to the address in the queue given by the send index, and the send index is incremented by 1. A similar process occurs when reading, in that the data the address specified by the receive index is removed and returned, then the index is incremented.
If either index is greater than the length of the queue, it is returned to 0, and so the indexes can be thought of as [[modular numbers]] of modulus equal to the length of the buffer.
If the location being written to is full, or the one being read from empty, then the [[goroutine]] requesting access to the channel waits until this is not the case. 

Writing to a buffer is done by copying the data from the goroutine's [[stack]], rather than passing a pointer. This is done to ensure that no data in a buffer is lost when a routine terminates.