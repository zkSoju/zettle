202207181426
Status: 
Tags: #rust

# Rust module system

- `cargo new` creates a package which contains crates
- binary crates contain executable code
- library crates contain reusable code
- crates contain modules which allow you to scope code and maintain visibility
- bring parent module into scope instead of specific function so we can still indicate which module it came from and not local
- use keyword is used to bring code into scope in our own program and then mark as public so external code can use it
- we can declare modules in Rust with `mod` and we can declare contents in curly brackets or we use semi-colon and define contents in a separate file with the same name as the module
- child modules must live in a folder with the same name as the parent module






---
# References

