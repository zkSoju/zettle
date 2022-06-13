202205291526
Status: #fleeting
Tags: #cairolang 

# Functions that need builtins require a pointer to the builtin
- Comparison in Cairo requires a built called `range-check` [[Logical operations in Cairo]]
- In order to specify that a function uses the builtin, we need to supply the pointer as an implicit argument
- Then return the pointer at the end (happens automatically when supplied as implicit argument)
	- Similar to they way we treat dict pointers
```cairo
func check_solution{output_ptr : felt*, range_check_ptr}(
    loc_list : Location*, tile_list : felt*, n_steps
):
  ...
  let (squashed_dict_end : DictAccess*) = squash_dict(
        dict_accesses=dict_start,
        dict_accesses_end=dict_end,
        squashed_dict=squashed_dict,
    )
```
- Until the call to `squash_dict` which takes in `range_check_ptr` as an implicit argument,  `range_check_ptr` refers to the argument of the function
- The function then rebinds the pointer to the return of `squash_dict` , pointer is changing but does not mean immutable [[Cairo memory is immutable]]



---
# References

