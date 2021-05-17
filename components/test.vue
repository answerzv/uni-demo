<template>
	<view id="myView">
		这是test组件{{num}}
		这是父子件传递过来的数据{{cuttt}}
		
		<button @click="sendNum">给父组件传值</button>
	</view>
</template>

<script>
	export default {
		data(){
			return{
				num:3,
				in:null
			}
		},
		methods:{
			sendNum(){
				console.log('给父组件传值')
				this.$emit('myEven',this.num)
			}
		},
		
		props:['cuttt'],
		
		
		//组件生命周期  beforeCreate在实例初始化后被调用 但数据页面还没初始化完成
		beforeCreate(){
			console.log('实例已经开始初始化化了')
			console.log(this.num) //打印为undefined
		},
		
		//在实例创建完成后立即调用
		created(){ //一般都在created里进行数据的初始化
			//console.log('created',this.num)
		//	this.in = setInterval(()=>{
			//	console.log('执行定时器')
			//},1000)
	    },
		beforeMount(){// 这时候组件还没有渲染在页面上
			//console.log('beforemount',document.getElementById('myView'))  dom仅支持h5
		},
		mounted(){ //组件挂载了已经渲染了
			//console.log('mounted',document.getElementById('myView'))
		},
		destroyed(){
			console.log('组件销毁了')
			//clearInterval(this.in)
		}
		
		
	}
</script>

<style>
</style>
