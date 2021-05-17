<template>
	<view>
		<view>导航跳转的学习</view>
		<!-- 声明式导航 -->
		<navigator url='/pages/detail/detail?id=80&age=19'>跳转至详情页</navigator>
		<navigator url='/pages/message/message' open-type="switchTab">跳转至信息页</navigator>
		<navigator url='/pages/detail/detail' open-type="redirect">跳转至详情页</navigator> <!--跳转没有返回页头并关闭上一页 -->
		
		<!-- 编程式导航 -->
		<button @click="goDetail">跳转至详情页</button>
		<button @click="goMessage">跳转至详情页</button>
		<button type="primary" @click="goDetail2">跳转至详情页并关闭当前页面</button>
		
		<button @click="home">跳转至home页</button>
		<button type="default" @click="list">跳转为列表页</button>
		<button type="default" @click="style">跳转为样式页</button>
		<button @click="index">跳转为组件页</button>
		
	</view>
</template>

<script>
	export default{
		onUnload(){ //生命周期函数页面卸载运行
			console.log('导航页面卸载了')
		},
		
		methods:{
			
			goDetail(){
				uni.navigateTo({
					url:'/pages/detail/detail'
				})
			},
			 
			 goMessage(){
				 uni.switchTab({ //跳转至tabBar页面并关闭其它非tabBar页面
					 url:'/pages/message/message'
				 })
			 },
			 
			 goDetail2(){
				 uni.redirectTo({
				 	url:"/pages/detail/detail"
				 })
			 },
			 
			 home(){
				 uni.redirectTo({
				 	url:'../home/home'
				 })
			 },
		
		     list(){
				 uni.redirectTo({
				 	url:'../list/list'
				 })
			 },
			 
			 style(){
				 uni.redirectTo({
				 	url:'../uni-style/uni-style'
				 })
			 },
			 
			 index(){
				 uni.redirectTo({
				 	url:'../index/index'
				 })
			 }
		}
		
		
	}
</script>

<style>
</style>
