- 出现的背景？
- 底层实现是基于什么的？
	- 自己封装的 getter 和 setter，getter 是个函数，会从 value 取值，看起来像是借鉴了 ref 的结构。
- `writeSignal` 的 observer 什么时候会有值？
- 怎么收集依赖项的？
- creatMemo 底层是懒加载的 createEffect ？