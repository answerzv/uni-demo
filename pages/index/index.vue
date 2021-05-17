<template>
	<view class="content"><!--父给子传值注册自定义事件@myEven -->
		<testa v-if='flag' :cuttt='title' @myEven="getNum"></testa> <!--属性可以随便写 --> 
	    <button type="primary" @click="checktest">切换组件按钮</button>
		这是子组件传递过来的数据{{num}}
		
		<test-a></test-a>
		 <test-b></test-b>
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testA from '../../components/a.vue'
	import testB from '../../components/b.vue'
	
	export default {
		data() {
			return {
				title: 'Hello',
				flag:true,
				num:0
			}
		},
		methods: {
		    checktest(){
				this.flag= !this.flag
			},
			getNum(z){
				console.log(z)
				this.num = z
			}
		},
		
		// 页面的生命周期
		onLoad(op) {
			console.log('页面加载了时候运行 ' ,op) //用于传参

		},
		onShow(){
			console.log('页面显示了运行 ')
		},
		onReady(){
			console.log('页面初次渲染完成了 ')
		},
		onHide(){
			console.log('页面隐藏了运行 ')
		},
		onUnload(){
			console.log('页面卸载了')
		},
		
		
		
		
		
		
		
		// 组件注册
		components:{
			testa:test,
			"test-a":testA,
			"test-b":testB
			
			
		},
		
		
		
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
