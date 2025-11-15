# Anatomy of a Rust Program

Let's review in detail about the Hello, world! program.

```
fn main() {

}
```

These lines define a function in Rust. The main function is special: it is always the first code that runs in every executable Rust program.
The first line declares a function named `main` that has no parameters and returns nothing. 
If there were parameters, they would go inside the parantheses, (). Also, note that the function body is wrapped in curly brackets, {}. 
Rust requires thses around all function bodies. It's good style to plce the opening curly bracket on the same line as the function declaration, adding one space in between. 
The println! calls a Rust macro. If it aclled a function instead, it would be entered as println (without the !). 

# Compiling and Running Are Separate Steps

`rustc main.rs` 

On executing the above command, you can see main and main.rs. 
Rust is an ahead-of-time compiled language, meaning you can compule a program and give the executable to someone else and they can run it without even Rust being installed. 

# Hello, Cargo!

Cargo is Rust's build system and package manager. Most Rustaceans use this tool to mange their Rust projects because Cargo handles a lot of task for you, such as building your code, downloading the libraries your code depends on, and building those libraries. 

The simplest Rust programs, like the one written so far don't have any dependencies. 

Cargo.toml -> This file is in the TOML (Tom's Obvious, Minimal Language) format

