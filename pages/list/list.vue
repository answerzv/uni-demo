<template>
	<view>
		<button type="default" @click="get">发送get请求</button>
		<button type="primary" @click="setStorage">存储数据</button>
	    <button type="primary" v-on:click="getStorage">获取数据</button>
		<button type="primary" v-on:click="removeId">移除id</button>
		<view>
			这是列表页
		</view>
		<view class="box-item" v-for="item in list">{{item}}</view>
		<button v-on:click="pullDown">下拉刷新</button>
	</view>
</template>


<script>
	export default {
		data(){
			return{
				list:['前端','java','ui','测试','前端','java','ui','测试','前端','java','ui','ui','测试','前端','java']
			}
		},
		onPullDownRefresh(){
			console.log('触发了下拉刷新'),
			setTimeout(()=>{
				this.list = ['盗墓笔记','鬼吹灯','灵魂摆渡','无心法师'],
				uni.stopPullDownRefresh()
			},2000)
		},
		
		onReachBottom(){
			console.log('页面到底了')
			this.list = [...this.list,...['nh','rc','lh','wq']]
		},
		methods:{
			pullDown(){
				uni.startPullDownRefresh()
				
			},
		    get(){
				uni.request({
					url:"http://dev.admin.carrots.ptteng.com/a/article/search",
					success(res){
						console.log(res)
					}
				})
			},
			
			setStorage(){
				/*ni.setStorage({
					key:'id', //本地存储
					data:'80',
					success(){
						console.log('存储成功')
					}
				})*/
				uni.setStorageSync('id',100) //同步方法
				
			},
			getStorage(){
				/* uni.getStorage({
					key:"id",
					success(nb){
						console.log("获取成功",nb)
						console.log('获取',nb.data)
					}
					
				}) */
				const res = uni.getStorageSync('id')
				console.log('ok',res)
			},
			removeId(){
			/*	uni.removeStorage({
					key:'id',
					success(){
						console.log('删除成功')
					}
				}) */
				
				uni.removeStorageSync('id')
			}
			
			
		}
	}
	
</script>

<style>
	.box-item{
		height: 100px;
		line-height: 100px;
	}
</style>
