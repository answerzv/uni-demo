<template>
	<view>
		   <view>数据绑定</view>
		   <view>{{msg}}</view>
		   <view>{{'你好'+'sj'}}</view>
		    <view>{{flag?'是':'否'}}</view>
			<image :src="urlmge"></image>
			<view v-for="(item,index) in all" :key='item.id'>   <!-- :key='item.id'>唯一值 -->
				序号：{{index}}名字：{{item.name}} ,  年龄：{{item.age}}
			</view>
			<button  type="primary" @click="clickHandle(20,$event)"> 按钮</button>
	</view>
</template>

<script>
	export default {
		  data(){
			  return{
				  msg:'hello',
				  flag:true,
				  urlmge:'https://ss0.bdstatic.com/70cFuHSh_Q1YnxGkpoWK1HF6hhy/it/u=1136864548,1606862484&fm=26&gp=0.jpg',
				  all:[
					  {
						  name:'数据',
						  age:1,
						  id:2,
					  },
					  {
					  	 name:'信息',
					  	 age:14,
					  	 id:25,
					  },
					  {
					   	 name:'消息',
					     age:55,
					  	 id:23,
					  },
				  ]
			  }
		  },
		  methods:{
			  
			  clickHandle(d,e){
				  console.log('danji',d,e) //e为事件对象
			  }
			 
			  
		  }
	}
	
</script>

  

<style>
</style>
