202205282214
Status: #fleeting
Tags: [[Temporary variables]]

# Temporary variables

- `tempvar` is the definition of a temporary variable
	- "variable" may be deceiving because memory is immutable in Cairo
	- Scope of a temporary variable is restricted
		- Variable may be revoked do to jumps or function calls
	- Use with caution (typically in simple functions with no jumps and calls to other functions)







---
# References
[[Cairo memory is immutable]]
