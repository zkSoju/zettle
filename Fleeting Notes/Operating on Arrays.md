202205282047
Status: #fleeting
Tags: #cairolang 

# Operating on Arrays

- `from starkware.cairo.common.alloc import alloc`
	- Library used to allocate a new memory segment
	- Exact location of allocated memory is determined when program terminates allowing us to avoid specifying the size
```sol
func array_sum(arr, size) -> (sum):
    # ...
end

func main{output_ptr : felt*}():
    const ARRAY_SIZE = 3

    # Allocate an array.
    let (ptr) = alloc()

    # Populate some values in the array.
    assert [ptr] = 9
    assert [ptr + 1] = 16
    assert [ptr + 2] = 25

    # Call array_sum to compute the sum of the elements.
    let (sum) = array_sum(arr=ptr, size=ARRAY_SIZE)

    # Write the sum to the program output.
    serialize_word(sum)

    return ()
end
```
- Key takeways
	- Memory allocation - uses the `alloc()` library function to allocate a new memory segment
		- Doesn't specify size of allocation because exact location is determined when program terminates
	- Constants - constants defined in Cairo are defined with `cosnt CONST_NAME = <expr>` and must be a felt known at compile time






---
# References
https://www.cairo-lang.org/docs/hello_cairo/intro.html#product-exercise