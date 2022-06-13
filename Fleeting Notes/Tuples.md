202205290044
Status: #fleeting
Tags: [[Breaking down basics of Cairo language]]

# Tuples
```cairo
  local loc_tuple : (
        Location, Location, Location, Location, Location
    ) = (
        Location(row=0, col=2),
        Location(row=1, col=2),
        Location(row=1, col=3),
        Location(row=2, col=3),
        Location(row=3, col=3),
        )
```

- Ordered finite lists that can define any combination of valid types
- Can be accessed with zero-based index (ex. `loc_tuple[2]`)
- Allocates the number of cells defined by `SIZE` of each type in tuple


---
# References
https://www.cairo-lang.org/docs/hello_cairo/puzzle.html
