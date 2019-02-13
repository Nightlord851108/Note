# Difference between Multi-tasking, Multi-threading, Multi-processing.
refs: https://www.geeksforgeeks.org/operating-system-difference-multitasking-multithreading-multiprocessing/

* Multiprogramming: A computer running more than one program at a time (Like running keynotes and safari simultaneously).

* Multiprocessing: One computer using more than one CPU at a time.

* Multitasking: Tasks sharing a common resource (like CPU).

* Multithreading: An extension of multitasking.

## Category
* [Multiprogramming](#Multi-Programming)
* [Multiprocessing](#Multi-Processing)
* [Multitasking](#Multi-Tasking(Time-Sharing))
* [MultiThreading](#Multi-Threading)

## Multi Programming
In a computer system, there are multiple processes (or sometimes called jobs) waiting to be executed. Since the main memory is too small to accommodate all of these processes, these processes are initially kept in an area-- called job pool.

CPU will select one job from job poll, bring it to main memory and start executing it.

### Non-multi programmed system
* If the job leaves CPU and go for other task-- for example, I/O-- CPU has to wait for the job back.
* During the time waiting for job, CPU is idle, however, CPU **cannot execute** other jobs in job pool, since CPU is still assigned to previous job.
* CPU should not be stuck by a process for too long time, therefore, multi programming came up.

### Multi programmed system
**The main idea of multi programming is to maximize the CPU time.**

* Once a job goes into I/O task, the OS interrupts the job, choose another job from job pool, allocate CPU to the new job and starts its execution.

* As soon as the previous job completes its I/O tasks and comes back to CPU tasks, the CPU is allocated to it.


## Multi Processing
Multiprocessing is the use of multiple CPUs(processors) in a computer system.
In a uni-processor system, only one process can be execute at a time. Since there are multiprocessor available, we are able to execute multiple processes simultaneously.

### Multi processing system’s working
* With the help of multiprocessing, many processes can be executed simultaneously. Say processes P1, P2, P3 and P4 are waiting for execution. Now in a single processor system, firstly one process will execute, then the other, then the other and so on.

* But with multiprocessing, each process can be assigned to a different processor for its execution. If its a dual-core processor, two processes can be executed simultaneously and thus will be two times faster.

### Why Multi processing?
* Main advantage is the more works are done in a shorter time.

* It also increase the reliability in the sense that if one processor fails, the work does not halt, it only slows down.

* Multiprocessing refers to the hardware rather than software.

## Multi Tasking(Time Sharing)
Multi tasking is a logical extension of multi programming. The major way in which multitasking differs from multi programming is that multi programming works solely on the concept of context switching whereas multitasking is based on **time sharing** alongside the concept of context switching.

* In a time sharing system, each process is assigned a quantum of time for which a process is meant to execute.

* The processes share the time slices. As soon as the time quantum of one process expires, another process begin.

* Multi tasking also occurs context switching, however, it's so quick that user can interact with each program separately.

* It gives user a illusion of the program is running simultaneously (in fact, there's always only one executing program per processor)

** In a more general sense, multitasking refers to having multiple programs, processes, tasks, threads running at the same time.

![Multi tasking image](https://www.geeksforgeeks.org/wp-content/uploads/multitasking.jpg)


## Multi Threading
A thread is a basic unit of CPU utilization.

Multi threading is an execution model that allows a single process to have multiple code segments (i.e., threads) running concurrently within the “context” of that process.

* Ability of a process to manage its use by more than one user at a time

* Managing multiple requests by the same user without having to have multiple copies of the program.

![VLC Multi Threading image](https://www.geeksforgeeks.org/wp-content/uploads/vlc.jpg)
