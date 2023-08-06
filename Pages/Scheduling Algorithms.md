# Scheduling Algorithms

## Non-preemptive 

### First-Come, First-Served
x

### Shortest-Job-First
- Scheduling bby the next CPU burst of process, where the process with shortest time is selected

## Preemptive

### Shortest-remaining-time-first
x

### Priority Scheduling
- A priority number (int) is associated with each process, CPU is allocated to the process with the highest priority
- As time progresses we need to increase the priority of stored processes to prevent starvation (low priority processes never executing)

### Round Robin
- Each process gets a small unit of CPU time, after which the process is preempted and added to the end of the ready queue

