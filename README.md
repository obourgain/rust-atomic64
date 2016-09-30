# Atomic64 - 64 bits integers with atomic operations for Rust


# Deprecated

Use the types that are now included as unstable feature in std/sync [AtomicU64](https://doc.rust-lang.org/std/sync/atomic/struct.AtomicI64.html) and [AtomicI64](https://doc.rust-lang.org/std/sync/atomic/struct.AtomicI64.html)

[![Build Status](https://travis-ci.org/obourgain/rust-atomic64.svg?branch=master)](https://travis-ci.org/obourgain/rust-atomic64)

## Usage

`atomic64` is on [Crates.io](https://crates.io/crates/atomic64).

To use `atomic64`, first add this to your `Cargo.toml`:

```toml
[dependencies]
atomic64 = "0.1.0"
```

Then, add this to your crate root:

```rust
extern crate atomic64;
```

You can now use AtomicI64 and AtomicU64.

## Note

Due to the use of `const fn` to allow the creation of `AtomicI64::new` and `AtomicU64::new` in constant context, atomic64 is only usable on nightly rust. Maybe conditional compilation could solve the issue ?

Includes code derived from [Syncbox](https://crates.io/crates/syncbox).

## Internals

On 64-bits platforms, atomic64 will internally use Rust's [AtomicIsize](https://doc.rust-lang.org/std/sync/atomic/struct.AtomicIsize.html) and [AtomicUsize](https://doc.rust-lang.org/std/sync/atomic/struct.AtomicUsize.html).

On 32-bits platforms, atomic64 will use an i64 or u64 wrapped by a [Mutex](https://doc.rust-lang.org/std/sync/struct.Mutex.html). The performance will be wildly different between 32 and 64 bits platforms, with 64 bits expected to be faster.
