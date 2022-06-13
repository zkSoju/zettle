202205282237
Status: #fleeting
Tags: #cairolang 

# References, temporary variables, and local variables
- Reference is defined using a `let` statement
	- ex. `let x = y * y * y`
	- Think of x as an alias to the expression, so by itself the above code will not cause computation to be performed
	- However a later instruction like `assert x * x = 1`
	- Scope for a reference is derived from scope of aliased expressions
	- **No memory cell is aallocated**
- [[Temporary variables]] and [[Local variables]] are special cases of referencces
	- Point to specific memory cell, storing result of computation
	- `tempvar x = y * y` **will** invoke computation
	- x will be an **alias to the memory cell not expression**
- Key takeaways
	- Temporary variables don't require prior allocation but scope is limited
	- Local variables are placed at beginning of function stack so prior allocation is required by `alloc_locals` 
		- Can be accessed throughout function
	- Store returns of functions to local variables to avoid variable being revoked
	- If you get an error for tempvar, you can try making it a local variable







---
# References

