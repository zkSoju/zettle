202205282229
Status: #fleeting
Tags: #cairolang 

# Local variables

```cairo
alloc_locals
local row_diff = loc0.row - loc1.row
```

- Similar to [[Temporary variables]] except scope is restricted
	- Can only access them starting from definition to end of the function
- `alloc_locals` is used as part of Cairo `local` mechanism, should be first statement in function using local variables
- Why doesn't compiler automatically add the line if I'm using local variables?
	- Explicit language, code usually must instruct
	- Some cases it's possible to avoid statement with registers or place elsewhere in the code







---
# References

