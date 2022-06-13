202205290208
Status: #fleeting
Tags: #cairolang 

# Retrieving address of local variable
```cairo
from starkware.cairo.common.registers import get_fp_and_pc

let (__fp__, _) = get_fp_and_pc()
```
- For technical reasons Cairo needs to be told value of frame pointer register in order to get the address of a local variable (`&loc_tuple`)
- Cairo looks for the value `__fp__` when it needs to know value of `fp`
- 









---
# References

