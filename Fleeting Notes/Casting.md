202205290205
Status: #fleeting
Tags: #cairolang

# Casting

```cairo
# Since the tuple elements are next to each other we can use the
# address of loc_tuple as a pointer to the 5 locations.
verify_location_list(
    loc_list=cast(&loc_tuple, Location*), n_steps=4
)
```

- `loc_tuple` represents an address in memory, so to cast it to a pointer we need to use `cast`







---
# References

