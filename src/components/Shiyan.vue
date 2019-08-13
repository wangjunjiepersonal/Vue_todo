<template>
	<div>
		<p class="msg">{{msg}}</p>
	</div>
</template>
<script>
	export default{
		data(){
			return{
				msg:'第一次使用vue-cli的实验数据'
			}
		}
	}
</script>
<style>
	.msg{
		color: red;
		font-size: 30px;
	}
</style>