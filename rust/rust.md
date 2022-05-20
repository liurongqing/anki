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
