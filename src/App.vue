/**
 *app.vue是项目主文件
  如果需要展示其他页面 需要使用 import *** from *** 来指定需要引入的文件
 在script 标签中 使用 export default 来映射组件标签 就是将组件引用到 vue中
 在template标签中 引入需要使用的组件名
 在vue-cli中 不用的区域分为不同的组件 相互使用 import *** from *** 来进行接收
 父子组件之间通信 
 	<!--父组件使用: 对象绑定的形式传递数据 <list :comments:'comments'></list>-->
 	子组件通过props接收父组件传递过来的值或者方法
 	<!--父组件使用子组件传递过来的内容 需要在子组件上传递方法<add :addcomment="addcomment"></add>-->
 */
<template>
  <div id="app">
    <div>
    	<h2>自定义项目</h2>
    	<add :addcomment="addcomment"></add>
    	<list :comments='comments' :delcon="delcon"></list>
    </div>
  </div>
</template>

<script>
import add from './components/Add.vue'
import list from './components/List.vue'
export default {
  data(){
  	return{
  		comments:[
  			{
  				name:'张三',
  				content:'vue初始实战1'
  			},
  			{
  				name:'李四',
  				content:'vue初始实战2'
  			},
  			{
  				name:'王五',
  				content:'vue初始实战3'
  			}
  		]
  	}
  },
  methods:{
//	添加评论
  	addcomment(comment){
  		this.comments.unshift(comment)
  	},
//	删除指定评论 index是索引
	delcon(index){
		this.comments.splice(index,1)
	}
  },
  components:{
  	add,
  	list
  }
}
</script>
<style>
</style>
