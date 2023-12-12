---
publish: "false"
topics: tech, rust
---
# Exploration

## Reading of [Rust data structures with circular references](https://eli.thegreenplace.net/2021/rust-data-structures-with-circular-references/ "Permalink to Rust data structures with circular references")

> Rust compiler should be able to calculate the size of a struct at compile-time, left and right typically use a heap-allocated Box.

- How is the compiler able to calculate the size of a struct at compile time? What if one of the struct's property values has `Vector`?
- Guessing from the article which says 'left and right typically use a heap-allocated `Box`', I'm guessing a `Vector` can't be used in a struct?