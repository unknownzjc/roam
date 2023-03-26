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

## 所有权
### 所有权规则
- 所有值都有它的拥有者
- 一个值同一时间内只有一个拥有者
- 值在超过作用域之后就会被丢弃
### 变量的移动
- 当一个变量被赋给另一个变量时，通常会导致这个变量失去所有权，如果在后面使用则会报 `value borrowed here after move` 的错误
- 哪些数据类型的变量会发生 move 语义传递？
	- 默认情况下所有数据类型都具有 move 语义传递，但是实现了 Copy trait 的数据类型是例外，它们允许被复制值，而不是使用 move 的方式来转移所有权，这些数据类型包括基本整数类型，布尔类型，字符类型，浮点数类型，元组（所有元素都是 Copy 类型时），数组（所有元素都是 Copy 类型时）还有一些结构体类型。如果一个数据类型没有实现 Copy trait，那么它就只能通过 move 来转移所有权
- Drop trait
	- 实现了 Drop trait 的数据类型在所有权被转移之后，作用域结束后会调用 `drop` 进行资源清理。所以说，实现了 Drop trait 的数据类型具有更严格的所有权转移机制和资源清理机制
	- Drop trait 和 Copy trait 是互斥的操作
### 引用和借用
主要是为了解决变量在传递过程中，需要传入传出的问题，通过引用可以使函数可以引用值而不对值有所有权。
- 引用可以通过 `&` 来表示
  ```Rust
  fn calc_len(s: &String) -> usize {
      s.len()
  }
  let s = String::from("hello");
  let len = calc_len(&s);
```
- 当一个变量借用别人时，它不能修改借用的东西
- 可变借用和不可变引用不能在同一个作用域下共存
- 不能同时有两个可变引用存在
