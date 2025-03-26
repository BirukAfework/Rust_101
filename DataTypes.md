# Rust Data Types: Scalars and Compounds

Rust is a statically typed language, which means all variables must have known types at compile time. The compiler can usually infer types, but you can also explicitly annotate them. Rust's type system is rich and ensures memory safety without garbage collection.

## Scalar Types (Single Values)

### 1. Integers

| Type     | Signed (i) | Unsigned (u) | Size       | Range (Signed)          | Range (Unsigned) |
|----------|-----------|-------------|------------|-------------------------|------------------|
| Integer  | i8        | u8          | 8-bit      | -128 to 127             | 0 to 255         |
|          | i16       | u16         | 16-bit     | -32,768 to 32,767       | 0 to 65,535      |
|          | i32       | u32         | 32-bit     | -2³¹ to 2³¹-1           | 0 to 2³²-1       |
|          | i64       | u64         | 64-bit     | -2⁶³ to 2⁶³-1           | 0 to 2⁶⁴-1       |
|          | i128      | u128        | 128-bit    | -2¹²⁷ to 2¹²⁷-1         | 0 to 2¹²⁸-1      |
|          | isize     | usize       | arch       | depends on architecture |                  |

- Default: `i32`
- `isize/usize`: Pointer-sized (32-bit on 32-bit systems, 64-bit on 64-bit systems)

```rust
let decimal = 98_222;       // 98,222
let hex = 0xff;             // 255
let octal = 0o77;           // 63
let binary = 0b1111_0000;   // 240
let byte = b'A';            // 65 (u8 only)
```

### 2. Floating-Point Numbers

| Type   | Size   | Precision          |
|--------|--------|--------------------|
| f32    | 32-bit | ~6-7 decimal digits|
| f64    | 64-bit | ~15-16 decimal digits|

- Default: `f64` (more precise and about the same speed as `f32` on modern CPUs)

```rust
let x = 2.0;          // f64
let y: f32 = 3.0;     // f32
let z = 1.0e10;       // Scientific notation
```

### 3. Booleans

- Size: 1 byte
- Values: `true` or `false`

```rust
let t = true;
let f: bool = false;  // Explicit type annotation
```

### 4. Characters

- Size: 4 bytes (Unicode scalar value)
- Single quotes (unlike string literals which use double quotes)

```rust
let c = 'z';
let z = 'ℤ';
let heart_eyed_cat = '😻';
```

## Compound Types (Multiple Values)

### 1. Tuples

- Fixed-length sequence of values with different types
- Parentheses `()`
- Access elements with `.` followed by index or destructuring

```rust
let tup: (i32, f64, u8) = (500, 6.4, 1);

// Destructuring
let (x, y, z) = tup;
println!("y is {}", y);  // 6.4

// Index access
let five_hundred = tup.0;
let six_point_four = tup.1;
let one = tup.2;
```

### 2. Arrays

- Fixed-length sequence of values with the same type
- Square brackets `[]`
- Stack-allocated
- Useful when you want data on stack rather than heap

```rust
let a = [1, 2, 3, 4, 5];
let months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];

// With type and size
let b: [i32; 5] = [1, 2, 3, 4, 5];

// Initialize all elements to same value
let c = [3; 5];  // [3, 3, 3, 3, 3]

// Access elements
let first = a[0];
let second = a[1];

// Runtime bounds checking
let index = 10;
// a[index];  // Panics at runtime if out of bounds
```

### Array vs. Vector

For dynamic collections, use `Vec<T>` (vector) from the standard library:

```rust
let v: Vec<i32> = vec![1, 2, 3];  // Heap-allocated, can grow/shrink
```

## Type Conversion

Rust requires explicit conversion between types:

```rust
let x: i32 = 5;
let y: u32 = x as u32;  // Explicit cast
```

## Summary Table

| Category   | Types                          | Description                          |
|------------|--------------------------------|--------------------------------------|
| **Scalar** | `i8`-`i128`, `u8`-`u128`      | Signed/unsigned integers             |
|            | `isize`, `usize`               | Pointer-sized integers               |
|            | `f32`, `f64`                   | Floating-point numbers               |
|            | `bool`                         | Boolean (`true`/`false`)             |
|            | `char`                         | Unicode scalar value (4 bytes)       |
| **Compound** | `(T1, T2, ...)`               | Tuple (fixed-size, heterogeneous)    |
|            | `[T; N]`                       | Array (fixed-size, homogeneous)      |

Rust's type system helps prevent bugs by catching type mismatches at compile time while providing flexibility through type inference. The compiler's strict checks ensure memory safety without runtime overhead.
