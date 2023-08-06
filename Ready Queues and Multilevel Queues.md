# Ready Queues and Multilevel Queues

The ready queue as we already know, is normally implemented via a FIFO [[Stack]] (although this isn't the only way). 

## Multilevel Queues

This is where the ready queue is partitioned into seperate queues, for example:
- foreground queue (interactive)
- background queue (batch)

Scheduling is done *between both queues*.

Pretty wild shit huh?

A Multilevel-feedback-queue scheduler is defined by the following parameters:  
- number of queues  
- scheduling algorithms for each queue  
- method used to determine when to upgrade a process  
- method used to determine when to demote a process  
- method used to determine which queue a process will enter when that process needs service