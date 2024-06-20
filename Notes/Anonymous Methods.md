A feature of [[Delegates]] that can speed up coding.

There are two syntax for anonymous methods:
- One using the delegate-keyword
- Another one using the Lambda-Operator (‘$=>$‘)

Can only be called once.

Example:
```
PrintHandler print = delegate(int value) { 
	Console.WriteLine("First Anonymous call, value: {0}", value);
};
```

## Creation via Lambda Expressions 

Syntax: Lambda operator ($=>$), separates input (left) from the output (right)
Specification of datatypes not needed! Figured out by the compiler...

Two types of Lambda expressions:
- Lambda expression
- Lambda statement

Use {} for multi-line definitions.
() => for no parameters!


See also:
- 