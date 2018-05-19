# 1. 详细说说react-redux库的作用和API
	作用: 简化react中使用redux的使用
	API:
		Provider组件: <Provider store={store}><App/></Provider>, 为所有层次的容器组件共享store
		connect函数: connect()(UIComponent), 包装UI组件返回容器组件, 向UI组件提供一般/函数属性
	
# 2. 说一下你对Vue的理解
	vue是一个前端JS库
	MVVM模式的实现
	作用: 动态构建用户界面
	重要技术: 模板与数据绑定(angular), 组件与虚拟DOM(react)

# 3. 说说你对模板的理解
	html中嵌套js
	指令: <p v-text='msg'>
	大括号表达式: {{msg}}

# 4. vue的常用配置选项(5个)
	el: 最外层元素选择器
	data: 状态数据
	computed: 计算属性
	methods: 事件回调函数
	watch: 监视属性变化
# 5. 写一个vue的基本使用例子程序
	<div id='test'>
		<input v-model='msg'>
		<p>{{msg}}</p>
	</div>

	<script src='vue.js'>
	<script>
		new Vue({
			el: '#test', 
			data: {msg: 'xxx'}
		})
