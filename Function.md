
# Rust Functions: Definition, Parameters, and Return Values

Rust functions are defined using the `fn` keyword and provide a way to organize code into reusable blocks. Let's explore how to work with functions in Rust.

## Defining Functions

Basic function syntax:
```rust
fn function_name(parameters) -> return_type {
    // function body
    // optional return value
}
```

Example:
```rust
fn greet() {
    println!("Hello, world!");
}
```

## Function Parameters

Parameters are specified with their types (Rust requires explicit type annotations):

```rust
fn print_sum(a: i32, b: i32) {
    println!("Sum is: {}", a + b);
}
```

Calling functions with arguments:
```rust
print_sum(5, 10);  // Prints "Sum is: 15"
```

### Explicit Return
```rust
fn add(a: i32, b: i32) -> i32 {
    return a + b;
}
```

### Implicit Return (Expression Style)
```rust
fn add(a: i32, b: i32) -> i32 {
    a + b  // No semicolon means this is the return value
}
```

### Returning Unit Type

```rust
fn no_return() -> () {
    println!("This returns nothing");
}
// Equivalent to:
fn no_return() {
    println!("This also returns nothing");
}
```
