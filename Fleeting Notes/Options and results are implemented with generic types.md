202207191303
Status: 
Tags: #rust

# Options and results are implemented with generic types

```rust
enum Option<T> {
	Some(T),
	None,
}

enum Result<T,E> {
	Ok(T),
	Err(E),
}
```







---
# References

