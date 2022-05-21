## 1. 常用数组分二种

1. 一种是速度很快、长度固定的 `array` 数组

   ```rust
   let a = [1, 2, 3, 4];
   ```

2. 一种是可动态增长的但是有性能损耗的 `Vector` 动态数组

   ```rust
   let mut v: Vec<i8> = vec![1, 2, 3];
   ```

## 2. if else 基本写法

```rust
// 如果 condition 为 true，则执行 A， 否则执行 B
let condition = true;
if condition {
    // A...
} else {
    // B...
}
```

## 3. Rust 语言中有三种循环方式

`for`、`while` 和 `loop`

## 4. `for` 循环

```rust
for i in 1..=5 {
    println!("{}", i);
}
// 1
// 2
// 3
// 4
// 5
```

## 5. 不想用的变量用 `_` 来代替

```rust
// 循环 10 次，如果不使用 _，编辑器会给个变量未使用的警告
for _ in 0..10 {
 // 此处只想做点事情，不想用变量
}
```

## 6. continue 跳出当前当次的循环

```rust
for i in 1..4 {
    if i == 2 {
        continue;
    }
    println!("{}", i);
}
// 1
// 3
```

## 7. break 跳出当前的循环

```rust
for i in 1..4 {
    if i == 2 {
        break;
    }
    println!("{}", i);
}
// 1
```

## 8. while 循环

```rust
let mut n = 0;
while n < 5 {
    println!("{}", n);
    n += 1;
}

println!("我出来了");
```

## 9. loop 循环 + break

```rust
let mut counter = 0;
let result = loop {
    counter += 1;
    if counter == 10 {
        break counter * 2;
    }

    println!("result is {}", result);
}
```

## 10.声明一个变量

```rust
let x = 5;
```

## 11. 声明一个可变变量

```rust
let mut x = 5;
x = 6;
```

## 12. 忽略下划线开头的未使用的变量

```rust
let _x = 5;
```

## 13. 变量解构

```rust
let (a, mut b) : (bool, bool) = (true, false);
b = true;
```

## 14. Rust 注释跟 JavaScript 一样

```rust
// 这是第一种注释

/* 这是第二种注释 */

/*
 * 多行注释
 * 多行注释
 */

/// 头部说明文档的注释
```

## 15. cargo doc

```bash
# 生成文档，并打开在浏览器上
cargo doc --open 
```

## 16. 声明一个常量

```rust
const a: i8 = 100;
```

## 17. 重影 (shadowing)

```rust
let a: i8 = 10;
let a: i8 = a + 1;
println!("{}", a);
```

## 18. 声明个浮点类型

```rust
// 默认浮点类型64位
let a: f64 = 2.0;
```

## 19. 数学基本运算

```rust
let a = 1 + 2; // 加法
let b = 2 - 1; // 减法
let c = 2 * 3; // 乘法
let d = 2 / 3; // 除法
let ef = 3 % 2; // 求余
let mut sum = 1;
sum += 1; // 自运算，不支持++ --
```

## 20. 声明一个普通数组

```rust
let arr: [i32; 3] = [11, 22, 33];
```

## 21. 声明一个基本函数

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}
```

## 22. 用 `{}` 块里的表达式绑定一个变量

```rust
let x = {
    let y = 1;
    y + 1
};
```

## 23. 用 `loop` + `break` 块里的表达式绑定一个变量

```rust
let mut a = 1;
let b = loop {
    if a >= 10 {
        break a;
    }
    a += 1;
};
println!("{}", b); // 10
```

## 24. 所有权三条规则

1. 每个值都有一个变量称为所有者
2. 一个值只能有一个所有者
3. 所有者不在程序运行范围内则删除

## 25. 一个变量的内存

> 变量的值存在于内存中

## 26. 变量与数据交互方式(移动Move与克隆Clone)

```rust
// 移动
let x = 5;
let y = x;

// s1 不可再使用
let s1 = String::from("hello");
let s2 = s1;

// s1 可继续用
let s1 = String::from("hello");
let s2 = s1.clone();
```

## 27. 函数参数的所有权

```rust
let s = String::from("hello");
// s 有效
add(s); // 当成函数参数与移动效果一样
// s 无效
```

## 28. 函数返回值的所有权

```rust
// s1 的所有权返回给了 s2
let s2 = some_action();
fn some_action() -> String {
    let s1 = String::from("hello");
    return s1;
}
```

## 29. 最简单的引用

```rust
// 引用是间接访问方式，不会在栈中复制变量的值
let s1 = String::from("hello");
let s2 = &s1;
```

## 30. 最简单的可变引用

```rust
// 可变引用不可多重引用，不可变引用可以
let mut s1 = String::from("hello");
let s2 = &mut s1;

s2.push_str(" world");
```

## 31. 最简单的垂悬引用

```rust
// 局部s本身没有当做返回值被释放了
// 引用却被返回了，引用的值已经不存在了
fn main() {
    let reference1 = dangle();
}
fn dangle() {
    let s = String::from("hello");
    &s
}
```

## 32. 最简单的字符串切片

切片(slice)是对数据值的部分引用

```rust
let s = String:from("broadcast");
let s1 = &s[0..5]; // 索引0-4
let s2 = &s[5..9]; // 索引5-8
```

## 33. `..` 表示范围的语法

..y 等价于 0..y     
x.. 等价于 位置 x 到数据结束    
.. 等价于 0 到结束  

## Rust 常用的字符串类型有 &str 和 String

```rust
let s1: &str = "hello"; // &str
let s2: String = String::from("hello");
```

## 数组切片

```rust
let arr = [1, 3, 5, 7, 9];
let part = &arr[0..3];
for i in part {
    println!("{}", i);
}
```