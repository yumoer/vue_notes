# 1. 说说你对vuex的理解
	vue的插件
	对vue应用中多个组件的共享状态进行集中式的管理(读/写)

# 2. 在vue项目中引入vuex的基本流程
	下载vuex
	创建store对象
		export default new Vuex.Store({
			state,
			mutations,
			actions,
			gettters
		})
	配置store对象
		new Vue({
			store
		})

# 3. vuex结构图
![](https://i.imgur.com/mje1tyD.png)

# 4. 说说使用vue和jQuery开发项目的区别
	vue不用直接操作页面DOM, 只需要操作数据, 页面就会更新(数据绑定)
	vue支持组件化开发, 能极大的提高开发效率 
