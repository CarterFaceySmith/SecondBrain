# Deadlocks

A *lock* occurs when multiple processes try to access the same resource at the same time.

One process loses and must wait for the other to finish.

A *deadlock* occurs when the waiting process is still holding on to another resource that the first needs before it can finish.

The best way to avoid this is to avoid having processes cross over in this way, therefore reducing the need to lock anything as much as possible.

## Handling Deadlocks

1. Prevention, see Mutex in [[Multiprogramming]]
2. Avoidance
3. Ignore the possibility and handle if arises


See also:
- [[Computer System Structure]]
- [[CPU Scheduling]]
- [[Multiprogramming]]