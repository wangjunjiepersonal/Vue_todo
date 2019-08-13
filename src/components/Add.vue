<template>
	<div>
		<form action="">
			用户名<input type="text" placeholder="用户名" v-model="name"/>
			评论内容<input type="text" placeholder="发布留言" v-model="content"/>
			<input type="button" value="提交按钮" @click="add"/>
		</form>
	</div>
</template>
<script>
	export default{
		props:{
			addcomment:{
				type:Function,
				required:true
			}
		},
		data(){
			return{
				name:'',
				content:''
			}
		},
		methods:{
			// 检查内容的合法性
			add(){
				const name = this.name.trim()
				const content = this.content.trim()
				if(!name || !content){
					alert('内容不合法')
				}
			//根据输入的数据 封装一个comment对象
			const comment = {
				name,
				content
			}
			//将数据添加到comments中
			this.addcomment(comment)
			//清除输入
			this.name = ''
			this.content = ''
		}
	}
}		
</script>
<style>
	.msg{
		color: red;
		line-height: 30px;
	}
</style>