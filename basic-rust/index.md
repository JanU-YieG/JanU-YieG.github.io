# Basic Rust


<!--more-->
## Variables && Constant
- Immutable (default)
    ```
    let x = 7;
    ```
- Mutable
    ```
    let mut x = 8;
    ```
- Shadowing
    ```
    let spaces = "    ";
    let spaces = spaces.len();
    ```
- Constant
    ```
    const MAX_POINTS: u32 = 100_000;
    ```

## Original Data Types
- Scalar Types
    - Integer Types
        - `i8,u8,i16,u16,i32(default),u32,i64,u64,i128,u128,isize,usize`
        - liteger:`74u8,89_333,0xff,0o77,0b1111_0000,b'A'`
    - Floating-Point Types
        - `f32,f64(default)`
    - Boolean Type
        - `bool`
        - values:`true`,`false`
        - one byte in size
    - Character Type
        - `char`
        - '😻'
        - four bytes in size
- Compound Types
    - Tuple Type
        - (, , , , ),tup.1
        - different type elements
        - fixed length
    - Array Type
        - [, , , , ],[i32;5]=[ , , , , ],[3;5];a[0]
        - same type elements
        - fixed length
        - data allocated on the stack

## Functions
- fn function_name(params_name: type) -> return_type{}
- must declaring the type of each parameter
- Rust is an expression-based language.
- `Statements` are instructions that perform some action and do not return a value.
- `Expressions` evaluate to a resulting value.do not include ending semicolons.
- The return value of the function is synonymous with the value of the final expression in the block of the body of a function.Also you can return early by using `return`.

## Control Flow
- `if` `else`,`else if`,`while`,`loop`,`for`
- `arms`
- break ...;

## Ownership
- Both the stack and the heap are parts of memory that are available to your code to use at runtime,but they are structured in different ways.
- `Stack`:adding data is called `pushing onto the stack`,and removing data is called `popping off the stack`.known,fixed size.
- `Heap`:allocating.unknown.pointer.
- `pointer` is a known,fixed size.store the pointer on the stack ,but when you want the actual data,you must follow the pointer.
- Ownership Rules
    - Each value in Rust has a variable that's called its owner.
    - There can only be one owner at a time.
    - When the owner goes out of scope, the value will be dropped.
- `move`
- `clone`
- stack-only data:copy
- `Copy` trait
- `Drop` trait
- `References``&`
    - never have ownership---function parameters---->`Borrowing`
    - In a particular scope , you can have either one mutable reference or any number of immutable references.-->solved data race-->curly brackets can create a new scope.
    - References must always be valid.
    - A reference's scope starts from where it is introduced and continues through the last time that reference is used.
- `Dereferencing``*`
- `refer to` and `onw`
- `Slice Type`
    - have no ownership
    - Slices let you reference a contiguous sequence of elements in a `collection` rather than the whole collection.
    - The slice data structure stores the starting position and the length of the slice,which correspondes to ending_index minus starting_index.

## Using Structs to Structure Related Data
- create custom types.
- `Shorthand`
- `tuple structs`--->tuple struct instances behave like tuples.(destructure,`.`)
- Each struct you define is its own type.
- `unit-like structs`--->behave similary to `()`.
- `Lifetimes` specify reference in struct.
- `derive` annotation can add useful behavior to our custom types.
- `method`
    - defined within the context of a struct(or an enum or a trait object),and their first parameter is always `self`.
    - `automatic referencing and dereferencing`
    - `Associated functions`:Don't take `self` as a parameter.Calling associated function use `::`.This function is namespaced by the struct.
    - Multiple `impl` Blocks

## Enums
- Enums can create custom types.
- Each variant can have diferent types and amounts of associated data.
- you can put any kind of data inside an enum variant.
- we can also define methods on enums like struct.

## Option enum
- enum defined by the standard library.
- a value could be something or it could be nothing.
- included in the prelude:you don't need to bring it into scope explicitly,you can use `Some` and `None` derectly without the `::` prefix.
- `Option<T>` enum is still just a regular enum,and `Some<T>` and `None` are still variants of type `Option<T>`
- `<T>` is a generic type parameter.
- useing `None` ,you need to tell Rust what type of `Option<T>` we have.

## Match
- allowed you to compare a value against a series of paterns and then execute code based on which pattern matches.
- Patterns:literal values,variable names,wildcards,many other things.
- `if` the expression needs to return a Boolean value,but the `Match` can be any type.
- each arm is an expression,and the resulting value of the expression in the matching arm is the value that gets returned for the entire `match` expression.
- If you want to run multiple lines of code in a match arm ,you can use curly brackets.
- Another useful feature of match arms is that they can bind to the parts of the values that match the pattern. 
- Matches are exhaustive.(we must exhaust every last possibility in order for the code to be valid).
- `if let`:If we care about only one of the cases and ignore the rest,we can use `if let` to avoid the match is wordy.You can use `else` after `if let`.

## The _ placeholder
1.match:the pattern `_` will match any value.

## Managing Growing Projects with Packages,Creates,and Modules  (Module system)
- Cargo provides Workspaces for very large projects of a set of interrelated packages that evolve together and contain multiple binary crates and optionally one library crate.
- You can not have two items with the same name in the same scope;tools are available to resolve name conflicts.
- Packages: A Cargo feature that lets you build, test, and share crates
- Crates: A tree of modules that produces a library or executable
- Modules and use: Let you control the organization, scope, and privacy of paths
- Paths: A way of naming an item, such as a struct, function, or module
- keywords:`pub`,`as`,`use`,`mod`,`crate`,`self`,`super`,`*`
- Mudules are not useful onlu for organizing your code.They alse define Rust's `privacy boundary`.
- Items in a parent module can’t use the private items inside child modules, but items in child modules can use the items in their ancestor modules.
- Rust chose to have the module system function this way so that hiding inner implementation details is the default. 
- `pub` to struct and enum:we use pub before a struct definition, we make the struct public, but the struct’s fields will still be private. We can make each field public or not on a case-by-case basis.In contrast, if we make an enum public, all of its variants are then public.
- `pub use`:Re-exporting
- `std` is also a crate that's external to our package,but we do not need to change `Cargo.toml` to include `std`,because the standard library is shipped with the Rust language.However,we do need to refer to refer to it with `use` to bring items from there into our package's scope.
- nested path: `use std::{cmp::Ordering,io}` `use std::io::{self,Write}`
- `*` the Glob operator:`use std::collections::*`
- The mod keyword declares modules, and Rust looks in a file with the same name as the module for the code that goes into that module.
- Module code is private by default, but you can make definitions public by
adding the pub keyword.

## Common Collections
- Rust's standard library includes a number of very useful data structures called `collections`.
- The data these collections point to is stored on the heap.
- A vector allows you to store a variable number of values next to each other.
- A string is a collection of characters. We’ve mentioned the String type previously, but in this chapter we’ll talk about it in depth.
- A hash map allows you to associate a value with a particular key. It’s a particular implementation of the more general data structure called a map.

## Vec<T>
-  Vectors allow you to store more than one value in a single data structure that puts all the values next to each other in memory.
- Vectors can only store values of the same type.
- When we need to store elements of a different type in a vector ,we can define and use an enum!
## String
- Strings are implemented as a collection of bytes.
- every collection type has operetions:creating,updating,reading.
- Rust has only one string type in the core language,which is the string slice `str` that is usually seen in its borrowed for `&str`.
- The `String` type, which is provide by Rust's standard library rather than coded into the code language,is a growable,mutable,owned,UTF-8 encoded string type.
- strings are UTF-8 encoded.---->can not use index get char in a string.
- `+`:fn add(self,s:&str)->String{}
- format!:It does not take ownership of any of its parameters.
- you can use `string slice` to index a range getting a `string slice`.---->bytes.--not the best way.
- grapheme clusters:you can use `chars` methond,if you need to perform operations on individual Unicode scalar values.  `bytes` method:returns each raw byte, which might be appropriate for your domain.  But be sure to remember that valid Unicode scalar values may be made up of more than 1 byte.
## Hash Map
- all of the keys must have the same type, and all of the values must have the same type.
- A hasher is a type that implements the `BuildHasher` trait.

## Appendix
- [Operators](https://doc.rust-lang.org/book/appendix-02-operators.html)
- [Trait for custom types](https://doc.rust-lang.org/book/appendix-03-derivable-traits.html)
- [crates.io]*(https://crates.io/)

