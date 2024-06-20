An [[Interrupt]] that diverts program flow to force an [[Operating Systems]] to attend to some task.

In [[C++]], various versions of this signal are offered which can be caught and processed in runtime.

## C++ Signals

| Signals                | Operations                                                                      |
| ---------------------- | ------------------------------------------------------------------------------- |
| GINT                   | Produces a receipt for an active signal                                         |
| GTERM                  | Sends a termination request to the program                                      |
| GBUS                   | Bus error which indicates access to an invalid address                          |
| GILL                   | Detects an illegal command                                                      |
| GALRM                  | This is used by the alarm() function and indicates the expiration of the timer. |
| GABRT                  | Termination of a program, abnormally                                            |
| GSTOP                  | The signal cannot be blocked, handled, and ignored and can stop a process       |
| GSEGV                  | Invalid access to storage                                                       |
| GFPE                   | Overflow operations or mathematically incorrect operations like divide by zero  |
| SIGUSR1<br><br>SIGSUR2 | User-Defined Signals                                                            |


See also:
- [[Kernel]]
- [Signals: I Spent 2 years to understand this part.](https://www.youtube.com/watch?v=d0gS5TXarXc)