# Process Coordination

## Busy waiting
A busy waiting is a process repeatedly checks if a condition is true.

### Avoid busy waiting
* Do something that hand over the CPU usage, for example, I/O.
*

## Starvation & Deadlock
Consider the following situation:

Process p1 is in a critical section c1 waiting for process p2 to get out of a critical section c2. Process p2, meanwhile, is waiting for process p1 to get out of c1. Both p1 and p2 are stuck: each is waiting to get into a critical section being executed by the other.

This sort of circular waiting is called a **deadlock**.

Another problem related to process coordination is **starvation**. This problem arises when one or more processes waiting for a critical section are never allowed to enter the region.

## Process Synchronization
Processes are categorized as one of the following two types:
* **Independence Process**: Execution of one process does not affect other process.
* **Cooperative Process**: Execution of one process affects other process.

** Process synchronization problem arises in the case of Cooperative process

### Critical Section Problem
Critical section is a code segment that can be accessed by only one process at a time. It contains shared variables which need to be synchronized.

Any solution to the critical section problem must satisfy three requirements:
* **Mutual Exclusion**: If a process is executing in its critical section, then no other process is allowed to execute in critical section.

* **Progress**: If no process is in critical section, then no other process can block it from entering in critical section.

* **Bounded Waiting**: A bound must exist on the number of times that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted.

#### Peterson's Solution
There are two shared variables in Peterson's solution.
* bool flag[i]: Initialized to false, i.e. initially no one is interested in entering the critical section.
* int turn: The process whose turn is to enter the critical section.

![Peterson's Solution](https://www.geeksforgeeks.org/wp-content/uploads/gq/2015/06/peterson.png)

Disadvantage:
* Involves Busy waiting
* limited to two processes.
