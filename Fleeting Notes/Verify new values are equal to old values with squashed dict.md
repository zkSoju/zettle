202205291445
Status: #fleeting
Tags: #cairolang 

# Verify new values are equal to old values with squashed dict

- We can verify that new positions are the correct ones by ****appending the solved configuration to entires from [[Recursively constructing dictionary entries]] and squashing it (which verifies the squash property)
- We can construct all 15 tiles by recursively creating entries as `(key=1,prev_value=0,next_value=0) etc.`
- This leverages the property from [[Creating a squashed dictionary that simulates a normal dict]] previous value of new item equals new value of old item
- 





---
# References
https://www.cairo-lang.org/docs/hello_cairo/dict.html
