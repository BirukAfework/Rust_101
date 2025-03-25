

### **1. Immutable Variables (`let`)**
By default, variables are **immutable** (cannot be modified after assignment):
```rust
fn main() {
    let x = 5;    // Immutable variable
    println!("x = {}", x);

    // x = 6;     // ❌ Error: Cannot assign twice to immutable variable like in a python by default
}
```



### **2. Mutable Variables (`let mut`)**
To allow changes, declare the variable with `mut`:
```rust
fn main() {
    let mut y = 10;  // Mutable variable
    println!("Original y = {}", y);

    y = 15;          // ✅ Allowed (mutability) because of keyword mut in above variable y
    println!("Updated y = {}", y);
}
```



### **3. Shadowing (Re-declaring with `let`)**
You can **shadow** a variable by re-declaring it with `let`. This creates a new variable under the same name:
```rust
fn main() {
    let z = 5;
    println!("z = {}", z);  // 5

    let z = z + 1;          // Shadowing (new variable)
    println!("z = {}", z);  // 6

    let z = "now a string"; // Can even change type!
    println!("z = {}", z);  // "now a string"
}
```
- Shadowing is different from `mut` because it creates a **new binding** (allowing type changes).



### **4. Constants (`const`)**
Constants are **always immutable** and must have a compile-time known value:
```rust
const PI: f64 = 3.14159; // Must specify type (`f64` here)
fn main() {
    println!("PI = {}", PI);
}
```
- Naming convention: Uppercase with underscores (e.g., `MAX_POINTS`).


### **5. Static Variables (`static`)**
Global variables with a `'static` lifetime (rarely needed):
```rust
static APP_NAME: &str = "MyApp";
fn main() {
    println!("Welcome to {}", APP_NAME);
}
```
- Use sparingly (prefer passing variables as arguments).


### **Key Differences: `mut` vs. Shadowing**
| Feature          | `mut`                          | Shadowing (`let`)               |
|------------------|-------------------------------|---------------------------------|
| Mutability       | Same variable, can be changed | New variable (can change type)  |
| Memory           | Reuses memory                 | Allocates new memory            |
| Type Change      | ❌ No                         | ✅ Yes                          |



### **When to Use Which?**
1. **Immutable (`let`)**: Default choice (safe, functional style).
2. **Mutable (`let mut`)**: Needed for in-place updates (e.g., counters).
3. **Shadowing (`let`)**: Useful for transforming values without mutability.
4. **Constants (`const`)**: For compile-time known values (e.g., configs).



### **Example: Mutable Counter**
```rust
fn main() {
    let mut count = 0;
    count += 1;       // ✅ Works (mutability)
    println!("Count: {}", count);
}
```

### **Example: Shadowing with Type Change**
```rust
fn main() {
    let value = 42;
    let value = "forty-two"; // ✅ Changes type
    println!("value = {}", value);
}
```
