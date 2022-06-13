202205281841
Status: #fleeting
Tags: #cairolang 

# Breaking down basics of Cairo language
```cairo
func array_sum(arr: felt*, size) -> (sum):
	if size == 0:
        return (sum=0)
    end

    # size is not zero.
    let (sum_of_rest) = array_sum(arr=arr + 1, size=size - 1)
    return (sum=[arr] + sum_of_rest)
end
```

- Function breakdown
	- `felt*` is a pointer 
	- `arr` is an array of `size` element
	- `return (sum = 0)`  is not mandatory but it increases readability of the code
		- Parentheses are required
	- You cannot call functions as parts of other expressions like `foo(bar())`
	- `[]` deference operator allows us to access the value of memory at address `arr` 

## Low level language with syntactic sugar
- Allows for writing maintainable and efficient code
	- Disadvantage is that deep understanding is required to avoid common mistakes



## Assertions
- `assert <expr0> = <expr1>
	- Allows us to
		- Verify two values are the same
		- Assign value to memory cell
		- ex. `assert [ptr] = 0`
			- If `[ptr]` is set then it would act as a normal assertion
			- If `[ptr]` is not set then Cairo will set and assertion will pass

## Writing a main() function
```cairo
%builtins output

from starkware.cairo.common.serialize import serialize_word

func main{output_ptr: felt*}():
	serialize_word(1234)
	serialize_word(4321)
	return()
end
```

- Things to note
	- **Function main()** is the starting point of Cairo program
	- **Builtin directive and output builtin** defined by `%builtins output` tells Cairo to use output builtin
		- output builtin is the equivalent to printing to console `print()` in Python
			- Operates by converting the `main()` signature to `main{output_ptr: felt*}()`
				- Utilizes `{output_ptr: felt*}` as an implicit argument, which is used behind the scene to add the argument and return value
				- Argument indicates beginning of output and return value marks end (cell **after** last written cell)
			- Cairo does not offer special instructions for builtins, they are done by reading/writing values to memory 
			- [[Cairo memory is immutable]]
	- **Function serialize_word()**
		- Implicit argument `output_ptr` is used in first call to write `1234` and then returns `output_ptr + 1` which is then used in the second call
	- **import statements**

---
# References
https://www.cairo-lang.org/docs/hello_cairo/intro.html
