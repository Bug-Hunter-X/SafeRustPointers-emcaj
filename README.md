# Unsafe Rust Pointer Manipulation Example

This repository demonstrates a potential pitfall when working with raw pointers in unsafe Rust code.  The example shows how directly modifying a vector's underlying memory through its raw pointer can lead to undefined behavior if not done meticulously.  The solution provides a safer, more idiomatic Rust approach.

## Bug

The `bug.rs` file contains code that uses `as_mut_ptr()` to obtain a raw mutable pointer to a vector's data. This pointer is then dereferenced and modified directly.  This method is unsafe and prone to errors if not handled precisely, possibly leading to memory corruption or panics.  The output might not reflect the expected changes due to Rust's ownership and borrowing system.

## Solution

The `bugSolution.rs` file presents a safer and more idiomatic way to modify vector elements. Instead of manipulating raw pointers, it uses standard vector methods, ensuring memory safety and preventing potential issues. This method avoids potential issues associated with violating Rust's memory management rules.