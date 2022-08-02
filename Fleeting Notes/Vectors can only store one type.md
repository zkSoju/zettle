202207182224
Status: 
Tags: #rust

# Vectors can only store one type
- Enums can only store one type but you can create an enum to create variants for multiple types of data

```rust
enum SpreadsheetCell {
	Int(i32),
	Float(f64),
	Text(String),
}

let row = vec![Spreadsheetcell::Int(3)]
```







---
# References

