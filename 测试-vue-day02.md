# 1. 说说你对计算属性的理解
	computed:包含多个方法的对象
	对状态属性进行计算返回一个新的数据, 供页面获取显示
	一般情况下是相当于是一个只读的属性
	利用set/get方法来实现属性数据的计算读取, 同时监视属性数据的变化
# 2. 说说vue的生命周期
	1)	初始化显示
	    * beforeCreate()
	    * created()
	    * beforeMount()
	    * mounted()
	2)	更新状态: this.xxx = value
	    * beforeUpdate()
	    * updated()
	3)	销毁vue实例: vm.$destory()
	    * beforeDestory()
	    * destoryed()

# 3. 写出7个指令及其作用
	1)	v:text : 更新元素的 textContent
	2)	v-html : 更新元素的 innerHTML
	3)	v-if : 如果为true, 当前标签才会输出到页面
	4)	v-else: 如果为false, 当前标签才会输出到页面
	5)	v-show : 通过控制display样式来控制显示/隐藏
	6)	v-for : 遍历数组/对象
	7)	v-on : 绑定事件监听, 一般简写为@
	8)	v-bind : 强制绑定解析表达式, 可以省略v-bind
	9)	v-model : 双向数据绑定
	10)	 ref : 指定唯一标识, vue对象通过$els属性访问这个元素对象
	11)	 v-cloak : 防止闪现, 与css配合: [v-cloak] { display: none }
# 4. 画出下面代码的内存结构图
	function Foo () {}
	const f1 = new Foo()
	const f2 = new Foo()
	const o1 = new Object()
	const o2 = {}

![](https://i.imgur.com/E3Gja4M.jpg)
