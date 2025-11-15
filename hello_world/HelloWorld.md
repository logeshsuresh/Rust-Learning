# Anatomy of a Rust Program

Let's review in detail the classic **Hello, world!** program in Rust.

```rust
fn main() {
    println!("Hello, world!");
}
```

## `fn main()`

* These lines define a **function** in Rust.
* `main` is special: it is **the entry point** of every Rust executable.
* It takes **no parameters** and returns **nothing** by default.

If the function had parameters, they would go inside the parentheses `()`. The body of the function is enclosed in curly braces `{}`, which Rust **always** requires for function bodies.

### Style Note

It is idiomatic Rust to place the opening `{` on the **same line** as the function declaration, with **one space** between them:

```rust
fn main() {
}
```

---

## `println!`

`println!` calls a **Rust macro**.

* You can identify macros by the **exclamation mark** (`!`).
* If this were a normal function call, it would appear as `println()` instead of `println!()`.

Macros in Rust allow metaprogramming—expanding into code before compilation.

---

# Compiling and Running Are Separate Steps

To compile a program manually:

```sh
rustc main.rs
```

Running this command produces:

* The source file: `main.rs`
* The compiled binary: `main`

Rust is an **ahead-of-time compiled language**, meaning:

> You can compile a Rust program and give the executable to someone else—even if they don't have Rust installed.

---

# Hello, Cargo!

**Cargo** is Rust's:

* Build system
* Package manager
* Dependency manager

Cargo is the standard tool used by nearly all Rust developers because it automates:

* Building your code
* Fetching libraries (dependencies)
* Compiling dependencies

Even though simple programs have no dependencies, Cargo gives you a consistent project structure.

A typical Cargo project contains:

```
Cargo.toml
src/
  main.rs
```

### Cargo.toml

This file uses **TOML** (Tom's Obvious, Minimal Language), a clean and minimal configuration format.

Example:

```toml
[package]
name = "hello"
version = "0.1.0"
edition = "2021"
```

---

# Useful Cargo Commands

## 1. Build the Project

```sh
cargo build
```

This compiles your Rust project and outputs the binary inside `target/debug/`.

---

## 2. Run the Project

```sh
cargo run
```

Builds (if needed) and runs the binary in a single command.

---

## 3. Check for Errors Without Building

```sh
cargo check
```

`cargo check` analyzes your code and validates types and borrow rules **without producing a binary**.

This is much faster and is commonly used during development.

---

## 4. Build for Release

```sh
cargo build --release
```

This compiles the project with **optimizations enabled**, producing a faster binary in:

```
target/release/
```

Use this for production builds.




