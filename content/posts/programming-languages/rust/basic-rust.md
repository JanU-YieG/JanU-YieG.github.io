---
title: "Basic Rust"
subtitle: "The basic of rust-lang"
date: 2021-08-12T11:53:01+08:00
lastmod: 2021-08-12T11:53:01+08:00
draft: false
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description: rust basic semantics
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: "https://s3.jpg.cm/2021/08/12/IXvMjt.jpg"
featuredImagePreview: "https://s3.jpg.cm/2021/08/12/IXvMjt.jpg"
weight: 1
resources:
- name: ""
  src: "xx.jpg"
keywords: ["Rust basic", "Rust"]
tags: ["Rust", "Rust Basix"]
categories: ["Rust"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: "Rust Basic"
---

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

## Appendix
- [Operators](https://doc.rust-lang.org/book/appendix-02-operators.html)
