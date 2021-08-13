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

## Appendix
- [Operators](https://doc.rust-lang.org/book/appendix-02-operators.html)

