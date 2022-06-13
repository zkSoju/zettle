202205291435
Status: #fleeting
Tags: #cairolang 

# Recursively constructing dictionary entries
```
func build_dict(
    loc_list : Location*,
    tile_list : felt*,
    n_steps,
    dict : DictAccess*,
) -> (dict : DictAccess*):
    if n_steps == 0:
        # When there are no more steps, just return the dict
        # pointer.
        return (dict=dict)
    end

    # Set the key to the current tile being moved.
    assert dict.key = [tile_list]

    # Its previous location should be where the empty tile is
    # going to be.
    let next_loc : Location* = loc_list + Location.SIZE
    assert dict.prev_value = 4 * next_loc.row + next_loc.col

    # Its next location should be where the empty tile is
    # now.
    assert dict.new_value = 4 * loc_list.row + loc_list.col

    # Call build_dict recursively.
    return build_dict(
        loc_list=next_loc,
        tile_list=tile_list + 1,
        n_steps=n_steps - 1,
        dict=dict + DictAccess.SIZE,
    )
end
```

- Function receives a 
	- pointer to a list of structs
	- pointer to a list of felts
	- number of steps in solution
	- pointer called `dict`
- Writes entries starting from dict 
- Returns pointer to next address to write to
- Common practice in Cairo to get a pointer, read/write from that pointer, and return the pointer to the next entry







---
# References
[[Creating a squashed dictionary that simulates a normal dict]]