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
- move & clone & copy(Copy trait)
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

