# Mutex and Channel basics

### What is an atomic operation?
> Atomic operations in concurrent programming are program operations that run completely independently of any other processes.

### What is a semaphore?
> A variable used to control the acess to a common resource by multiple processes in a concurrent system. It's a flag saying whether or not the resource is in use

### What is a mutex?
> Mutual exclusion is a property of concurrency control preventing race conditions.

### What is the difference between a mutex and a binary semaphore?
> A mutex can only be released by the thread which has ownership, i.e. the thread which previously called the Wait function. A semaphore can be released by any thread.
> A thread can call a wait function repeatedly on a mutex without blocking. However, if you call a wait function twice on a binary semaphore without releasing the semaphore in between, the thread will block.

### What is a critical section?
> A Critical Section is the part of a program that accesses shared resources. Only when a process is in its Critical Section can it be in a position to disrupt other processes. We can avoid race conditions by making sure that no two processes enter their Critical Sections at the same time.

### What is the difference between race conditions and data races?
 > A data race occurs when 2 instructions from different threads access the same memory location, at least one of these accesses is a write and there is no synchronization that is mandating any particular order among these accesses.
 > A race condition is a semantic error. It is a flaw that occurs in the timing or the ordering of events that leads to erroneous program behavior. Many race conditions can be caused by data races, but this is not necessary.

### List some advantages of using message passing over lock-based synchronization primitives.
> A system built of Message passing semantics is inherently more scalable. Since message passing implies that messages are sent asynchronously, the sender is not required to block until the receiver acts on the message.
> The state of Mutable/Shared objects are harder to reason about in a context where multiple threads run concurrently.

### List some advantages of using lock-based synchronization primitives over message passing.
> Some algorithms tend to be much simpler.
>A message passing system that requires resources to be locked will eventually degenerate into a shared object systems.
>If algorithms are wait-free, you will see improved performance and reduced memory footprint as there is much less object allocation in the form of new messages.
