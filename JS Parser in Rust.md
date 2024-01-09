
https://oxc-project.github.io/javascript-parser-in-rust/docs/overview

# Overview

- Look out for heap-allocated objects, e.g. `Vec`, `Box`, `String` - the more we allocate on the heap, the slower our program will be.
- Zero-cost abstraction: where higher-level abstractions can be used without incurring additional runtime cost compared to lower-level written code.

# Lexer

- Transforms source text into tokens
- #todo [Read]([#tc39-inclusion](https://matrix.to/#/#tc39-inclusion:matrix.org)) the ECMAScript Language Specification
- String Interning


# Parser

- Consumes the tokens - no need to worry about whitespaces and comments