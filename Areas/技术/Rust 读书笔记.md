## 环境配置

## Cargo 及工程化 

## 变量
- 变量默认不可变，如果要让变量变成可变的，加上 `mut` 关键字
- 通过下划线前缀(类似 `_x` 这样)来表明变量虽然未被使用，但是它是有用的，规避 Rust 编译器的告警
- 作用域是块级作用域，即 `{}` 结束的位置，变量就失效了
- 将字符串转换为 String 包装类型的方法是调用 `to_string` 方法
- 定义函数返回值是这样的形式:
```Rust
fn define_x() -> String {
	let x = "hello".to_string()
	x
}
```
- 很奇怪，不用return 的，不知道返回多个的时候是怎么做的？
- 变量遮蔽跟 `mut` 的区别在于，变量遮蔽能够直接改掉一个值的类型，而 `mut` 的则只能修改值
```Rust
// 允许
let spaces = "  ";
let spaces = space.len();

// 报错,不能将
let mut spaces = "   ";
spaces = spaces.len();
```


## 数据类型

