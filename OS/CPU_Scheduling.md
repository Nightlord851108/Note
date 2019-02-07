# CPU Scheduling
* Arrival Time:       Time at which the process arrives in the ready queue.

* Completion Time:    Time at which process completes its execution.

* Burst Time:         Time required by a process for CPU execution.

* Turn Around Time:   Time Difference between completion time and arrival time.
```
    Turn Around Time = Completion Time - Arrival Time
```

* Waiting Time(W.T): Time Difference between turn around time and burst time.
```
    Waiting Time = Turn Around Time - Burst Time
```

## Tips with Scheduling Algorithms
* FCFS can cause long waiting time when the first job takes too much CPU time.

* Both SJF and Shortest Remaining Time Scheduling might cause starvation when there's a long job in queue and shorter jobs keep coming.

* If time quantum of Round Robin Scheduling is very large, it behaves same as FCFS scheduling.

* SJF is optimal in terms of average waiting time. The problem is how to know/predict time of next job.

## Different Scheduling Algorithms
1. First Come First Serve (FCFS): Simplest algorithm. According to the arrival time of processes.

2. Shortest Job First(SJF): Also called Shortest Job Next(SJN). Process which have shortest burst time are scheduled first. This might cause starving.

3. Longest Job First(LJF): Similar to SJF, but the longer burst time, the higher the priority of process. This is non-preemptive in nature i.e.,when any process starts executing, can’t be interrupted before complete execution.

4. Shortest Remaining Time First(SRTF): Preemptive mode of SJF. According to the remaining time of the processes.

5. Longest Remaining Time First(LRTF): Preemptive mode of LJF.

6. Round Robin Scheduling: Each process is assigned a fixed time in cyclic way.

7. Priority Based Scheduling(Non-preemptive): Processes are scheduled according to their priorities, highest priority first. If exist two processes with same priority, then schedule according to arrival time.

8. Highest Response Ratio Next(HRRN): The process with the highest response ratio is scheduled. It could avoid starvation.
```
    Response Ratio = (Waiting Time + Burst time) / Burst time
                   = 1 + (Waiting Time / Burst time)
```

9. Multi level Queue Scheduling: The processes are placed in diffrent queues according to their priority. Generally, high priority processes are place in top level. Only after the completion of the processes from top level, the lower level processes are scheduled.

10. Multi level Feedback Queue Scheduling: It allows the process to move in between queues. The idea is to separate processes according to the characteristics of their CPU bursts. If a process uses too much CPU time, it is moved to a lower-priority queue.
