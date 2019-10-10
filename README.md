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
- [hello world](#hello-world)

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

### upgrading rust

the `rustup` tool will be able to peform a bunch of tasks. Once of them is upgrading your current rust version:

```
rustup update
```

### hello world

```
fn main() {
    println!("Hello World!");
}
```
