# Atomic64 - 64 bits integers with atomic operations for Rust

## Usage

To use `atomic64`, first add this to your `Cargo.toml`:

```toml
[dependencies.atomic64]
git = "https://github.com/obourgain/rust-atomic64"
```

`atomic64` will soon be published on [Crates.io](https://crates.io/crates/atomic64).

Then, add this to your crate root:

```rust
extern crate atomic64;
```

Due to the use of `const fn` to allow the creation of `AtomicI64::new` and `AtomicU64::new` in constant context, atomic64 is only usable on nightly rust. Maybe conditional compilation could solve the issue ?

Includes code derived from [Syncbox](https://crates.io/crates/syncbox).
