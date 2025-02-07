# Rust Undefined Behavior Example

This repository demonstrates a common source of undefined behavior in Rust: modifying a vector's contents through a raw pointer after the vector has been reallocated.  This can lead to crashes, data corruption, or other unpredictable behavior.

The `bug.rs` file contains the buggy code. The `bugSolution.rs` demonstrates a safe and correct alternative.

**Key Concepts**
* **Raw Pointers:** Using raw pointers (`*mut T`) bypasses Rust's memory safety mechanisms and requires careful handling.
* **Vector Reallocation:** When a vector's capacity is exceeded, it will be reallocated to a new memory location.
* **Memory Safety:**  Rust's ownership and borrowing system is designed to prevent memory safety issues, and violating these rules can lead to bugs.

**How to Reproduce**
1. Clone this repository.
2. Run the buggy code using `cargo run --bin bug`. You might get a segfault or see incorrect output depending on the compiler and runtime environment.