# 1. 说说你对计算属性的理解
	vm上的特别属性, 它的值是由vm上的其它相关属性动态计算确定的(属性的get())
	同时还可以监视该属性值的变化, 去同步更新其它相关属性值(属性的set())

# 2. 说说vue的生命周期
	1). 初始化
		beforeCreate()
		created()
		beforeMount()
		mounted(): 异步任务(发ajax请求/启动定时器)
	2). 更新
		beforeUpdate()
		updated()
	3). 死亡
		beforeDestroy(): 收尾工作(清除定时器)
		destroyed()
	
# 3. 写出7个指令及其作用
	v-text: 设置标签体文本
	v-html: 设置标签体子标签
	v-if/v-else/v-show: 显示/隐藏
	v-for: 遍历显示列表
	v-bind: 强制绑定表达式, 简写:
	v-on: 绑定事件监听, 简写@
	v-model: 双向数据绑定

# 4. 画出下面代码的内存结构图
	function Foo () {}
	const f1 = new Foo()
	const f2 = new Foo()
	const o1 = new Object()
	const o2 = {}

![](https://i.imgur.com/DLtBFLw.png)