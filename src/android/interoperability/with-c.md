# Interoperability with C

Rust has full support for linking object files with a C calling convention.
Similarly, you can export Rust functions and call them from C.

You can do it by hand if you want:

```rust
unsafe extern "C" {
    safe fn abs(x: i32) -> i32;
}

fn main() {
    let x = -42;
    let abs_x = abs(x);
    println!("{x}, {abs_x}");
}
```

We already saw this in the
[Safe FFI Wrapper exercise](../../unsafe-rust/exercise.md).

> This assumes full knowledge of the target platform. Not recommended for
> production.

We will look at better options next.
