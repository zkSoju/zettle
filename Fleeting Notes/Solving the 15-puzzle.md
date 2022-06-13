202205282155
Status: #fleeting
Tags: [[Breaking down basics of Cairo language]]

# Solving the 15-puzzle

![[Pasted image 20220528215604.png]]


## What we need to check
- Solution is represented as two lists
	- Positions of missing tiles `[(0, 2), (1, 2), (1, 3), (2, 3), (3, 3)]`
	- Tiles that are moved `[3, 7, 8, 12]`
	- Note that number of tiles moved is one less than positions of missing tiles
- We need to verify that
	- Locations in first list are valid
		- All numbers are between 0 and 3 and each consecutive pair represents adjacent locations [[Logical operations in Cairo]]
	- Numbers in second list correspond with first
		- We need to store and update locations of each tile [[Creating a squashed dictionary that simulates a normal dict]]
		- [[Recursively constructing dictionary entries]] which also ensures that corresponding values are valid
			-  `DictAccess` only stores one felt, so we need to use pointers to refer to a struct or convert the coordinates in Location to a single felt using `4 * row + col`
	- Final state is "solved"
		- 
 

---
# References

