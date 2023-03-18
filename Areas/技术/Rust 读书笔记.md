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

// 报错
let mut spaces = "   ";
spaces = spaces.len();
```


## 数据类型
- 分为基本数据类型和复合数据类型
- 基本数据类型：整数，浮点数，布尔，字符
- 复合数据类型
	- 元组
		- 固定长度，支持不同的数据类型组合
		  ```Rust
		  let tup: (i32, f64, u8) = (100, 1.2, 1);
		  ```

	- 数组
		- 数组长度不可变，向量长度可变
		- 便捷的创建数组的方式 `let arr: [i32;5] = [1;5];`
## 流程控制
- 支持在 `let` 语句中用 `if` 语句控制赋值
  ```Rust
	  let condition = true;
	  let x = if condition {5} elsr {6};
	  println!("x is {}", x); 
  ```
- loop 是用来重试某些操作的，可以用 ` break ` 关键字退出 loop 并且通过 ` break xxx` 来返回值
- 可以用单引号来指定一个循环标签,用 ` break 'xxx ` 的形式来中断 loop 
```Rust
let mut a = 1;
	  'test_loop: loop{
		  if a == 2 {
			  break 'test_loop;
		  }
		  a += 1;
	  };
```

## Range
- 使用 `..` 或 `..=`的形式可以生成一个连续的数字序列
```Rust
let x = 1..4;
let y = 1..=4; 
```
- 使用 `collect` 方法可以将 `Range` 转换为数组
```Rust
let r = 1..4;
let arr: Vec<i32> = r.collect();
```