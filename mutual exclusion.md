Mutual exclusion refers to any process that ensures no two [[concurrency|concurrent]] threads access the same [[mutual exclusion#Critical Sections|critical section]] at the same time. Simultaneous access is a [[race condition#Data race|data race]], and can cause unpredictable, undesirable, and even non-deterministic execution. 

# Critical Sections
A critical section is a section of code in a concurrent program that allows access to a shared resource. Critical sections are guaranteed in the [[Shared Memory Model]], but are usually abstracted away in any language implementing the [[Message Passing Model]]. 

# Methods
## Mutex lock
A Mutex lock (short for mutual exclusion lock) ensures mutual exclusion via 'locking' a critical section. Whenever a thread requires access to the section it is given a unique key, or token, that permits it to enter the section. If no key is available, the thread waits or is put to sleep until a/the key becomes available.