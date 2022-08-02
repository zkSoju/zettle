202207192255
Status: 
Tags: #rust

# Lifetime Elision rules in Rust
1. each parameter that is a reference gets its own lifetime parameter
2. if exactly one input lifetime parameter then that lifetime is assigned to all output lifetime parameters
3. if there are multiple input lifetime parameters, but one is `&self` or `&mut self` the lifetime is assigned to all output parameters (applies to methods)







---
# References

