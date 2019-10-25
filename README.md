<p align="center">
  <img width="150" height="150" src="https://www.rust-lang.org/static/images/rust-logo-blk.svg">
</p>

# rust examples/tutorials

## more information can be found at [rust](https://www.rust-lang.org) website.

### I will add tons of examples that progressively get more complicated. I will also store examples of features of the standard library in these examples. If you see any issues with anything please make a pull request.

### each example will be seperated by a line seperator like below:

---

### table of contents

- [prerequisites](#prerequisites)
- [upgrading rust](#upgrading-rust)
- [cargo](#cargo)
- [hello world](#hello-world)
- [cargo new](#cargo-new)
- [cargo build](#cargo-build)
- [cargo run](#cargo-run)
- [cargo check](#cargo-check)
- [cargo build for release](#cargo-build-for-release)

---

### prerequisites

The first thing you need to do is install rust. To do this rust includes a shell script to automatically install rust on linux/mac machines:

```
curl https://sh.rustup.rs -sSf | sh
```

If you need on windows please refer to the installation instructions [here.](https://www.rust-lang.org/tools/install)
Once you have the install complete you should be able to check the version you are running:

```
rustc -V
```

output:

```
rustc 1.38.0 (625451e37 2019-09-23)
```

---

### cargo
cargo is the package manager that comes with rust.  You will want to make sure you also have this installed.  It comes with the default instllation method of rust but to check what version of cargo you have by running:
```
cargo -V
```

output:
```
cargo 1.38.0 (23ef9a4ef 2019-08-20)
```

---

### upgrading rust

the `rustup` tool will be able to peform a bunch of tasks. Once of them is upgrading your current rust version:

```
rustup update
```

---

### hello world
This will show you how to create your first program that says hello world.  First create a directory and create a file `main.rs`. Add the following text:

```
fn main() {
    println!("Hello World!");
}
```

Now you want to compile your rust program:

```
rustc main.rs
```

if you see no output the compile was successful and you should now have a binary for your program called `main` or `main.exe` on windows.  You can now run your hello world program by doing:

```
./main
```

output:

```
hello world!
```

---

### cargo new
cargo can also help with boilerplate setup once you are ready for new projects:

```
cargo new hello_world
```

output:
```
Created binary (application) `hello_world` package
```

What did this do?  It created a new project called hello_world.  It also started a new git project within this directory.  Once in the directory you will see `Cargo.toml` and a `src` directory.  Inside this `Cargo.toml` file you will see the following info:

```
[package]                                                                                                                                                   
name = "hello_world"
version = "0.1.0"
authors = ["Dan Sheffner <Dan@Sheffner.com>"]
edition = "2018"

# See more keys and their definitions at https://doc.rust-lang.org/cargo/reference/manifest.html

[dependencies]
```

This information came from git settings if you have configured git.  This is behind the scope of this setup but when first setting up git you would do:
```
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

These settings are then configured usually in `~/.gitconfig` 

---

### cargo build
Now lets compile our new package with `cargo`

```
cargo build
```

Your output my be sligthly different based on where you are running this:

```
Compiling hello_world v0.1.0 (/Users/username/git/rustcode/hello_world)
Finished dev [unoptimized + debuginfo] target(s) in 1.85s   
```

This will produce a binary now in `target/debug/hello_world`

--- 

### cargo run

You can run this program by doing:
```
cargo run
```

output:
```
    Finished dev [unoptimized + debuginfo] target(s) in 0.00s
     Running `target/debug/hello_world`
Hello, world!
```

`cargo run` is smart enough to see if your code changed and re-compile it for you.  Try changing the print statement to something else:

```
fn main() {
    println!("Hello from our rust program!");
}

```

Now when you do cargo run you will see it re-compile it for you:
```
cargo run
```

output:

```
   Compiling hello_world v0.1.0 (/Users/user/git/rustcode/hello_world)
    Finished dev [unoptimized + debuginfo] target(s) in 0.19s
     Running `target/debug/hello_world`
Hello from our rust program!
```

---

### cargo check
cargo check will check your source code and make sure it compiles but won't actually create a binary.  The reason for this is because its allot faster then creating a binary.  Its a good way to check your source code without incuring the time it takes to make the binary.

```
cargo check
```

output:

```
    Checking hello_world v0.1.0 (/Users/user/git/rustcode/hello_world)
    Finished dev [unoptimized + debuginfo] target(s) in 0.09s 
```

```
cargo build
```

output:

```
   Compiling hello_world v0.1.0 (/Users/user/git/rustcode/hello_world)
    Finished dev [unoptimized + debuginfo] target(s) in 0.42s
```

You can see the difference in peformance just with a hello world project.  As your project grows `cargo check` will become more useful. 


### cargo build for release
When you run `cargo build` you see that it says `unoptimized + debuginfo` This means its creating a binary that is not optimized for production and has debug symbols in it for debugging purposes.  Once you are ready for production you will want to pass `--release` to `cargo build`  This is another speed optimization as well.  It will take longer to compile but your rust program will run faster.  This will make a binary in directory `target/release/` vs `target/debug/`

```
cargo build --release
```

output:

```
Compiling hello_world v0.1.0 (/Users/user/git/rustcode/hello_world)
    Finished release [optimized] target(s) in 0.21s
```
