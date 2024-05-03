Deadlock is a state in the execution of a concurrent program in which all threads are waiting on another thread to return a value. This leads to the program failing to complete execution.

There are 4 conditions necessary for a deadlock to occur:
- [[mutual exclusion|Mutual exclusion]] - once a process is using a particular resource, the resource is unavailable to any other process.
- Resource holding - a process uses a particular resource until it has completed the required task, taking a non-zero amount of time
- No pre-emption - the lack of ability for an arbitrator to halt a task and/or withdraw the resource it is using
- Circular wait - the possibility of a procedure to wait for a resource while holding a separate resource, facilitating a 'circle' of procedures waiting on the previous procedure

#concurrency