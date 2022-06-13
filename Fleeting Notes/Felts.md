202205282008
Status: #fleeting
Tags: #cairolang 

# Felts
- Known as a field element 
- Integer in range -P/2 < x < P/2 where P is a large prime number (current 256 bits)
- Add, subtract, or multiply can cause overflow
	- Cairo adds/subtracts the appropriate multiple of P to bring reuslt back into range
- Key difference between field elements and integers is **division**
	- Felt division is different because in cases like `7/3` where the numerator is not a multiple of the denominator, you will not get the value you expect (`7/3 = 2`)
		- When we divide `7/3` in Cairo, we get a value `2.3333` that is outside of the range of integers causing an overflow to occur
			- Uses the mathematicalfact that there will always be a value `x` satisfying `denominator * x = numerator`








---
# References

