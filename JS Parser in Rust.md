
https://oxc-project.github.io/javascript-parser-in-rust/docs/overview

# Overview
- Look out for heap-allocated ob%%  %%jects, e.g. `Vec`, `Box`, `String` - the more we allocate on the heap, the slower our program will be.
- Zero-cost abstraction: where higher-level abstractions can be used without incurring additional runtime cost compared to lower-level written code.

# Lexer

- Transforms source text into tokens
- #todo [Read]([#tc39-inclusion](https://matrix.to/#/#tc39-inclusion:matrix.org)) the ECMAScript Language Specification
- String Interning
	- The storing of a string in cache and assigning a unique ID to it. This allows for string comparisons to be O(1), and only allow one heap allocation per distinct ID or string.
	- One library is [string-cache](https://crates.io/crates/string_cache)

# Abstract Syntax Tree



# Parser

- Consumes the tokens - no need to worry about whitespaces and comments

# OXC-specific

