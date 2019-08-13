<template>
	<div>
		<ul v-for="(item,index) in comments" :key="index">
			
			<li>发布人：{{item.name}}
			</li>
			<li>
				留言内容：{{item.content}}
			</li>
			<a href="" @click="del">删除</a>
		</ul>
	</div>
</template>
<script>
	export default{
		props:{
			comments:Object,
			delcon:{
				type:Function,
				required:true
			}
			},
		methods:{
			del(){
				const {comment,index} = this
				if (window.confirm(`确定删除${comment.name}吗`)) {
					delcon(index)
				}
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