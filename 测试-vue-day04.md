# 1. 说说vue项目中如何与后台通信
	通过使用第三方的插件库发送ajax请求
		resource
		axios
# 2. 路由编码的3步
	1)	定义路由组件
	2)	注册路由
	3)	使用路由
		<router-link>
		<router-view>

# 3. 说说vue-router给我们提供了哪些API
	//创建路由器
	new VueRouter({//多个配置
		//配置路由
		routes：[
			{//一般路由
				path：'/xxx',
				compoent: Xxx
				children: [
					path：'/xxx/yyy:id',
					compoent: Yyy
				]
			},
			{//自动跳转路由路由
				path：'/',
				redirect: '/xxx'
			},
		]
	})
	//注册路由
	import router from './router'
	new Vue({
		router
	})
# 4. 用数组的相关方法实现以下业务需求
	公司前后招聘了10个员工(性别,年龄, 月薪各不相同),有以下需求
	1. 列表显示所有员工的所有信息
	2. 对员工进行年薪降序列表显示
	3. 得到男员工的总月薪
	4. 查找一个月薪只比1200高一点点的员工
	5. 查找出所有月薪高于1200的员工
	6. 列表显示所有员工的姓名/性别和年薪
	
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

	
	//1. 列表显示所有员工的所有信息: forEach() 遍历
    employees.forEach( (emp)=> console.log(JSON.stringify(emp)));

    //2. 对员工进行yu薪降序列表显示: sort() 比较,更改原数组，返回新数组
    /*let sortEmp = employees.sort((emp1,emp2) =>{
        return emp2.salary - emp1.salary
    });
    console.log(sortEmp);*/

    //3. 得到男员工的总月薪: reduce() 求和
    let empReduce = employees.reduce((prototal,emp) =>{
        return prototal + (emp.sex === "男"?emp.salary:0)
    },0)
    console.log(empReduce);

    //4. 查找一个月薪大于12000且小于14000的男员工: find() 具体查找的第一个
    let empFind = employees.find((emp,index) =>{
        return emp.sex === '男' && emp.salary >12000 && emp.salary < 14000
    });
    console.log(empFind);
    
    //5. 查找出所有月薪高于12000的员工: filter() 过滤 返回新的子数组
    let empFilter = employees.filter((emp,index) =>{
        return emp.salary > 12000
    });
    console.log(empFilter);

    //6. 列表显示所有员工的'姓名/性别'和'年薪': map() 返回新的数组
    let mapEmp = employees.map( (emp,index) =>{
        return {
            '姓名/性别' : `${emp.name}/${emp.sex}`,
            年薪 : emp.salary
        }
    });
    console.log(mapEmp)