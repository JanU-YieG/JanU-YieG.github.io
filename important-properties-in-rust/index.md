# Important Properties in Rust


1.mutable & immutable & Shadowing & const

2.Statements & Expressions & Rust is expression-based language.

3.let ..if..

4.loop label & break/continue expression/loop label

5.for..in..

6.unit type(`()`)

7.Ownership
- Ownership Rules
    - Each value in Rust has a variable that's called its owner.
    - There can only be one owner at a time.
    - When the owner goes out of scope, the value will be dropped.
- move & clone & copy(Copy trait) & reference & slice
- 元组返回多个值,无值返回默认返回单元类型(`()`)
- 规避数据竞争：不可变引用`&` 和 可变引用`&mut`(在特定作用域中的特定数据只能有一个可变引用，且此时不能拥有不可变引用).在最后一行代码不使用的地方释放作用域。
- We call having references as function parameters borrowing
- 引用必须总是有效的。
- slice:&[starting_index..ending_index];`&str`--不可变引用

8.Struct
- `struct`
- field init shorthand
- struct update syntax(User{...., ..., ..user1})
- tuple structs:`struct Point(i32,i32,i32)`
- unit-like structs:`struct Unit`
- 在结构体中存储一个引用而不指定生命周期将是无效的。
- 方法：`impl`,`&self`,`self`,`&mut self`
- automatic referencing and dereferencing.
- associated functions：不以`self`作为参数的函数。`::`
- 每个结构体允许拥有多个`impl`块
- 匿名结构体：`{a:.., b:..,}`

9.Enums
- variants,
- `enum IpAddr{V4(u8,u8,u8,u8),V6(String)}`,variant:`IpAddr::V4(127,0,0,1)`属于IpAddr自定义数据类型。`enum Message{Quit,Move{x:i32,y:i32},Write(String),Color(i32,i32,i32)}`
- 方法：`impl`,`&self`,`self`,`&mut self`
- Option<T>:
    - `enum Option<T>{ Some(T),None }`
    - 只要一个值不是Option<T>，你就可以认定它的值不为空。

10.`match`控制流运算符
- exhaustive
- `_`匹配所有的值
- `if let`(..`else`)只匹配一个模式的值而忽略其他模式的情况,使用`=`分割一个模式和一个表达式。

11.The mudules system
- packages & crates
    - 一个包(package)中至多只能包含一个库crate（library crate）；包中可以包含任意多个二进制crate（binary crate）；包中至少包含一个crate,无论是库的还是二进制的。
    - `cargo new binary-crate-package`===>`src/main.rs`-->crate root & `cargo new --lib library-crate-package`===>`src/lib.rs`-->crate root.
- modules
    - 将一个crate中的代码进行分组。
    - 控制项的`私有性`即可以被外部代码使用（public），还是内部实现的不能被外部代码使用（private）。
    - Rust 中默认所有项（函数、方法、结构体、枚举、模块和常量）都是私有的。父模块中的项不能使用子模块中的私有项，但是子模块中的项可以使用他们父模块中的项。
    - `pub`:使子模块的内部部分暴露给上级模块。
    - `siblings`,`child`,`parent`;Notice that the entire module tree is rooted under the implicit module named `crate`.
    - 如果我们在一个结构体定义的前面使用了 pub ，这个结构体会变成公有的，但是这个结构体的字段仍然是私有的。字段共有需要字段前加`pub`.
    - 如果我们将枚举设为公有，则它的所有成员都将变为公有。
    - `use` Bringing Paths into Scope---bring a name into scope.---the name available in the new scope is private.---->`pub use`re-exporting---This technique is called re-exporting because we’re bringing an item into scope but also making that item available for others to bring into their scope.;;;`as`Providing New Names.
    - `use std::io::{self,Write};`.glob运算符：`use std::collections::*;`
    - `mod` 关键字声明了模块，Rust 会在与模块同名的文件中查找模块的代码。
    - `pub`,`mod`,`super`,`use`,`pub use`,`as`
- paths
    - absolute path:`crate::..::..`;relative path:`self/super::..::..`
    -  `"src/front_of_house.rs" or "src/front_of_house/mod.rs"` & `"src/front_of_house/hosting.rs" or "src/front_of_house/hosting/mod.rs"`

12.Collections(数据结构)
- The data these collections point to is stored on the heap, which means the amount of data does not need to be known at compile time and can grow or shrink as the program runs.
- Vector(Vec<T>)
    - 相邻排列所有值，存储相同类型的值.
    - `let v:Vec<i32>=Vec::new();` & `let v=vec![1,2,3];` & `v.push(3);` & `let third:&i32=&v[2];` & `let does_not_exist=v.get(100);` & `for i in &mut v{ *i+=59; }` & `v.pop()` & `enum + vector 实现vec中存放不同类型的数据（但其都是enum的一个类型）`
    -  vector 的工作方式：在 vector 的结尾增加新元素时，在没有足够空间将所有所有元素依次相邻存放的情况下，可能会要求分配新内存并将老的元素拷贝到新的空间中。
- String(UTF-8编码的)
    - 字符串就是作为字节的集合外加一些方法实现的.它是可增长的、可变的、有所有权的、UTF-8 编码的字符串类型。Rust 的核心语言中只有一种字符串类型：str，字符串 slice，它通常以被借用的形式出现，`&str`。
    - `String::from("hello")`<==>`"hello".to_string()`==>`String::new()` & `s.push(s2)`==>`s.push_str(s2)`==>`s3=s+&s2`->`fn add(self,s:&str)->String{}`->`deref coercion`->`String-->&str`-->`&s2-->&s2[..]`==>`let s=format!("{}-{}-{}",s1,s2,s3);`-->不会获取所有权 & `let s = &hello[0..4]`-->`小心使用` & `for c in s.chars(){}`===>`for b in s.bytes(){}`
    - `String` 是一个 `Vec<u8>`的封装。
    - 有效的 Unicode 标量值可能会由不止一个字节组成。
- Hash map
    - HashMap<K,V>:存储一个键类型K对应一个值类型V的映射。可以用任何类型作为键。哈希 map 是同质的：所有的键必须是相同类型，值也必须都是相同类型。
    - `let mut scores=HashMap::new()`==>`let scores:HashMap<_,_>=tems.iter().zip(initial_scores.iter()).collect();`-->teams和initial_scores是元组的vector & `scores.insert(String::form("blue"),10);` & `scores.get("Bule")` & `for (key,value) in &scores {}` & `scores.entry(String::from("Yellow")).or_insert(55);`
    - Hashing Functions



