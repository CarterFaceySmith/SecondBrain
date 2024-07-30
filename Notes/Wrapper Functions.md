A wrapper func. is a function in software whose main purpose is to call a second function or system call with no additional computation, ie wrapping the second call.

### But why?

We can do a number of things with wrapper functions:
1. extend the functionality of the secondary function without modifying it;
2. hide 'unpretty' stuff from the original func.;
3. run multiple funcs as a routine, ie execute this func then this func then this func and give me the results;
4. you may not have access to the inner function's code but may need to augment it, a wrapper can do this;
5. and more!


See also:
- [[Functions]]