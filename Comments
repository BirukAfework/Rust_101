# Rust Comments and Code Formatting


## Comments

### 1. Line Comments
```rust
// This is a single-line comment
let x = 5; // Comments can appear after code
```

### 2. Block Comments
```rust
/* This is a block comment
   that spans multiple lines */
let y = 10;
```

### 3. Documentation Comments (for items)

#### Outer Documentation (`///`)

```rust
/// Calculates the sum of two numbers
///
/// # Examples
/// ```
/// let result = add(2, 3);
/// assert_eq!(result, 5);
/// ```
fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

#### Inner Documentation (`//!`)

```rust
//! # My Crate
//! 
//! This is documentation about the entire crate
//! or current module
```

### 4. Documentation Attributes
Alternative syntax for documentation comments:

```rust
#[doc = "Calculates the difference between two numbers"]
fn subtract(a: i32, b: i32) -> i32 {
    a - b
}
```

## Code Formatting


### Installation
```bash
rustup component add rustfmt
```

### Usage
```bash
cargo fmt  # Formats all files in project
```

### Formatting Rules

1. **Indentation**: 4 spaces (not tabs)
2. **Line Length**: Default 100 chars (configurable)
3. **Braces**: Same-line for functions/control flow

```rust
// Properly formatted function
fn formatted_example(
    long_parameter_name: VeryLongTypeName,
    another_param: u32,
) -> Result<(), Error> {
    if condition {
        do_something();
    } else {
        do_something_else();
    }
}
```

### Common Formatting Patterns

#### Imports
```rust
use std::{
    collections::HashMap,
    fs::File,
    io::{Read, Write},
};
```

#### Long Function Calls
```rust
let result = some_really_long_function_name(
    argument1,
    argument2,
    argument3,
);
```

#### Match Expressions
```rust
match value {
    Some(x) if x > 10 => println!("Large number: {}", x),
    Some(_) => println!("Small number"),
    None => println!("No number"),
}
```

## Markdown in Documentation


```rust
/// # Header
/// 
/// - List item 1
/// - List item 2
/// 
/// **Bold text** and *italic text*
/// 
/// ```rust
/// // Code example
/// let example = 42;
/// ```
```

## Documentation Generation

Generate HTML documentation with:
```bash
cargo doc --open
```

## Special Documentation Sections

Common conventional sections in documentation:

```rust
/// # Panics
/// Explains when the function might panic
///
/// # Errors
/// Describes error conditions
///
/// # Safety
/// For unsafe functions, explains invariants
///
/// # Examples
/// Usage examples (tested by `cargo test`)
```

## Configuration

Add a `rustfmt.toml` to customize formatting:

```toml
# rustfmt.toml
max_width = 80
chain_width = 60
```
