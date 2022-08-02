202207181209
Status: 
Tags: #rust

# Ownership rules in Rust

1. Each value in Rust has a variable that's called its owner
2. There can only be one owner at a time
3. When owner goes out of scope, value will be dropped


- Integers are copied
- Moving a variable invalidates the previous assignment
- Assigning a new variable to a string moves the old string
- Passing in a variable as paramter into a function moves the variable
- `&` references don't take ownership, they borrow
- References are immutable by default
	- Add `mut` to mutate
		- **You can only borrow once in a scope**
		- **You cannot borrow as immutable if already borrowed as mutable because underlying immutable reference isn't expected to change**



---
# References

