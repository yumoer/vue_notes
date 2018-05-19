# 1. 说说vue组件间通信的几种方式
	1). props: 父子组件间相互通信, 可以传递一般数据/函数, 问题: 隔代组件间只能逐层传递/兄弟组件间必须借助于父组件
	2). vue自定义事件: 代替函数类型的prop, 隔代/兄弟组件不方便
	3). 消息订阅与发布(pubsub库): 任意关系组件间都可以
	4). slot: 通信的是标签, 而不仅仅是数据
	5). vuex: 后面讲

# 2. 说说vue项目中如何与后台通信
	1). 通过ajax请求与后台通信
	2). 常用的库有2个
		vue-resource: vue的插件, 用于vue1.x
		axios: 独立的第三方库, 用于vue2.x
	3). 执行请求代码的时机
		初始化异步显示: mounted()
		特定用户操作后异步显示: 事件回调函数或相关函数中

# 3. 路由编码的3步
	1). 定义组件
	2). 映射路由
	3). 使用路由: <router-link>和<router-view>

# 4. 说说vue-router给我们提供了哪些API
	1). 3个组件标签
		router-link
		router-view
		keep-alive
	2). 2个对象
		$route: 包含当前路由信息的路由对象
			path
			params.xxx
			query.xxx
		$router: 包含操作路由的路由器对象
			push(path)
			replace(path)
			back()2
	
# 5. 用数组的相关方法实现以下业务需求
	公司前后招聘了10个员工(性别,年龄, 月薪各不相同),有以下需求
	1). 列表显示所有员工的所有信息
	2). 对员工进行年薪降序列表显示
	3). 得到男员工的总月薪
	4). 查找一个月薪只比1200高一点点的员工
	5). 查找出所有月薪高于1200的员工
	6). 列表显示所有员工的姓名/性别和年薪
	
	const employees = [
		{name: 'A', sex: '男', age: 21, salary: 10000},
		{name: 'B', sex: '女', age: 25, salary: 12000},
		{name: 'C', sex: '男', age: 24, salary: 13000},
		{name: 'D', sex: '男', age: 24, salary: 12500},
		{name: 'E', sex: '女', age: 21, salary: 14000},
		{name: 'F', sex: '男', age: 24, salary: 16000},
		{name: 'G', sex: '男', age: 23, salary: 9000},
		{name: 'H', sex: '女', age: 21, salary: 11000},
		{name: 'I', sex: '男', age: 23, salary: 13200},
		{name: 'J', sex: '男', age: 23, salary: 15000}
	]

	1). employees.forEach(e => console.log(e))
	2). employees.sort((e1, e2) => e2.salary-e1.salary)
	3). employees.reduce((preTotal, e) => preTotal + (e.sex=='男'?e.salary:0), 0)
	4). employees.find(e => e.salary>1200 && e.salary<1400 && e.sex==='男')
	5). employees.filter(e => e.salary>1200)
	6). employees.map(e => ({'姓名/性别': `${e.name}/${e.sex}`, '年薪': e.salary*12}))
	