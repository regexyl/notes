---
publish: "false"
topics: tech, rust
---
# Exploration

## Reading of [Rust data structures with circular references](https://eli.thegreenplace.net/2021/rust-data-structures-with-circular-references/ "Permalink to Rust data structures with circular references")

> Rust compiler should be able to calculate the size of a struct at compile-time, left and right typically use a heap-allocated Box.

- How is the compiler able to calculate the size of a struct at compile time? What if one of the struct's property values has `Vector`?
- Guessing from the article which says 'left and right typically use a heap-allocated `Box`', I'm guessing a `Vector` can't be used in a struct?

## Reading of The Rust Book Ch. 15 - Smart Pointers

Different libraries may implement their own smart pointers. Common smart pointers in the standard library include:

1. `Box<T>`: for allocating values on the heap #what -> does this mean that `Rc<T>` and `RefCell<T>` don't 
2. `Rc<T>`: a type that allows for multiple owners by enable *reference counting* #what
3. `RefCell<T>`, which allows access to `Ref<T>` and `RefMut<T>`: a type that enforces borrowing rules at runtime instead of compile time