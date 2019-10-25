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
