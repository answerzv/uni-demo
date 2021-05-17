<template>
	<view>
		这是a组件：
		<button @click="addnum">修改b组件里的数据</button>
	</view>
	
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			addnum(){
				uni.$emit('upnum',5)
			}
		}
			}
</script>

<style>
</style>
