# Recursion

Calling a function within itself, come on chief remember this shit from like Y1?

Basically, tests the base case as an if statement, then enters recursive case in an else statement.

Factorial example:

$$
\begin{align}
4! = 4 * 3 * 2 * 1 = 24 \\
4! = 4 * 3! \\
... \\
0! = 1 \\
therefore \\
n! = n * (n - 1)!
\end{align}
$$

Surely you can see how breaking this down into factorialisations (is that a word?) is a perfect chance to use a recursive function.

### Example Recursive Function in [[C++]]
```c++
int factorial(int n)
{
	if(n==0){		//here's your base case you fuckin moron
		return 1;
	}
	
	else
	{
		return n * factorial(n-1);		//here's your recursive case
	}
}
```