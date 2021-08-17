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
- 

## Appendix
- [Operators](https://doc.rust-lang.org/book/appendix-02-operators.html)
- [Trait for custom types](https://doc.rust-lang.org/book/appendix-03-derivable-traits.html)

