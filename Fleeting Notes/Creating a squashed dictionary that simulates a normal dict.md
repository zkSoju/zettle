202205291355
Status: #fleeting
Tags: #cairolang

# Creating a squashed dictionary that simulates a normal dict
- Necessity for a data type with read-write access like a dictionary or a map, but [[Cairo memory is immutable]]
	- `squash_dict` library that can assist us in simulating that behavior

```cairo
struct DictAccess:
	member key: felt
	member prev_value: felt
	member new_value: felt
end
```

- `squash_dict` is constructed of a list of `DictAccess` in order to simulate the same behavior as a read-write dict
	- Function verifies that every write makes sense
	- Returns **squashed dict** where
		- Squashed keys are sorted
		- Each key appears once
		- `prev_val` refers to first time key appeared and `new_value` refers to last time
	- The above properties make `squashed_dict` appear as a normal dict
	- Example
	- ![[Pasted image 20220529140756.png|200]]
	- Verification process
		-  If prev in the second occurence of key 7 did not equal new in the first occurence then squash dict would fail
	- Return value
	- ![[Pasted image 20220529141127.png|200]]
 
 






---
# References

