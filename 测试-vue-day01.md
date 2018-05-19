# 1. 详细说说react-redux库的作用和API
	* 一个react插件库，用来简化react项目中的redux
		* UI组件
			a.	只负责 UI 的呈现，不带有任何业务逻辑
			b.	通过props接收数据(一般数据和函数)
			c.	不使用任何 Redux 的 API
			d.	一般保存在components文件夹下
		* 容器组件
			a.	负责管理数据和业务逻辑，不负责UI的呈现
			b.	使用 Redux 的 API
			c.	一般保存在containers文件夹下
	* API
		* Provider
		* connect()
		* mapStateToprops()
		* mapDispatchToProps()

# 2. 说一下你对Vue的理解
	* vue是一款渐进式JavaScript框架，用来动态构建用户界面
	* 特点：
		* 遵循MVVM模式
		* 编码简介，体积小，效率高
		* 本身只关注UI
	* 借鉴了angular的模板和数据绑定技术
	* 借鉴了react的组件化和虚拟DOM技术

# 3. 说说你对模板的理解
	* 模板就是html标签里嵌套着js代码
	* 基本语法
		* 大括号表达式
		* 指令

# 4. vue的常用配置选项(5个)
	* el
	* data
	* methods
	* computed
	* watch

# 5. 写一个vue的基本使用例子程序

	<div id='app'>
		<input type='text' v-model='msg'/>
		<p>hello,{{msg}}</p>
	</div>
	<script>
		new Vue({
			el: "#app",
			data: "Jason"
		})
	</script>