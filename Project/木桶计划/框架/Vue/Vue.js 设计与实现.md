## 非原始值的响应式方案
- 浅响应和深响应的实现
	- 增加 isShallow 配置，在 get proxy 时，判断当前取出来的值是否为对象，为对象时如果 isShallow 为 false 则递归调用 reactive 方法处理
- 数组的代理方式
	- 对额外的读取操作进行响应式更新
		- 通过索引读取元素
		- 访问 length 属性
		- 使用 for...in 访问数组
		- 使用 for...of 访问数组
		- 数组的某些原型方法，如 `include` 、`find` 等